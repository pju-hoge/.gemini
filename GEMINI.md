# Global Engineering Guidelines

## Planning Phase
When planning for an engineering task, always:
- Refer to ~/LEARNINGS.md to review past experiences and avoid repeating mistakes.
- Incorporate relevant lessons learned into your current strategy.

## Wrapping Up Phase
Upon completing an engineering task, always:
- Perform a project-specific look-back and document it in project-summary.md within the project root.
- Identify 3 project-agnostic key takeaways and append them to ~/LEARNINGS.md for future reference.

## Fork Synchronization
When working on a fork of a repository, always ensure that it is synchronized with the upstream source before starting any new development work.
- Use gh repo view --json parent to identify the original repository.
- If an upstream remote is not configured, add it (e.g., git remote add upstream <url>).
- Fetch the latest changes from upstream and merge or rebase the target branch (usually main or master) into your local branch to ensure you are building on the most recent code.

## Validation & Testing
- **Continuous Validation:** After modifying any code, you MUST run relevant tests to verify your changes and ensure no regressions. Never assume a change is too small to break things.

## PR Hygiene & Scope Control
- **PR Isolation:** Always create new feature/fix branches from the latest clean upstream state (e.g., upstream/main) to ensure each PR contains ONLY relevant commits.
- **Strict Scope:** Revert all out-of-scope changes before submitting a PR. Do NOT include unrelated formatting, version bumps, or local environment files.

## Resource & Concurrency Management
- **Concurrency Control:** Never fire unbounded parallel requests to external APIs or heavy resources. Always implement a concurrency limit (e.g., chunking or queueing) to ensure system stability.
- **Defensive Limits:** Solve performance or limit issues through architectural improvements (like batching) rather than simply increasing arbitrary timeout or round limits.

## Code Quality & Type Safety
- **Database Efficiency:** Prioritize bulk operations (e.g., WHERE IN (...)) over row-by-row processing in loops for better performance.
- **Strict Validation:** Avoid permissive fallbacks (like any types). Throw explicit errors for unsupported configurations or types to catch issues early.
