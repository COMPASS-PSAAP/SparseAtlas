# SparseAtlas

**A structurally characterized sparse-matrix corpus for reproducible computational performance research.**

SparseAtlas is an open research project developing a curated and computationally characterized collection of sparse matrices. Its goal is to help researchers understand how sparse-matrix structure influences computational behavior across hardware architectures, algorithms, and scientific workloads.

Sparse matrices with similar dimensions, densities, and numbers of nonzeros can exhibit dramatically different computational performance. Conventional matrix metadata often fails to capture the structural characteristics responsible for these differences.

SparseAtlas aims to bridge that gap by connecting real-world sparse matrices with reproducible structural representations and, ultimately, measured computational performance.

## Core Components

SparseAtlas builds upon existing matrix collections, initially the [SuiteSparse Matrix Collection](https://sparse.tamu.edu/), rather than replacing them.

While existing collections provide matrices and their associated metadata, SparseAtlas focuses on **characterizing their computational structure and behavior**.

The project includes the following components:

- **Curated and validated matrices:** Reproducible matrix selection, canonicalization, provenance tracking, and integrity verification.
- **Structural characterization:** Multiresolution representations capturing sparsity patterns, spatial distributions, and other properties that conventional scalar descriptors may miss.
- **Structural similarity and coverage:** Quantitative methods for identifying related matrices, selecting representative benchmarks, and evaluating the diversity of a corpus.
- **Computational performance:** A developing framework for associating matrix structure with measurements across GPUs, sparse kernels, algorithms, and software environments.

These components are intended to support reproducible benchmarking, performance modeling, algorithm selection, and cross-platform performance analysis.

## Research Opportunities

SparseAtlas is designed to support questions such as:

- Which structural properties of sparse matrices are most predictive of computational performance?
- How can we select small but structurally representative benchmark suites?
- Do sparse matrices with similar structures exhibit similar performance across different GPUs?
- Can structural representations learned for one sparse kernel transfer to other kernels?
- How well do existing sparse-matrix collections cover the diversity of computational structures encountered in scientific applications?

An important principle of this project is that **the number of matrices in a benchmark is not necessarily a measure of its structural diversity**.

## Current Development

SparseAtlas is under active development.

The initial corpus contains **1,743 validated and structurally characterized matrices** derived from SuiteSparse. We are expanding this corpus to cover larger and potentially underrepresented structural regimes.

Current work focuses on reproducible canonicalization, deterministic multiresolution representations, structural similarity metrics, and systematic corpus coverage analysis.

SparseAtlas characterizes matrices using distributions of nonzeros across rows and columns, diagonal structure, and multiresolution spatial statistics. These descriptors capture differences in concentration, irregularity, and sparsity-pattern organization that are not apparent from conventional matrix dimensions and density alone. The structural similarity space balances these feature families and separates structural characteristics from absolute matrix size.

GPU SpMV benchmarking is the first planned computational-performance layer. Future development will extend the resource across additional hardware architectures and kernels.

## Project Organization

SparseAtlas is being developed as an independent research resource alongside **Struct2Perf**, a complementary project investigating learned sparse-matrix representations for computational performance modeling.

SparseAtlas provides the datasets, structural characterizations, and benchmark measurements. Struct2Perf develops and evaluates models that use those representations to understand and predict computational behavior.

## Availability

The corpus construction and benchmarking pipelines are being prepared for public distribution.

Future releases will include versioned metadata, structural representations, reproducible processing tools, benchmark protocols, and performance measurements. Large source matrices will generally remain available through their original collections.

**Status:** Research and development. The first public dataset release is forthcoming.

## Acknowledgments

SparseAtlas builds upon the [SuiteSparse Matrix Collection](https://sparse.tamu.edu/) and the contributions of the scientific computing community that has developed and shared sparse-matrix datasets.

## Citation

Citation information and an archival DOI will be provided with the first public release.
