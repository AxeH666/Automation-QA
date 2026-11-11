# Bonus — Uptime Monitor

**Target:** https://vue-vuex-realworld.netlify.app/ (the web app referenced in Task 1).  
**Trigger:** configured every 5 minutes when the workflow is published and n8n is running.  
**Check:** GET the target, capture the HTTP status, calculate elapsed milliseconds including retries, and compare with HTTP 200.  
**Alert:** send a Discord webhook message for any non-200 status; route Discord delivery errors to a logging node.

**Manual evidence, 11 November 2026:**
1. The monitor completed a no-alert run (screenshot 02).
2. A later run observed `503 Service Unavailable` from the configured URL, measured 975 ms, and set `healthy=false` (screenshot 03).
3. The IF node chose its True branch (screenshot 04), and Discord received the alert (screenshot 05).

**Limits:** The five-minute scheduled cadence and failure-to-deliver handling have not been demonstrated. The 503 screenshot records the observed response; it is not proof that the outage was intentionally induced. The webpage may continue returning 503; consider keeping scheduled alerts off until ready.

**Import:** Add the JSON to n8n, assign an existing `Discord Webhook account` credential, and save. Do not commit credential values.
