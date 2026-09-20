---
name: dynamicfeed-ai-verify-before-answer
description: 'Ground a draft answer against live, signed data before committing to it: batch the relevant tools
  keyless, run the guard/drift checks, and verify the Ed25519 signature offline.'
api: Dynamic Feed REST API
base_url: https://dynamicfeed.ai
openapi: openapi/dynamicfeed-ai-openapi.yml
operations:
- v1_batch_v1_batch_post
- v1_guard_v1_guard_post
- v1_drift_v1_drift_post
- v1_explain_v1_explain_get
- v1_sources_v1_sources_get
- v1_facts_v1_facts_get
auth: keyless for reads; X-API-Key (POST /signup) for per-user writes
generated: '2026-09-19'
method: generated
source: openapi/_original/dynamicfeed-ai-openapi.json + https://dynamicfeed.ai/llms.txt + https://dynamicfeed.ai/v1
  (every operationId verified against the spec)
---

# dynamicfeed-ai-verify-before-answer

## When to use
Before an agent asserts anything about the present (a version, a price, a hazard, a sanction, the time). Reads are keyless; no signup.

## Steps
1. **Batch the facts** — `POST /v1/batch` (`v1_batch_v1_batch_post`) with `{"calls":[{"tool":"reality_check","args":{"claim":"<draft claim>"}},{"tool":"current_time","args":{}}]}`. Up to 20 calls per request; each call has its own 20 s deadline, so one slow upstream degrades one item, never the batch. Add `"facts": true` to get each result as a reliability-graded canonical fact (`confidence`, `sources`, `verified`, `conflict`).
2. **Guard the draft** — `POST /v1/guard` (`v1_guard_v1_guard_post`) with the answer you are about to send; the verdict is `pass` or `revise` with the exact corrections.
3. **Audit many claims at once** — `POST /v1/drift` (`v1_drift_v1_drift_post`) grades a list of claims drifted / confirmed / unverifiable with severity.
4. **Explain provenance when challenged** — `GET /v1/explain?subject=<tool>` (`v1_explain_v1_explain_get`) returns the chain of custody origin → ingest → normalize → serve; `GET /v1/sources` (`v1_sources_v1_sources_get`) lists every upstream feed with licence and official URL. `GET /v1/facts` (`v1_facts_v1_facts_get`) is the canonical-fact surface.
5. **Verify, don't trust** — every result carries `signature {alg: Ed25519, key_id, canonicalization: json-sorted-compact, sig}`. Drop `signature`, serialize with sorted keys and compact separators, verify against `GET /.well-known/keys`, and reject any `key_id` whose status in `/.well-known/signing-key-registry.json` is not `active`.

## Rules
- Treat `freshness.state` other than `live` as a reason to caveat, and `verified: false` as "signed, not corroborated" — the provider's own rule is *signed is not verified*.
- Errors: a malformed batch returns 400 `{error, available_tools}`; individual items fail inside a 200 with `ok: false`. No `Retry-After` is emitted; back off yourself.
- Idempotency: reads are safe to retry. There is no idempotency key on any write.
