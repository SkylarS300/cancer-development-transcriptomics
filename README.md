## Cancer–Development Transcriptomics

**Do Tumors Reuse Fetal Gene Expression Programs?**

---

### Overview

Cancer cells divide rapidly. So do cells in early development.

This project asks a simple question:

> **Do tumors “look like” fetal tissue at the gene expression level?**

To test this, we compare tumor and fetal RNA-seq data, focusing on genes involved in cell division (mitosis).

---

### Research Question

Do tumors exhibit gene expression patterns similar to those seen during fetal development?

---

### Approach (Plain Language)

- Start with real RNA-seq data from tumors (TCGA) and fetal tissues
- Focus on ~600 genes involved in cell division
- Keep only genes shared between both datasets
- Compare tumor and fetal samples in three ways:
  1. **PCA** → do they occupy similar regions overall?
  2. **Pattern matching** → which fetal tissues do tumors most resemble?
  3. Cluster analysis + marker genes → what defines tumor subtypes?

---

### Key Result 1: Global Structure (PCA)

![Joint PCA](results/figures/joint_pca_balanced.png)

After correcting for sample size differences, tumor samples cluster tightly in a small region, while fetal samples spread across a much wider space.

**Interpretation:**  
Tumors occupy a narrow and consistent expression state, while fetal development explores many different states.

---

### Key Result 2: Tissue-Level Similarity

![Fetal Matches](results/figures/top_fetal_matches_corr.png)

When comparing expression patterns directly, tumors most often resemble:

- kidney
- testis
- liver
- brain regions

**Interpretation:**  
Tumors do not match one specific fetal tissue. Instead, they resemble multiple highly active developmental contexts.

---

### Key Result 3: Tumor Subgroups

![Cluster Similarity](results/figures/cluster_fetal_similarity.png)

Clustering tumors reveals distinct groups with different fetal tissue similarities.

Some clusters are enriched for:

- liver/kidney-like patterns
- testis-like patterns
- neural-like patterns

**Interpretation:**  
Tumors are not a single state. They form **subtypes**, each resembling different developmental programs.

---

### Key Result 4: Cluster-Defining Genes

![Marker Genes](results/figures/top_marker_genes_by_cluster.png)

To understand what drives these tumor subgroups, we identified the genes that most strongly distinguish each cluster.

Each group of tumors is defined by its own set of highly expressed genes, which act as a “signature” for that subtype.

**Interpretation:**  
Tumor clusters are not just visually different—they are driven by distinct gene expression programs.

Some clusters show strong activation of cell division genes, while others show reduced or more selective expression of the same genes. This suggests that tumors exist in different regulatory states of the same underlying biological machinery.

In simple terms:

> Tumors are not all doing the same thing.  
> They are using different versions of the same cellular toolkit.

---

### Overall Interpretation

- Tumor gene expression is consistent but limited
- Fetal gene expression is diverse and context-dependent
- Tumors do not fully “revert” to fetal states
- Instead, they reuse specific subsets of developmental programs
- These programs differ across tumor subgroups and are driven by distinct gene expression signatures

---

### Limitations

- Focused only on mitotic (cell division) genes
- No direct comparison to normal adult tissue
- Results depend on chosen similarity metric (correlation distance)
- PCA captures global structure but not all relationships

---

### Project Structure

notebooks/ → analysis notebook
data/ → processed tumor + fetal data
results/ → figures and tables

---

### Status

This is an exploratory analysis aimed at understanding how cancer relates to developmental biology.

**Note:** Raw TCGA files are not included due to size constraints. The project is reconstructed from processed UCSC Xena TPM data.
