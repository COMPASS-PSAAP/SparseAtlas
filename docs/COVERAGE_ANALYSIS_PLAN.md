# Completing SparseAtlas coverage characterization

**Primary population:** all 1,945 matrices. The representative panel is secondary.

| Dimension | Existing evidence | Missing work | Intended figure |
|---|---|---|---|
| Scale and shape | NNZ, density, irregularity summaries | Dimensions, aspect ratios, joint scale/shape bins, extremes | Size–shape landscape |
| Structural diversity | 65 descriptors; PCA; marginal and joint plots | Local density, outliers, structural regimes, metric sensitivity and redundancy | Structural neighborhoods and gaps |
| Application diversity | SuiteSparse group metadata | Join kind and source; group/kind balance and concentration; structural association | Application–structure map |
| Computational diversity | 13,615 observations, seven runs, four machines | GFLOP/s and runtime distributions, CV, correctness, cross-GPU ranking and structure–performance tests | Performance portability landscape |

## Inputs needed from repository

1. Unified corpus metadata keyed by `ss_id`, including `group`, `kind`, `rows`, `cols`, `nnz`, and `canonical_sha256`.
2. Structural feature table keyed by `ss_id` (the 1,945-row, 65-feature table is already available).
3. Unified performance table with all 13,615 rows, including run identity, `gpu_name`, `algorithm`, `median_us`, `gflops`, `cv`, and correctness metrics.

Inspect `releases/v1.0.0-rc1` and its schema to establish exact filenames; do not assume paths.

## Validation requirements

- Confirm 1,945 distinct `ss_id` values in corpus metadata and feature table.
- Confirm 13,615 performance rows and seven selected run combinations; preserve repeats.
- Separate entry-weighted and unique-hash-weighted analyses (1,906 distinct canonical hashes).
- Use frozen `structural-distance-v1` when comparing with earlier expansion decisions; label the newly refitted exploratory metric separately.
- Test whether structural neighborhoods persist under changes in metric or clustering; avoid interpreting PCA clusters as ground truth.
- Analyze performance within each hardware/run setting, including dispersion, correctness, and possible contention.
- Test structural predictive value beyond NNZ, dimensions, and density; use duplicate-aware held-out evaluation.

## Claims not yet supported

- Quantified coverage of all possible sparse matrices.
- Representation of every scientific application domain.
- A globally optimal or canonical 25-matrix panel.
- Established transfer across hardware or other sparse kernels.
- Scientific quality of every timing solely because release checks passed.
