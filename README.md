# Dynamic Feed

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Dynamic Feed, a product of Fluxdyne Pty Ltd (Australia), is a live-data and machine-evidence layer for AI agents and robots: 94 read-only tools across 20 domains (weather and air quality, natural hazards, space weather and satellite positions, CVEs and actively-exploited vulnerabilities, software versions and EOL, sanctions and Federal Register, shipping, macro and rates, AI-model pricing and provider latency) drawn from named public sources such as NASA, NOAA, USGS, CISA, OFAC and the World Bank plus its own measurements. Every response carries a provenance and freshness envelope and a detached Ed25519 signature (DF-VERIFY/1) verifiable offline against published keys. The same tool registry is served three ways from one host: a keyless MCP server at /mcp (Streamable HTTP, protocol 2025-06-18), an A2A 1.0 agent at /a2a with a conformant signed agent card, and a REST API published as OpenAPI 3.1 with a keyless 20-call batch endpoint. A /v1 surface adds robot go/caution/no-go awareness verdicts, RFC 3161 anchoring, signed transaction/inference/robot/eval receipts on an append-only notary log with daily checkpoints, per-key watchlists, HMAC-signed change webhooks and an SSE stream. Paid access is machine-native via x402 (HTTP 402, USDC on Base, 0.001 USDC per call).

**Areas:** Live Data · AI Agents · MCP · A2A · Agent-Native · Provenance · Weather · Natural Hazards · Vulnerabilities · Sanctions · Space · Robotics

## Dynamic Feed on APIs.io

Everything profiled for Dynamic Feed is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/dynamicfeed-ai/](https://apis.io/providers/dynamicfeed-ai/)** — or go straight to one of the APIs or properties below.

### APIs (71)

- [Dynamic Feed MCP Server](https://apis.io/apis/dynamicfeed-ai/dynamic-feed-mcp-server/) — Hosted, keyless Model Context Protocol server at https://dynamicfeed.ai/mcp (Streamable HTTP with legacy HTTP+SSE auto-detected; explicit SSE at /sse)…
- [Dynamic Feed A2A Agent](https://apis.io/apis/dynamicfeed-ai/dynamic-feed-a2a-agent/) — A2A 1.0 JSON-RPC agent at https://dynamicfeed.ai/a2a with a JWS-signed agent card (graded conformant) declaring eight keyless skills — live weather, natural…
- [Dynamic Feed Webhooks and Live Stream](https://apis.io/apis/dynamicfeed-ai/dynamic-feed-webhooks-and-stream/) — Push-on-change webhooks registered per key at POST /v1/webhooks (SSRF-validated URL, one-time secret, HMAC-SHA256 X-DynamicFeed-Signature on every delivery)…
- [Dynamic Feed Advisories API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-advisories-api/) — The Advisories API from Dynamic Feed — 2 operation(s) for advisories.
- [Dynamic Feed Agent API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-agent-api/) — The agent API from Dynamic Feed — 53 operation(s) for agent.
- [Dynamic Feed Agent Stats API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-agent-stats-api/) — The Agent Stats API from Dynamic Feed — 1 operation(s) for agent stats.
- [Dynamic Feed Ai Models API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-ai-models-api/) — The Ai Models API from Dynamic Feed — 1 operation(s) for ai models.
- [Dynamic Feed Air Quality API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-air-quality-api/) — The Air Quality API from Dynamic Feed — 1 operation(s) for air quality.
- [Dynamic Feed Airport Delays API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-airport-delays-api/) — The Airport Delays API from Dynamic Feed — 1 operation(s) for airport delays.
- [Dynamic Feed Benchmarks API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-benchmarks-api/) — The Benchmarks API from Dynamic Feed — 2 operation(s) for benchmarks.
- [Dynamic Feed Billing API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-billing-api/) — The Billing API from Dynamic Feed — 3 operation(s) for billing.
- [Dynamic Feed Carbon Intensity API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-carbon-intensity-api/) — The Carbon Intensity API from Dynamic Feed — 1 operation(s) for carbon intensity.
- [Dynamic Feed China API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-china-api/) — The China API from Dynamic Feed — 1 operation(s) for china.
- [Dynamic Feed Cite API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-cite-api/) — The Cite API from Dynamic Feed — 1 operation(s) for cite.
- [Dynamic Feed Consensus API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-consensus-api/) — The Consensus API from Dynamic Feed — 1 operation(s) for consensus.
- [Dynamic Feed Convert API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-convert-api/) — The Convert API from Dynamic Feed — 1 operation(s) for convert.
- [Dynamic Feed Countdown API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-countdown-api/) — The Countdown API from Dynamic Feed — 1 operation(s) for countdown.
- [Dynamic Feed Dataset API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-dataset-api/) — The Dataset API from Dynamic Feed — 8 operation(s) for dataset.
- [Dynamic Feed Dev API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-dev-api/) — The dev API from Dynamic Feed — 3 operation(s) for dev.
- [Dynamic Feed Drought API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-drought-api/) — The Drought API from Dynamic Feed — 1 operation(s) for drought.
- [Dynamic Feed Drug Shortages API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-drug-shortages-api/) — The Drug Shortages API from Dynamic Feed — 1 operation(s) for drug shortages.
- [Dynamic Feed Dynamic Feed — Live Data For AI API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-dynamic-feed-live-data-for-ai-api/) — The Dynamic Feed — Live Data For AI API from Dynamic Feed — 1 operation(s) for dynamic feed — live data for ai.
- [Dynamic Feed Earthquakes API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-earthquakes-api/) — The Earthquakes API from Dynamic Feed — 1 operation(s) for earthquakes.
- [Dynamic Feed Energy API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-energy-api/) — The Energy API from Dynamic Feed — 1 operation(s) for energy.
- [Dynamic Feed Exploited Vulnerabilities API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-exploited-vulnerabilities-api/) — The Exploited Vulnerabilities API from Dynamic Feed — 1 operation(s) for exploited vulnerabilities.
- [Dynamic Feed Federal Register API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-federal-register-api/) — The Federal Register API from Dynamic Feed — 1 operation(s) for federal register.
- [Dynamic Feed Flights API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-flights-api/) — The Flights API from Dynamic Feed — 1 operation(s) for flights.
- [Dynamic Feed Forecast API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-forecast-api/) — The Forecast API from Dynamic Feed — 1 operation(s) for forecast.
- [Dynamic Feed Global Disasters API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-global-disasters-api/) — The Global Disasters API from Dynamic Feed — 1 operation(s) for global disasters.
- [Dynamic Feed Gps Interference API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-gps-interference-api/) — The Gps Interference API from Dynamic Feed — 1 operation(s) for gps interference.
- [Dynamic Feed Health API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-health-api/) — The Health API from Dynamic Feed — 1 operation(s) for health.
- [Dynamic Feed History API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-history-api/) — The History API from Dynamic Feed — 1 operation(s) for history.
- [Dynamic Feed Info API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-info-api/) — The Info API from Dynamic Feed — 1 operation(s) for info.
- [Dynamic Feed Internet Outages API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-internet-outages-api/) — The Internet Outages API from Dynamic Feed — 1 operation(s) for internet outages.
- [Dynamic Feed Iss API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-iss-api/) — The Iss API from Dynamic Feed — 1 operation(s) for iss.
- [Dynamic Feed Launches API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-launches-api/) — The Launches API from Dynamic Feed — 1 operation(s) for launches.
- [Dynamic Feed Macro API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-macro-api/) — The Macro API from Dynamic Feed — 1 operation(s) for macro.
- [Dynamic Feed Market Hours API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-market-hours-api/) — The Market Hours API from Dynamic Feed — 1 operation(s) for market hours.
- [Dynamic Feed Models API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-models-api/) — The Models API from Dynamic Feed — 1 operation(s) for models.
- [Dynamic Feed Movers API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-movers-api/) — The Movers API from Dynamic Feed — 1 operation(s) for movers.
- [Dynamic Feed Natural Events API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-natural-events-api/) — The Natural Events API from Dynamic Feed — 1 operation(s) for natural events.
- [Dynamic Feed News API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-news-api/) — The News API from Dynamic Feed — 1 operation(s) for news.
- [Dynamic Feed Orbital Datacenters API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-orbital-datacenters-api/) — The Orbital Datacenters API from Dynamic Feed — 1 operation(s) for orbital datacenters.
- [Dynamic Feed Rates API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-rates-api/) — The Rates API from Dynamic Feed — 1 operation(s) for rates.
- [Dynamic Feed Reality Check API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-reality-check-api/) — The Reality Check API from Dynamic Feed — 1 operation(s) for reality check.
- [Dynamic Feed Recalls API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-recalls-api/) — The Recalls API from Dynamic Feed — 1 operation(s) for recalls.
- [Dynamic Feed Robot API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-robot-api/) — The robot API from Dynamic Feed — 10 operation(s) for robot.
- [Dynamic Feed Sanctions API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-sanctions-api/) — The Sanctions API from Dynamic Feed — 1 operation(s) for sanctions.
- [Dynamic Feed Satellite API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-satellite-api/) — The Satellite API from Dynamic Feed — 1 operation(s) for satellite.
- [Dynamic Feed Satellites API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-satellites-api/) — The Satellites API from Dynamic Feed — 1 operation(s) for satellites.
- [Dynamic Feed Sec Filings API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-sec-filings-api/) — The Sec Filings API from Dynamic Feed — 1 operation(s) for sec filings.
- [Dynamic Feed Security API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-security-api/) — The security API from Dynamic Feed — 1 operation(s) for security.
- [Dynamic Feed Servers API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-servers-api/) — The Servers API from Dynamic Feed — 1 operation(s) for servers.
- [Dynamic Feed Shipping API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-shipping-api/) — The Shipping API from Dynamic Feed — 1 operation(s) for shipping.
- [Dynamic Feed Signals API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-signals-api/) — The Signals API from Dynamic Feed — 1 operation(s) for signals.
- [Dynamic Feed Signup API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-signup-api/) — The Signup API from Dynamic Feed — 1 operation(s) for signup.
- [Dynamic Feed Space Weather API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-space-weather-api/) — The Space Weather API from Dynamic Feed — 1 operation(s) for space weather.
- [Dynamic Feed Sports API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-sports-api/) — The Sports API from Dynamic Feed — 2 operation(s) for sports.
- [Dynamic Feed Status API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-status-api/) — The Status API from Dynamic Feed — 1 operation(s) for status.
- [Dynamic Feed Tides API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-tides-api/) — The Tides API from Dynamic Feed — 1 operation(s) for tides.
- [Dynamic Feed Time API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-time-api/) — The Time API from Dynamic Feed — 1 operation(s) for time.
- [Dynamic Feed Treasury Yields API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-treasury-yields-api/) — The Treasury Yields API from Dynamic Feed — 1 operation(s) for treasury yields.
- [Dynamic Feed verified facts API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-verified-facts-api/) — The verified facts API from Dynamic Feed — 4 operation(s) for verified facts.
- [Dynamic Feed Versions API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-versions-api/) — The Versions API from Dynamic Feed — 1 operation(s) for versions.
- [Dynamic Feed Volcanoes API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-volcanoes-api/) — The Volcanoes API from Dynamic Feed — 1 operation(s) for volcanoes.
- [Dynamic Feed Water Levels API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-water-levels-api/) — The Water Levels API from Dynamic Feed — 1 operation(s) for water levels.
- [Dynamic Feed Weather Alerts API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-weather-alerts-api/) — The Weather Alerts API from Dynamic Feed — 1 operation(s) for weather alerts.
- [Dynamic Feed Weather API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-weather-api/) — The Weather API from Dynamic Feed — 3 operation(s) for weather.
- [Dynamic Feed Whats New API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-whats-new-api/) — The Whats New API from Dynamic Feed — 1 operation(s) for whats new.
- [Dynamic Feed Wildfires API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-wildfires-api/) — The Wildfires API from Dynamic Feed — 1 operation(s) for wildfires.
- [Dynamic Feed World Pulse API](https://apis.io/apis/dynamicfeed-ai/dynamicfeed-ai-world-pulse-api/) — The World Pulse API from Dynamic Feed — 1 operation(s) for world pulse.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Dynamicfeed Ai Webhooks](https://apis.io/asyncapis/dynamicfeed-ai/dynamicfeed-ai-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [dynamicfeed-ai-mcp.yml](https://apis.io/servers/dynamicfeed-ai/dynamicfeed-ai-mcp-yml/)

#### JSON Schema (16)

The data models the API reads and writes.

- [DF-VERIFY/1 — attestation/v1 profile (parametric trigger)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-attestation-v1/)
- [DF-VERIFY/1 — awareness/v1 profile](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-awareness-v1/)
- [DF-VERIFY/1 — delivery-receipt/v1 (proof of delivery for agent commerce)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-delivery-receipt-v1/)
- [Dynamic Feed eval-receipt/v1](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-eval-receipt-v1/)
- [DF-VERIFY/1 — GroundTruthReceipt Verifiable Credential profile](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-ground-truth-vc-v1/)
- [Dynamic Feed — inference-receipt/v1](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-inference-receipt-v1/)
- [DF-VERIFY/1 — intensity/v1 profile (parametric intensity-at-location)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-intensity-v1/)
- [OKF reliability object (v1 draft)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-okf-reliability-v1/)
- [DF-VERIFY/1 — proxy-witness/v1 profile (receipts for any API)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-proxy-witness-v1/)
- [DF-VERIFY/1 — receipt/v1 profile](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-receipt-v1/)
- [Dynamic Feed — robot-receipt/v1](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-robot-receipt-v1/)
- [Dynamicfeed Ai Schemas Index](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-schemas-index/)
- [DF-VERIFY/1 — station-receipt/v1 profile (We Sign Your Station)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-station-receipt-v1/)
- [DF-VERIFY/1 — trigger-receipt/v1 profile (parametric catastrophe settlement)](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-trigger-receipt-v1/)
- [Dynamic Feed Trust Receipt v1 envelope](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-trust-receipt-v1/)
- [Dynamic Feed txn-receipt/v1](https://apis.io/schemas/dynamicfeed-ai/dynamicfeed-ai-txn-receipt-v1/)

#### Overlays (69)

OpenAPI overlays, including conversational phrasing for each operation.

- [Dynamicfeed Ai Advisories Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-advisories-api-phrasing-overlay/)
- [Dynamicfeed Ai Agent Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-agent-api-phrasing-overlay/)
- [Dynamicfeed Ai Agent Stats Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-agent-stats-api-phrasing-overlay/)
- [Dynamicfeed Ai Ai Models Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-ai-models-api-phrasing-overlay/)
- [Dynamicfeed Ai Air Quality Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-air-quality-api-phrasing-overlay/)
- [Dynamicfeed Ai Airport Delays Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-airport-delays-api-phrasing-overlay/)
- [Dynamicfeed Ai Benchmarks Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-benchmarks-api-phrasing-overlay/)
- [Dynamicfeed Ai Billing Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-billing-api-phrasing-overlay/)
- [Dynamicfeed Ai Carbon Intensity Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-carbon-intensity-api-phrasing-overlay/)
- [Dynamicfeed Ai China Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-china-api-phrasing-overlay/)
- [Dynamicfeed Ai Cite Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-cite-api-phrasing-overlay/)
- [Dynamicfeed Ai Consensus Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-consensus-api-phrasing-overlay/)
- [Dynamicfeed Ai Convert Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-convert-api-phrasing-overlay/)
- [Dynamicfeed Ai Countdown Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-countdown-api-phrasing-overlay/)
- [Dynamicfeed Ai Dataset Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-dataset-api-phrasing-overlay/)
- [Dynamicfeed Ai Dev Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-dev-api-phrasing-overlay/)
- [Dynamicfeed Ai Drought Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-drought-api-phrasing-overlay/)
- [Dynamicfeed Ai Drug Shortages Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-drug-shortages-api-phrasing-overlay/)
- [Dynamicfeed Ai Dynamic Feed Live Data For Ai Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-dynamic-feed-live-data-for-ai-api-phrasing-overlay/)
- [Dynamicfeed Ai Earthquakes Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-earthquakes-api-phrasing-overlay/)
- [Dynamicfeed Ai Energy Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-energy-api-phrasing-overlay/)
- [Dynamicfeed Ai Exploited Vulnerabilities Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-exploited-vulnerabilities-api-phrasing-overlay/)
- [Dynamicfeed Ai Federal Register Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-federal-register-api-phrasing-overlay/)
- [Dynamicfeed Ai Flights Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-flights-api-phrasing-overlay/)
- [Dynamicfeed Ai Forecast Api Phrasing Overlay](https://apis.io/overlays/dynamicfeed-ai/dynamicfeed-ai-forecast-api-phrasing-overlay/)
- …and 44 more published on APIs.io

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Dynamicfeed Ai Authentication](https://apis.io/security/dynamicfeed-ai/dynamicfeed-ai-authentication/)
- [Dynamicfeed Ai Domain Security](https://apis.io/security/dynamicfeed-ai/dynamicfeed-ai-domain-security/)
- [Dynamicfeed Ai Trust Center](https://apis.io/security/dynamicfeed-ai/dynamicfeed-ai-trust-center/)
- [Dynamicfeed Ai Vulnerability Disclosure](https://apis.io/security/dynamicfeed-ai/dynamicfeed-ai-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Dynamicfeed Ai Plans Pricing](https://apis.io/plans/dynamicfeed-ai/dynamicfeed-ai-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Dynamicfeed Ai Rate Limits](https://apis.io/rate-limits/dynamicfeed-ai/dynamicfeed-ai-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://dynamicfeed.ai/)
- [Documentation](https://dynamicfeed.ai/docs)
- [Getting started](https://dynamicfeed.ai/connect)
- [API reference](https://dynamicfeed.ai/docs)
- [Pricing](https://dynamicfeed.ai/pricing)
- [Sign up](https://dynamicfeed.ai/dashboard)
- [Trust centre](https://dynamicfeed.ai/trust)
- [Terms of service](https://dynamicfeed.ai/terms)
- [Privacy policy](https://dynamicfeed.ai/privacy)
- [GitHub](https://github.com/Fluxdyne)
- [Status](https://dynamicfeed.ai/uptime)

## API Evangelist rating

**Kin Score 69.6** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 81.7 |
| Contract quality | 60.1 |
| Contract governance | 18.2 |
| Operational transparency | 71.1 |
| Developer ergonomics | 73.2 |
| Access clarity | 84.2 |

**Agent readiness 38.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | mostly |

**Regulatory alignment 43.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/dynamicfeed-ai/](https://apis.io/providers/dynamicfeed-ai/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Dynamic Feed: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/dynamicfeed-ai/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
