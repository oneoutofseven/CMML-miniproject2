# Doublet Detection with scDblFinder

## 1. Project Goals

1. **Objective 1:** Evaluate the sensitivity of **scDblFinder** under different doublet rates (0.1%, 0.5%, 1%, 5%).
2. **Objective 2:** Assess the impact of doublet removal on clustering structure (ARI).
3. **Objective 3:** Benchmark **scDblFinder**, **DoubletFinder**, and **Scrublet** across real datasets.

---

## 2. Important Notes Before Running

- **Recommended to clone the repository to handle large files with Git LFS**:
  ```bash
  git clone https://github.com/oneoutofseven/CMML-miniproject2.git
  ```
- **If downloading manually**, additional files must be retrieved from **GitHub Releases(Tag)**:
  - Place `pbmc.rds` into `analysis/dataset/`
  - Place `cline-ch.rds` into `benchmark/datasets/`

- **Seurat version:**  
  scDblFinder works best with **Seurat v4.4.0**.  
  Install with:
  ```r
  remove.packages(c("Seurat", "SeuratObject"))
  install.packages('Seurat', repos = c('https://satijalab.r-universe.dev'))
  packageVersion("Seurat") # Should be ‘4.4.0’
  ```

---

## 3. Running the Code

### 3.1 Main Analysis (PBMC Dataset)

- Open and run **`analysis/scDblFinder.Rmd`**
- This will perform:
  - Data preprocessing (QC, normalization, PCA)
  - scDblFinder doublet detection
  - 3D PCA visualization
  - ROC curve evaluation using SNP-labeled dataset
  - Simulation benchmarks (Precision/Recall/F1)
  - Clustering impact analysis

### 3.2 Benchmarking (Real Dataset Comparison)

- **Important:**  
  Normally, you should run **`benchmark/benchmark.Rmd`** to generate the benchmark results and then run **`benchmark/benchmark_figure.Rmd`**.  
  However, since this step is very time-consuming (~2 hours), the generated results (`benchmark.results.rds`) have already been provided.

- **What to do:**  
  Simply run **`benchmark/benchmark_figure.Rmd`** to load the provided results and plot the benchmark figures.

- **Summary:**
  - `benchmark/benchmark.Rmd`: ⚡ Full benchmarking (already done, result provided)
  - `benchmark/benchmark.results.rds`: 📄 Pre-computed benchmark results
  - `benchmark/benchmark_figure.Rmd`: 📈 Plot benchmark figures directly

---

## 4. Summary of Files

| File | Description | Notes |
|:-----|:------------|:------|
| `analysis/scDblFinder.Rmd` | PBMC data analysis and simulations | **Must run** |
| `benchmark/benchmark.Rmd` | Full benchmarking on four datasets | ⚠️ Optional (very slow) |
| `benchmark/benchmark_figure.Rmd` | Plot benchmark results | **Recommended** |

---

## 5. References

Germain, P.-L. et al. (2021) ‘Doublet identification in single-cell sequencing data using scDblFinder’, F1000Research, 10, p. 979. Available at: https://doi.org/10.12688/f1000research.73600.2.

