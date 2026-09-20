---
name: dynamicfeed-ai-watch-and-notify
description: 'Monitor a set of live values and get pushed when they change: a per-key watchlist pulled in one call,
  HMAC-signed webhooks on change, or a keyless SSE stream.'
api: Dynamic Feed REST API
base_url: https://dynamicfeed.ai
openapi: openapi/dynamicfeed-ai-openapi.yml
operations:
- signup_signup_post
- v1_watchlist_post_v1_watchlist_post
- v1_watchlist_get_v1_watchlist_get
- v1_watchlist_delete_v1_watchlist_delete
- v1_webhooks_create_v1_webhooks_post
- v1_webhooks_test_v1_webhooks_test_post
- v1_webhooks_list_v1_webhooks_get
- v1_webhooks_delete_v1_webhooks_delete
- v1_stream_v1_stream_get
auth: keyless for reads; X-API-Key (POST /signup) for per-user writes
generated: '2026-09-19'
method: generated
source: openapi/_original/dynamicfeed-ai-openapi.json + https://dynamicfeed.ai/llms.txt + https://dynamicfeed.ai/v1
  (every operationId verified against the spec)
---

# dynamicfeed-ai-watch-and-notify

## When to use
An agent that must react to the world (a CVE lands on CISA KEV, a market opens, a wildfire grows) rather than poll 94 tools.

## Steps
1. **Key** — `POST /signup` (`signup_signup_post`); watchlist and webhooks are per-user and need `X-API-Key`. The SSE stream does not.
2. **Watchlist** — `POST /v1/watchlist` (`v1_watchlist_post_v1_watchlist_post`) with `{label, tool, args}` items (add/replace). `GET /v1/watchlist?pull=true` (`v1_watchlist_get_v1_watchlist_get`) returns the CURRENT value of everything watched in one call. Remove with `DELETE /v1/watchlist?label=…` (`v1_watchlist_delete_v1_watchlist_delete`).
3. **Webhook on change** — `POST /v1/webhooks` (`v1_webhooks_create_v1_webhooks_post`) with `{"url":"https://you.example/hook","tool":"exploited_vulnerabilities","args":{}}`. The URL is SSRF-validated (public http/https only). The response carries a ONE-TIME `secret`: store it; every delivery is HMAC-SHA256 signed in `X-DynamicFeed-Signature: sha256=…`. Fire a test with `POST /v1/webhooks/test` (`v1_webhooks_test_v1_webhooks_test_post`); audit with `GET /v1/webhooks` (`v1_webhooks_list_v1_webhooks_get`); remove with `DELETE /v1/webhooks` (`v1_webhooks_delete_v1_webhooks_delete`).
4. **Stream** — `GET /v1/stream?tool=current_time&interval=5&count=3` (`v1_stream_v1_stream_get`) as an EventSource: one `value` event per interval (5–300 s), up to 60 updates per connection.

## Rules
- Reversibility: DELETE exists for both watchlist items and webhooks; no window is stated. Registration is not idempotent — check `GET /v1/webhooks` before re-registering after a timeout.
- Verify the HMAC on every delivery; no timestamp is included, so add your own replay window.
- No event catalogue exists: the "event" is always "this tool's value changed".
