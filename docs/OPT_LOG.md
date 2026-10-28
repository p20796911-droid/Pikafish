# Pikafish speedup log (auto-generated header; attempt details in ATTEMPTS section below)
Generated 2026-10-28 20:14:00 UTC. Baseline = official master e9bd14d0 built with `make build` (g++ 14.2, no PGO), per ARCH.
Equivalence per ARCH vs. that ARCH's own baseline: single-thread `go depth 14` and `16`, startpos+24 FENs, every iteration line (score/nodes/hashfull/pv) + bestmove + bench node count.
Bench: `bench 16 1 14`, 1 thread pinned, interleaved A/B, median ms. A-vs-A noise ≈ ±3% (shared VM) -> nothing inside noise is marked accepted.
Status of work: see best-per-ARCH table; items marked cand are NOT accepted.

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

## Per-optimization speedup table (% vs ARCH baseline, median of 12 interleaved A/B runs; ✓=ACCEPTED: equivalent AND >3% median AND >3% paired-median AND B faster in ≥11/12 rounds; cand=candidate, equivalent but gain not confirmed above the ±3% noise floor; ~=no gain/slower; ✗=NOT equivalent)

| optimization | x64 | x64-sse3-popcnt | x64-ssse3 | x64-sse41-popcnt | x64-avx2 | x64-bmi2 | x64-avxvnni | x64-avx512 | x64-vnni512 | x64-avx512icl |
|---|---|---|---|---|---|---|---|---|---|---|
| PGO (make profile-build) | +0.1 ~ | +1.5 cand | -2.3 ~ | -1.4 ~ | +1.8 cand | +5.6 cand | +3.2 cand | +2.1 cand | -0.1 ~ | - |
| flag -O2 (instead of -O3) | - | - | - | - | +2.7 cand | -1.5 ~ | - | - | - | -0.7 ~ |
| flag -fno-unroll-loops | - | - | - | - | -5.0 ~ | -4.7 ~ | - | - | - | -3.5 ~ |
| flag -mtune=sapphirerapids | - | - | - | - | -1.3 ~ | - | - | - | - | - |
| prefetch threat row: 1 line, T0 hint | - | - | - | - | -0.1 ~ | +0.0 ~ | - | - | - | -6.2 ~ |
| prefetch threat row: 4 lines, T2 | - | - | - | - | -3.6 ~ | - | - | - | - | - |
| prefetch active threat rows in refresh: 1 line | - | - | - | - | -2.1 ~ | - | - | - | - | +1.8 cand |
| prefetch active threat rows in refresh: 4 lines | - | - | - | - | +0.8 ~ | - | - | - | - | +3.6 cand |
| prefetch active threat rows in refresh: 16 lines (full row) | - | - | - | - | -2.1 ~ | - | - | - | - | -2.0 ~ |
| prefetch PSQ rows (incremental+refresh): 4 lines | - | - | - | - | +0.2 ~ | - | - | - | - | -0.8 ~ |
| sparse propagate u64 nnz bitset + u64 pop_lsb | -9.1 ~ | -0.4 ~ | -4.3 ~ | +0.8 ~ | +2.8 cand | +1.0 cand | +3.4 cand | -6.7 ~ | +0.4 ~ | -2.1 ~ |
| prefetch PSQ rows (incremental+refresh): 16 lines | - | - | - | - | -6.8 ~ | - | - | - | - | -9.1 ~ |
| prefetch full rows: refresh threats + PSQ | - | - | - | - | -5.6 ~ | - | - | - | - | -1.8 ~ |
| sparse u64 nnz bitset (exp-bits) + PGO profile-build | -0.4 ~ | -1.2 ~ | -3.0 ~ | +7.1 cand | +1.2 cand | +5.3 cand | +7.4 cand | +2.7 cand | +3.7 cand | -2.1 ~ |

## Attempt notes

