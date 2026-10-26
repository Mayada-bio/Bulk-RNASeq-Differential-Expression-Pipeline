# Publication-Grade Bulk RNA-Seq & Functional Enrichment Pipeline

## 📌 Executive Summary
This repository houses an end-to-end, publication-grade bioinformatic pipeline for **Bulk RNA-Seq Differential Expression Analysis (DEA)** and **Functional Gene Ontology (GO) Enrichment**. Built using R and Bioconductor standards, the pipeline utilizes statistical shrinkage modeling via `DESeq2` & `apeglm`, coupled with `clusterProfiler` for functional annotation.

The standard benchmark dataset used is the **Human Airway Smooth Muscle Cell (ASM)** study (`airway`), evaluating transcriptional and pathway alterations following **Dexamethasone** treatment.

---

## 🔬 Scientific Methodology & Workflow

1. **Pre-processing & Low-Count Filtering:**
   - Filtered raw read counts ($\sum \text{counts} \ge 10$) to reduce false discovery rates and statistical noise.
   
2. **Quality Control (QC) & Exploratory Data Analysis:**
   - Applied **Variance Stabilizing Transformation (VST)**.
   - Built **Principal Component Analysis (PCA)** and **Sample-to-Sample Distance Heatmaps** for replicate validation.

3. **Differential Expression Analysis (DEA):**
   - Modeled read counts using Negative Binomial GLMs via `DESeq2`.
   - Applied **`apeglm` (Empirical Bayes Shrinkage)** to log2 fold changes for variance-unbiased effect sizes.
   - Statistical Thresholds: $\text{padj} < 0.05$ (Benjamini-Hochberg FDR) and $|\log_2\text{FC}| > 1.0$.

4. **Downstream Functional Enrichment (GO Analysis):**
   - Mapped significant DEGs to human ENSEMBL IDs via `org.Hs.eg.db`.
   - Performed **Gene Ontology (Biological Process - BP)** enrichment analysis using `clusterProfiler`.

---

## 📊 Key Findings & Deliverables

- **Total Human Genes Assessed:** 22,369
- **Statistically Significant DEGs ($\text{padj} < 0.05$ & $|\log_2\text{FC}| > 1$):** 696 Genes
  - **Up-regulated DEGs:** 311 Genes
  - **Down-regulated DEGs:** 385 Genes
- **Top Enriched Biological Pathways:** Regulation of actin filament-based processes, epithelial cell proliferation, and cell motility regulation.

---

## 🎨 Visualization Suite

- **Sample QC:** PCA Plot & Sample Correlation Distance Matrix.
- **Gene Expression:** Publication-grade Enhanced Volcano Plot & Top 30 DEGs Heatmap.
- **Functional Annotation:** GO Enrichment Dotplot & Barplot.

---

## 🛠️ Software Toolchain

- **Language:** R (v4.x)
- **Bioconductor Core:** `DESeq2`, `apeglm`, `airway`, `clusterProfiler`, `org.Hs.eg.db`
- **Data Visualization:** `EnhancedVolcano`, `pheatmap`, `ggplot2`, `dplyr`

---

## 👤 Author
**Mayada Mohammed Elfadil**  
*M.Sc. in Bioinformatics | Specialist in Medical Microbiology & Omics Pipelines*  
Riyadh, Saudi Arabia
