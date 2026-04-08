## 🧬 Cancer–Development Transcriptomics

**Do Tumors Recapitulate Fetal Mitotic Gene Expression Programs?**

---

### Overview

This project investigates whether tumor gene expression patterns resemble those of fetal tissue, focusing on mitotic gene programs using RNA-seq data from TCGA and fetal expression datasets.

---

### Research Question

Do tumors exhibit mitotic gene expression profiles similar to those observed during fetal development?

---

### Approach

- Gene-level RNA-seq TPM data (TCGA tumors + fetal samples)
- Curated set of ~600 mitotic genes
- Alignment of shared genes across datasets
- PCA for global structure comparison
- Controlled sampling to correct for dataset imbalance
- Correlation-based distance to compare expression patterns

---

### Key Result 1: Global Structure (PCA)

![Joint PCA](results/figures/joint_pca_balanced.png)

After balancing sample sizes, tumor samples form a tight cluster within a limited region of gene expression space, while fetal samples span a much broader range.

---

### Key Result 2: Tissue-Level Similarity

![Fetal Matches](results/figures/top_fetal_matches_corr.png)

Using correlation-based distance, tumors map most frequently to fetal tissues associated with high proliferative or developmentally active contexts, including kidney, testis, liver, and neural tissues.

Rather than matching a single fetal tissue, tumors distribute across multiple developmental contexts.

---

### Interpretation

Tumor mitotic gene expression appears **highly constrained and uniform**, whereas fetal mitotic expression is **diverse and context-dependent across tissues and developmental stages**.

Together, these results suggest that tumor proliferation reflects a **restricted and heterogeneous subset of developmental programs**, rather than broadly recapitulating fetal gene expression patterns.

---

### Limitations

- Analysis restricted to mitotic genes
- No direct inclusion of normal adult tissue for comparison
- PCA captures global variance but not all transcriptional relationships
- Distance-based matching depends on feature scaling and similarity metric

---

### Project Structure

notebooks/ → main analysis notebook
data/ → fetal + TCGA processed data
results/ → figures and output tables

---

### Status

This is an exploratory analysis aimed at refining hypotheses about the relationship between cancer and developmental gene expression.

**Note:** Raw TCGA source files are not included due to file size constraints. The project is rebuilt from processed matrices derived from UCSC Xena gene-level TPM data.
