# Task 2 — Workflow README (one page)

**Purpose.** Send an hourly digest of GitHub automation repositories to Discord, with extra context about the highest-ranked repository.

**APIs.** (1) GitHub REST search: recent, non-archived repositories tagged `automation`; (2) GitHub REST `/repos/{owner}/{repo}/languages` for the top repository. Both are public endpoints, so the example does not require API tokens (subject to rate limits).

**Transformation.** A Code node checks the search response, sorts the returned repository subset by star count, and keeps five. Another node combines the chosen repositories with the language response. An IF node routes to the high-interest Discord message when the top repo has more than 1,000 stars, otherwise to the standard/fallback message.

**Error handling.** HTTP requests are configured with retry and continued execution on error; an unavailable search/enrichment response results in a fallback/partial digest where possible. Discord nodes route notification errors to a logging node. This is configured logic; *deliberate* failure injection was not verified.

**Evidence and setup.** Manual run succeeded on 10 November 2026 in 3.434 seconds. The enrichment returned Python, HTML, and JavaScript counts, and Discord received the high-interest digest. See `Evidence/`. After import, configure **both Discord nodes** with your own `Discord Webhook account` credential in n8n. No secrets are included in JSON. Hourly auto-scheduling was not observed live.
