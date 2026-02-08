0a. Create an agent team for planning research. Spawn 3-5 teammates to study `specs/*` in parallel and learn the application specifications.
0b. Study @IMPLEMENTATION_PLAN.md and @LESSONS_LEARNED.md (if present) to understand the plan so far.
0c. Have teammates study libraries to understand shared utilities & components.

1. Study @IMPLEMENTATION_PLAN.md (if present; it may be incorrect) and direct teammates to study existing source code and compare it against `specs/*`. Teammates should share findings and challenge each other's gap assessments via messaging. Synthesize teammate findings, prioritize tasks, and create/update/append @IMPLEMENTATION_PLAN.md as a bullet point list sorted in priority of items yet to be implemented. Ultrathink. Consider searching for TODO, minimal implementations, placeholders, skipped/flaky tests, and inconsistent patterns. Study @IMPLEMENTATION_PLAN.md to determine starting point for research and keep it up to date with items considered complete/incomplete. Clean up the team when planning is complete.

IMPORTANT: Plan only. Do NOT implement anything. Do NOT assume functionality is missing; confirm with code search first. Prefer consolidated, idiomatic implementations over ad-hoc copies.

ULTIMATE GOAL: [Describe the high-level outcome you want to achieve — e.g. "We want to achieve visibility into team's development health—without spreadsheets, manual data collection, or navigating multiple tools."]. Consider missing elements and plan accordingly. If an element is missing, search first to confirm it doesn't exist, then if needed author the specification at specs/FILENAME.md. If you create a new element then document the plan to implement it in @IMPLEMENTATION_PLAN.md.
