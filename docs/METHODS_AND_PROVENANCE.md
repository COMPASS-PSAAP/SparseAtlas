# Methods, provenance, and interpretation

## What was reused

The figures under `figures/` are copies of existing exploratory analysis outputs. No structural distances or PCA coordinates were recomputed for this documentation package. Numeric results are preserved in `analysis/`.

## Unified structural metric

The exploratory analysis uses 62 features from 11 balanced families, excluding absolute scale features (`log_rows`, `log_cols`, `log_nnz`) from the structural distance. For each feature, values were transformed using average empirical ranks over all 1,945 matrices and the normal quantile function: `Phi^-1((rank - 0.5)/1945)`. Each feature was weighted by `1/sqrt(number of features in its family)`; distances are Euclidean in the resulting 62-dimensional space.

**This metric was refitted on all 1,945 matrices and is distinct from frozen `structural-distance-v1`.** Its PCA plot is visualization only, not the distance metric.

## Panel optimization

The original `run_analysis.py` used greedy minimization of mean nearest-panel distance and one pass of medoid-style coordinate swaps. The baseline used 30 seeded random panels at each panel size. Different sizes were refined independently. The final optimization did not implement the proposed hybrid mean/tail objective. The 0.25 GiB device-data cap does not guarantee total GPU memory usage.

## Reproducibility limitations

The original exploratory script uses local absolute paths and an input archive; it is not yet a portable repository-native workflow. For publication, parameterize inputs, pin dependencies, preserve the transformation specification, and verify regenerated outputs. The figures and tables here are descriptive artifacts, not a fully reproduced pipeline.

The package deliberately uses the **original data-derived PCA figure**. A separately generated stylistic reinterpretation was not included, because a generative illustration cannot guarantee the original coordinates, densities, or quantitative colorbar values.

## Release boundary

`releases/v1.0.0-rc1` independently passed 36/36 engineering checks, including 1,945 structural artifacts. These documentation files are separate and should not be used to overwrite the frozen release candidate.
