# Pikafish speedup log (auto-generated header; attempt details in ATTEMPTS section below)
Generated 2026-10-28 17:55:38 UTC. Baseline = official master e9bd14d0 built with `make build` (g++ 14.2, no PGO), per ARCH.
Equivalence per ARCH vs. that ARCH's own baseline: single-thread `go depth 14` and `16`, startpos+24 FENs, every iteration line (score/nodes/hashfull/pv) + bestmove + bench node count.
Bench: `bench 16 1 14`, 1 thread pinned, interleaved A/B, median ms. A-vs-A noise ≈ ±3%.

## Current best per ARCH (cumulative speedup vs. that ARCH's baseline, verified equivalent)

| ARCH | cumulative speedup % | build/commit |
|---|---|---|
| x86-64 | n/a yet |  |
| x86-64-sse3-popcnt | n/a yet |  |
| x86-64-ssse3 | n/a yet |  |
| x86-64-sse41-popcnt | n/a yet |  |
| x86-64-avx2 | n/a yet |  |
| x86-64-bmi2 | n/a yet |  |
| x86-64-avxvnni | n/a yet |  |
| x86-64-avx512 | n/a yet |  |
| x86-64-vnni512 | n/a yet |  |
| x86-64-avx512icl | n/a yet |  |

## Per-optimization speedup table (% vs ARCH baseline; ✓=equivalent & accepted, ✗=rejected/not equivalent, ~=no gain)

| optimization | x64 | x64-sse3-popcnt | x64-ssse3 | x64-sse41-popcnt | x64-avx2 | x64-bmi2 | x64-avxvnni | x64-avx512 | x64-vnni512 | x64-avx512icl |
|---|---|---|---|---|---|---|---|---|---|---|
| PGO (make profile-build) | +0.1 ~ | +1.5 cand | +6.5 cand(unconfirmed) | - | - | - | - | - | - | - |

## Attempt notes

