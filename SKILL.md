---
name: im-not-the-only-one
description: Enforce a strict Search-Think-Do workflow before starting new projects, choosing architectures, or debugging unexpected errors. Always search online for the current State of the Art (SOTA) before building, and search upstream bug trackers/forums for known issues instead of blind trial-and-error debugging.
---
# I'm Not the Only One (Search-Think-Do)

> "You may say I'm a dreamer, but I'm not the only one." — John Lennon, *Imagine*

Follow a disciplined three-phase workflow (**Search -> Think -> Do**) whenever starting a new project, selecting libraries/architectures, or encountering unexpected errors. Never rely solely on stale training-cutoff assumptions or waste time in blind trial-and-error loops.

## When to Use

- Starting a new project, designing a system architecture, or selecting libraries, frameworks, models, or protocols.
- Implementing a complex feature where modern tools or state-of-the-art (SOTA) approaches may have evolved.
- Encountering an unexpected build failure, runtime error, hardware/driver quirk, or silent malfunction that is not an obvious local typo.

## Core Workflow

### Phase 1: SEARCH (Look Upstream First)

Before writing boilerplate code or guessing workarounds, search online for current real-world evidence.

#### Scenario A: New Project / Feature / Architecture Selection

1. **Query the State of the Art:** Search for current best practices, recent benchmarks, and actively maintained libraries or models for the target domain.
2. **Check Maintenance & Compatibility:** Verify whether candidate tools are actively maintained, deprecated, or superseded by newer standards, and check compatibility with the target OS, hardware, or toolchain.
3. **Avoid Reinventing the Wheel:** Look for existing production-grade implementations or official reference designs before writing custom infrastructure from scratch.

#### Scenario B: Unexpected Error / Obscure Bug

1. **Stop Blind Trial-and-Error:** Do not chain multiple speculative edits or random config tweaks hoping the error disappears. If the first obvious check fails, pause and search.
2. **Search Exact Error Signatures:** Extract the exact error message, return code, symbol name, and tool/library/kernel version. Search upstream sources (GitHub Issues, mailing lists, release notes, vendor forums, Stack Overflow).
3. **Identify Known Bugs & Regressions:** Check whether the failure is a documented upstream bug, a breaking change in a specific version, a platform/architecture limitation, or a known missing dependency.

### Phase 2: THINK (Synthesize & Propose)

Analyze the findings from Phase 1 before executing major changes.

#### Scenario A: New Project / Feature

1. **Compare Options Concisely:** Present the user with a brief comparison of the current State of the Art:
   - **Recommended SOTA Choice:** Why it leads in performance, ergonomics, or ecosystem support.
   - **Battle-Tested Alternative:** When a more conservative or lightweight option makes sense.
   - **What to Avoid:** Legacy or deprecated tools that should no longer be used.
2. **Align with Constraints:** Match the proposal to the user's specific environment (e.g., hardware resources, language standard, deployment target) and confirm direction when architectural trade-offs exist.

#### Scenario B: Unexpected Error

1. **Correlate Root Cause:** Match the upstream bug report or documentation to the local environment (versions, flags, OS/hardware).
2. **Select the Cleanest Fix:** Prefer official fixes, version upgrades/pins, or documented upstream workarounds over brittle local hacks.

### Phase 3: DO (Execute with Evidence)

1. **Implement Cleanly:** Write the code, configuration, or fix based on the validated design or upstream resolution.
2. **Cite Evidence:** Briefly reference the SOTA comparison, official documentation, or upstream issue/bug report that informed the decision so the user knows the rationale is grounded in verified facts.

## Gotchas

- **Stale Training Priors:** Popular libraries, AI models, and build practices change rapidly. Always verify the current ecosystem state via search before recommending a stack.
- **Symptom Masking:** In debugging, suppressing warnings or adding arbitrary sleeps/retries hides the real issue. Search for the root cause first.
- **Over-Searching Trivial Tasks:** Do not run web searches for basic syntax, standard library calls, or obvious one-line typos where the cause is immediately visible in the local code.
