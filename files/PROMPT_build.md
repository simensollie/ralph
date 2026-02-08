0a. Create an agent team. Spawn teammates to study `specs/*` in parallel and learn the application specifications.
0b. Study @IMPLEMENTATION_PLAN.md.
0c. Study @LESSONS_LEARNED.md.

1. Your task is to implement functionality per the specifications using an agent team. Follow @IMPLEMENTATION_PLAN.md and choose up to 5 independent items to address in parallel. Assign each task to a teammate with clear file ownership to prevent conflicts. Require plan approval before teammates implement — review and approve or reject with feedback. Before making changes, teammates must search the codebase (don't assume not implemented). Use delegate mode — coordinate, review plans, and synthesize only.
2. After teammates implement functionality or resolve problems, have one teammate run the tests for the changed code. If functionality is missing then it's their job to add it as per the application specifications. Ultrathink.
3. When you discover issues, immediately update @IMPLEMENTATION_PLAN.md with your findings. When resolved, update and remove the item.
4. Append your progress and insights to @LESSONS_LEARNED.md (never replace, always append) sorted newest to oldest.
5. When the tests pass, update @IMPLEMENTATION_PLAN.md, then `git add -A` then `git commit` with a message describing the changes. After the commit, `git push`. Clean up the team.

99999. Important: When authoring documentation, capture the why — tests and implementation importance.
999999. Important: Single sources of truth, no migrations/adapters. If tests unrelated to your work fail, resolve them as part of the increment.
9999999. As soon as there are no build or test errors create a git tag. If there are no git tags start at 0.0.0 and increment patch by 1 for example 0.0.1  if 0.0.0 does not exist.
99999999. You may add extra logging if required to debug issues.
999999999. Keep @IMPLEMENTATION_PLAN.md current with learnings — future work depends on this to avoid duplicating efforts. Update especially after finishing your turn.
9999999999. When you learn something new about how to run the application, update @AGENTS.md but keep it brief. For example if you run commands multiple times before learning the correct command then that file should be updated.
99999999999. For any bugs you notice, resolve them or document them in @IMPLEMENTATION_PLAN.md even if it is unrelated to the current piece of work.
999999999999. Implement functionality completely. Placeholders and stubs waste efforts and time redoing the same work.
9999999999999. When @IMPLEMENTATION_PLAN.md becomes large periodically clean out the items that are completed from the file.
99999999999999. If you find inconsistencies in the specs/* then use a teammate with 'ultrathink' requested to update the specs.
999999999999999. IMPORTANT: Keep @AGENTS.md operational only — status updates and progress notes belong in `IMPLEMENTATION_PLAN.md`. A bloated AGENTS.md pollutes every future loop's context.

## Lessons Learned Format

```
## [YYYY-MM-DD HH:MM] - [Feature]
- What was implemented
- Files changed
- **Learnings for future iterations:**
  - Patterns discovered (e.g., "this codebase uses X for Y")
  - Gotchas encountered (e.g., "don't forget to update Z when changing W")
  - Useful context (e.g., "the evaluation panel is in component X")
---
```

The learnings section is critical - it helps future iterations avoid repeating mistakes and understand the codebase better.

## Consolidate Patterns

If you discover a **reusable pattern** that future iterations should know, add it to the `## Codebase Patterns` section at the TOP of progress.txt (create it if it doesn't exist). This section should consolidate the most important learnings:

```
## Codebase Patterns
- Example: Use `sql<number>` template for aggregations
- Example: Always use `IF NOT EXISTS` for migrations
- Example: Export types from actions.ts for UI components
```

Only add patterns that are **general and reusable**, not story-specific details.

## Update AGENTS.md Files

Before committing, check if any edited files have learnings worth preserving in nearby AGENTS.md files:

1. **Identify directories with edited files** - Look at which directories you modified
2. **Check for existing AGENTS.md** - Look for AGENTS.md in those directories or parent directories
3. **Add valuable learnings** - If you discovered something future developers/agents should know:
   - API patterns or conventions specific to that module
   - Gotchas or non-obvious requirements
   - Dependencies between files
   - Testing approaches for that area
   - Configuration or environment requirements

**Examples of good AGENTS.md additions:**

- "When modifying X, also update Y to keep them in sync"
- "This module uses pattern Z for all API calls"
- "Tests require the dev server running on PORT 3000"
- "Field names must match the template exactly"

**Do NOT add:**

- Story-specific implementation details
- Temporary debugging notes
- Information already in progress.txt

Only update AGENTS.md if you have **genuinely reusable knowledge** that would help future work in that directory.

## Quality Requirements

- ALL commits must pass your project's quality checks (typecheck, lint, test)
- Do NOT commit broken code
- Keep changes focused and minimal
- Follow existing code patterns
