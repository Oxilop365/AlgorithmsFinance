# AI usage (Class 3)

**Tool:** Claude Code (Anthropic), desktop app, Opus 5.5.
**Date:** 2026-11-27.

## What the AI produced

From my task description (lab slides 29–31 and the professor's focus on memory,
backward induction, larger N and parallelisation), the AI wrote the first
version of:

- the tests, written before the implementation (see `DEVLOG.md`: 203 failed
  against stubs)
- the three pricers:
  - the pure-Python reference that follows the slide pseudocode
  - the NumPy version with one vector update per date
  - the naive full tree for contrast
- the early-exercise boundary, built inside the single backward pass
- the float-range guard for S0·d^N
- data loading, calibration and the exercise check
- the measurement runner: the memory/time curve against N, and the 40 assets
  in parallel with `ProcessPoolExecutor`
- the README, `DEVLOG.md` and `REVISIONS.md`

## My decisions

*To be filled in by Maurice: which suggestions were accepted, corrected or
rejected, and why.*

- **Instructions (mine):**
  - the algorithm, the contract (at the money, written at P0, expiring at PN,
    hourly exercise)
  - the calibration (sample std dev, u = e^s, R = e^(0.04·T/N) with
    T from timestamps)
  - the focus: O(N) memory, a boundary in the same pass, a full-tree contrast,
    NumPy, multiprocessing
  - the folder layout
- **RAM limit:** I told the AI the free RAM was about 20 GB. It recorded the
  measured value in `environment.json` and extended the full-tree curve beyond
  the data length to show where the tree stops fitting.
- **Accepted / corrected / rejected:** …

## What I checked myself

- …
