---
name: dynamicfeed-ai-robot-awareness
description: Get a signed go / caution / no-go verdict for a robot or embodied agent at a place and time, then anchor
  it with an RFC 3161 timestamp so the decision record is independently verifiable.
api: Dynamic Feed REST API
base_url: https://dynamicfeed.ai
openapi: openapi/dynamicfeed-ai-openapi.yml
operations:
- v1_awareness_v1_awareness_post
- v1_preflight_v1_preflight_post
- v1_road_v1_road_post
- v1_humanoid_v1_humanoid_post
- v1_marine_v1_marine_post
- v1_anchor_v1_anchor_post
- v1_robot_receipt_v1_robot_receipt_post
- v1_robot_receipt_sample_v1_robot_receipt_sample_get
auth: keyless for reads; X-API-Key (POST /signup) for per-user writes
generated: '2026-09-19'
method: generated
source: openapi/_original/dynamicfeed-ai-openapi.json + https://dynamicfeed.ai/llms.txt + https://dynamicfeed.ai/v1
  (every operationId verified against the spec)
---

# dynamicfeed-ai-robot-awareness

## When to use
Before a ground, humanoid, aerial, marine or orbital system acts outdoors. Advisory evidence, never a safety system (the provider states this on every verdict).

## Steps
1. **Ask for the verdict** — `POST /v1/awareness` (`v1_awareness_v1_awareness_post`) with `{"robot":{"class":"aerial"},"location":{"lat":51.5,"lon":-0.12}}`. Keyless. The response fuses live weather, air quality, space weather and nearby earthquakes under a hard deadline; it degrades to `caution` rather than hanging, and floors to `caution` on stale safety data. Class-specific variants: `v1_preflight_v1_preflight_post` (aerial), `v1_road_v1_road_post`, `v1_humanoid_v1_humanoid_post`, `v1_marine_v1_marine_post`.
2. **Validate the shape** — the verdict conforms to `awareness/v1` (json-schema/dynamicfeed-ai-awareness-v1.json).
3. **Anchor it** — `POST /v1/anchor` (`v1_anchor_v1_anchor_post`) with the snapshot digest to request an RFC 3161 timestamp artifact (hash only, no account). The provider states that artifact issuance "does not by itself establish full independent validation"; validate the token and chain yourself if the record matters.
4. **Record what the robot did** — see the sample first with `GET /v1/robot-receipt/sample` (`v1_robot_receipt_sample_v1_robot_receipt_sample_get`), then mint with `POST /v1/robot-receipt` (`v1_robot_receipt_v1_robot_receipt_post`; requires a free `X-API-Key` from `POST /signup`).

## Rules
- Reversibility: a minted receipt and an anchor are permanent (append-only transparency log). Use the `/sample` route to rehearse.
- Verify the Ed25519 signature on the verdict against `/.well-known/keys` before acting on it.
