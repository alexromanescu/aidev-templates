---
section: conventions
stack: node
version: 9
target: CLAUDE.md
---
## Conventions

- **You are the developer; the user is not.** They will not code, debug, deploy, or test. Do all of that yourself. If a task isn't strictly human-only (judgment call, credential entry, physical-world step), generate a prompt for the agent that picks it up.
- **Write outputs for a non-developer audience.** Reports should say what works, what doesn't, and what the user can now do — not implementation detail or jargon. Strip technical mechanics unless the user asks.
- **For decisions that need a human, weigh long-term simplicity, bug-proneness, scalability.** Effort is not a factor — pay it now. Never defer an architecturally better solution for an easy patch.
- **If blocked on a mandatory step (running tests, deploys, browser checks), try to unblock yourself first.** If you can't, report the blocker precisely. Ditching the assignment is not an option.
- **Verify what's verifiable.** Check the repo, git, or tool output before asking the user. Reserve questions for preferences and decisions.
- **Design every feature for automated verification, end-to-end, with no human in the loop.** If you can't see how a test would drive the workflow and assert on the outcome, the design is wrong — restructure before implementing. Every feature, no matter how small, ships with an automated test.
- **Match existing patterns first.** Read the surrounding code before writing new code.
- **TypeScript strict mode.** No `any` without a comment. Prefer `unknown` when the type is genuinely unknown.
- **Prefer `const` over `let`; never `var`.** `let` only when reassignment is intentional.
- **`async/await` over raw Promises.** Chain `.then()` only at the outermost edge.
- **kebab-case for filenames.** Follow the codebase's existing component-file convention.
- **Named exports over default exports.**
- **Types co-located with their module,** not in a global `types.ts` dump.
- **No dead code.** Delete commented-out blocks, unused imports, unused types, orphan helpers.
- **Validate at boundaries.** Zod at API boundaries (user input, external API responses, untrusted data); trust internal calls.
- **Fail loudly in development, gracefully in production.** Never silently swallow errors you don't understand.
- **YAGNI; don't abstract prematurely.** Build only what was requested. Three similar lines are fine.
- **Worktree-aware:** when you work on a worktree, launched agents must work in the same worktree.
