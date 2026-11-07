# Engineering handoff

Updated: 2026-11-07
Repository: DevTunaSoft/kimi-k3-in-c-redux
Work branch: chore/autonomous-development-governance
Base: main

## Purpose
Establish persistent autonomous engineering instructions, an evidence-based handoff, and CI coverage without duplicating existing workflows.

## Verified repository observations
- README.md describes a portable C99 Kimi K3 inference engine and upstream acknowledgements.
- CMakeLists.txt exists, and its header states that the Makefile is the reference build.
- .github/workflows/ci.yml exists with Linux GCC/Clang, macOS and Windows build/test jobs.
- AGENTS.md and HANDOFF.md were absent on the default branch when checked.
- These are repository inspections, NOT proof that builds or tests currently pass.

## Changes in this work branch
- Add AGENTS.md with standing autonomous engineering rules and safeguards.
- Add HANDOFF.md as a durable checkpoint.
- Audited existing CI: CMake smoke tests, Linux/macOS/Windows builds, sanitizer jobs, strict warnings, tokenizer parity, Python lint, and shellcheck already exist. No duplicate workflow added.

## Test evidence
- GitHub repository file inspection: completed.
- Local compilation and runtime tests: NOT RUN (GitHub connector only).
- CI results for this branch: NOT YET VERIFIED. Existing CI workflows trigger on pull requests; this branch has not been merged.
- Full checkpoint inference: NOT RUN; requires model weights.

## Risks and follow-up
1. Existing CI was inspected; avoid redundant workflows. Evaluate new coverage only for documented gaps.
2. Check the current branch's CI run and fix any failure with root-cause analysis.
3. Audit README branding and attribution separately; do not remove mandatory notices.
4. Inventory tests, fuzz targets, sanitizers and platform-specific coverage before expanding.
5. Keep this handoff updated with actual commit SHAs, commands and test results; never invent them.

## Recovery
Checkout branch `chore/autonomous-development-governance`, read `AGENTS.md`, this file, and `.github/workflows/ci.yml`. Inspect the latest commits and Actions status, then resume from the first outstanding item above.
