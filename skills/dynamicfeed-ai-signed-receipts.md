---
name: dynamicfeed-ai-signed-receipts
description: "Mint and independently verify signed receipts of what an agent did \u2014 transaction witness, proof-of-model\
  \ inference receipt, eval receipt \u2014 and check them against the append-only notary log and daily checkpoints."
api: Dynamic Feed REST API
base_url: https://dynamicfeed.ai
openapi: openapi/dynamicfeed-ai-openapi.yml
operations:
- signup_signup_post
- v1_me_v1_me_get
- v1_witness_sample_v1_witness_sample_get
- v1_witness_v1_witness_post
- v1_inference_receipt_v1_inference_receipt_post
- v1_eval_receipt_v1_eval_receipt_post
- v1_witness_inclusion_v1_witness__idx__inclusion_get
- v1_notary_head_v1_notary_log_head_get
- v1_notary_proof_v1_notary_log__idx__proof_get
- v1_checkpoints_v1_checkpoints_get
- v1_checkpoint_proof_v1_checkpoints__day__proof_get
auth: keyless for reads; X-API-Key (POST /signup) for per-user writes
generated: '2026-09-19'
method: generated
source: openapi/_original/dynamicfeed-ai-openapi.json + https://dynamicfeed.ai/llms.txt + https://dynamicfeed.ai/v1
  (every operationId verified against the spec)
---

# dynamicfeed-ai-signed-receipts

## When to use
When a machine decision may later have to be defended: an agent-to-agent transaction, which model actually answered, a benchmark run.

## Steps
1. **Get a key once** — `POST /signup` (`signup_signup_post`, optional `{"email": ...}`) returns `api_key`; send it as `X-API-Key`. Check quota any time with `GET /v1/me` (`v1_me_v1_me_get`).
2. **Rehearse** — `GET /v1/witness/sample` (`v1_witness_sample_v1_witness_sample_get`) returns a keyless sample `txn-receipt/v1` so you can wire verification before minting anything real.
3. **Mint** — `POST /v1/witness` (`v1_witness_v1_witness_post`) with the record or just its sha256 (hash-first; the witness sits beside the deal, never in the money path). For inference provenance use `POST /v1/inference-receipt` (`v1_inference_receipt_v1_inference_receipt_post`); for a sealed benchmark, `POST /v1/eval-receipt` (`v1_eval_receipt_v1_eval_receipt_post`). Schemas are in json-schema/ (txn-receipt-v1, inference-receipt-v1, eval-receipt-v1).
4. **Prove inclusion** — `GET /v1/witness/{idx}/inclusion` (`v1_witness_inclusion_v1_witness__idx__inclusion_get`) or `GET /v1/notary/log/{idx}/proof` (`v1_notary_proof_v1_notary_log__idx__proof_get`) against the current head from `GET /v1/notary/log/head` (`v1_notary_head_v1_notary_log_head_get`). Daily chained digests: `GET /v1/checkpoints` (`v1_checkpoints_v1_checkpoints_get`) and `GET /v1/checkpoints/{day}/proof` (`v1_checkpoint_proof_v1_checkpoints__day__proof_get`).
5. **Verify offline** — DF-VERIFY/1: drop `signature` (and `anchor`), canonicalize json-sorted-compact, verify Ed25519 against `/.well-known/keys`; enforce the key lifecycle registry (the former key `df-ed25519-4cb32e72f333` is `compromised`).

## Rules
- Receipts are irreversible and there is no idempotency key: a retried POST mints a second receipt. Persist the returned `idx` before retrying.
- `POST /v1/vc` is quarantined and returns 503 — do not call it.
- Zero PII by construction: send hashes, not payloads, wherever the profile allows.
