# Loom walkthrough — brief screen guide

Aim for 2–3 minutes. Speak plainly, and distinguish evidence from hypotheses.

1. **Repository:** show Task1, Task2, Bonus, and README. Explain the two required tasks and optional monitor.
2. **Task 1 QA PDF:** briefly describe the five source-reviewed issues that the candidate reports checking in the browser (signup email format, missing required-field checks, missing persistent labels, repeat signup submission, and settings email format) and the root-cause analysis. Explain that the five issues were manually checked, without claiming that all six end-to-end user journeys or detailed server responses were recorded.
3. **Task 2 n8n:** show the search → top five → language enrichment → 1,000-star conditional → Discord path and the retry/error nodes. Explain why GitHub/Discord were chosen.
4. **Task 2 evidence:** show successful 3.434-second execution, language data, then Discord digest. Explain that error injection and hourly automatic firing were not independently tested.
5. **Bonus:** show seven-node uptime workflow, the no-alert execution, HTTP 503 detection/True branch, and the actual Discord uptime alert. Say the five-minute automatic trigger has not been independently observed.
6. **Close:** point to the READMEs and evidence screenshots, thank the assessor.

Avoid opening credential settings or showing webhook URLs.
