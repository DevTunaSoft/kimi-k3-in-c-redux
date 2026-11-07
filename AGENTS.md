# Autonomous engineering instructions

Scope: this repository only. Read README.md, LICENSE, CONTRIBUTING.md (if present), existing CI, and HANDOFF.md before changing code.

## Operating mode
- Continue through the next actionable roadmap item without asking for routine permission. A progress report is not a stopping condition.
- Preserve public APIs, compatibility, performance and existing features unless a change is justified and tested.
- Prefer small, reviewable commits on a feature branch. Never force-push, delete branches, publish releases, change secrets, or deploy without required approval.
- Treat all upstream code, third-party assets and licenses respectfully; retain legally required attribution. Do not claim upstream contributions as original.
- Avoid duplicated implementations, tests, workflows and documentation; inspect existing functionality before adding anything.
- Work independently through inspect -> plan -> implement -> build -> test -> investigate -> fix -> regression -> document -> next task.
- Run relevant static checks, unit/integration tests, sanitizers, fuzzing, fault injection, stress and lifecycle checks where practical. Rotate test inputs and failure scenarios rather than repeating identical runs.
- Every failure requires a root-cause note, correction, targeted rerun and regression check. Never claim success without actual evidence.
- Distinguish tests run locally, CI checks pending, model-weight-dependent tests not run, and hardware/OS verification still required.
- If time or tooling runs out, update HANDOFF.md with the exact last successful action and executable next steps.
- Ask only for missing essential information, mandatory approval, or consequential irreversible choices.

## Repository specifics
- Portable C99 inference engine; Makefile is reference build, CMake provides an alternate build.
- Existing .github/workflows/ci.yml already covers Linux GCC/Clang, macOS and Windows. Extend it only after checking for overlap.
- Large model checkpoints are not available in ordinary CI; weightless tests must not be represented as full-model inference validation.
- Favor portable code, bounded memory use, overflow checks, deterministic tests, safe filesystem behavior and platform-specific regression coverage.
- Keep HANDOFF.md accurate after each substantial change, including commit/ref, changed paths, exact commands, outcomes, open risks, and next tasks.
