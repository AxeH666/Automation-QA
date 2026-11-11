# Automation & QA Developer — Take-Home Assessment

**Candidate:** Mohaddis YSM  
**Evidence date:** 10–11 November 2026

## Task 1 — Web app QA
`Task1/Task1_QA_Report_Mohaddis.pdf` contains five source-reviewed QA findings with reproduction procedures, severity, suspected causes, and root-cause analysis. **The candidate reports manually checking and observing the five issues**; no independent browser logs or video evidence of those five reproductions was supplied. The complete set of signup, login, create/edit/delete, and logout journeys is not documented separately.

## Task 2 — GitHub API → Discord digest
`Task2/Task2_Workflow_Mohaddis.json` defines an hourly trigger; GitHub repository search; top-five selection; a second API call for language breakdown; a 1,000-star IF threshold; Discord notification; and retry/continue/error logging. The Discord webhook is stored in n8n credentials, not the JSON.

**Verified manually:** a successful 3.434-second run; second API's language counts (Python/HTML/JavaScript); high-interest branch; delivered Discord digest. Four screenshots are in `Task2/Evidence/`. **Not verified:** deliberate Task 2 API failure/recovery and an automatically triggered hourly run.

## Bonus — Website uptime monitor
`Bonus/Bonus_UptimeMonitor_Mohaddis.json` checks the [RealWorld Vue demo](https://vue-vuex-realworld.netlify.app/) every five minutes *when activated*, measures response time, and alerts Discord if the status is not 200. **Verified manually:** a normal no-alert execution and a later HTTP 503 response (975 ms), routed through the True branch with a delivered Discord alert. Evidence is in `Bonus/Evidence/`. **Not verified:** a scheduled five-minute run or a failure in delivering an alert. The observed 503 was from the configured RealWorld URL, not evidence of an intentionally simulated outage.

## Submission notes
Workflow JSON files were prepared and successfully imported. The assignment also requests exports from n8n's built-in Download menu; export the live instances there if strict compliance is needed. Include a brief Loom walkthrough and share the new **public** GitHub repository URL.

The documentation distinguishes working behavior from tests not conducted. No credentials or Discord webhook URLs are embedded in these exported JSON files.
