# This project presents a comprehensive and rigorous RNA-seq analysis from Raw data to GSEA. It addresses the serious environmental pollution problem of polystyrene nanoparticle (PS-NP) contamination by analyzing its impact on the early developmental stages of zebrafish (larvae).

**Pipeline Flow:** Raw sequencing reads → preprocessing → quantification → differential expression → functional enrichment (GSEA).

---

## 📊 Project Metadata
* **Data Source:** NCBI Sequence Read Archive (SRA)
* **BioProject ID:** `PRJNA1175381`
* **Dataset:** 6 Samples (3 Control vs. 3 PS-NP Exposed)

---

## Step-by-Step Analysis

### Step 1: Raw Data Quality Control
* **Tools:** `FastQC` & `MultiQC`
* Initial assessment of sequencing quality, identifying adapter contamination and overrepresented sequences.

### Step 2: Read Trimming & Filtering
* **Tool:** `Trimmomatic`
* Removed Illumina adapters and filtered low-quality bases (Phred score < 20).

### Step 3: Transcript Quantification
* **Tool:** `Kallisto`
* High-speed pseudo-alignment against the *D. rerio* (GRCz11) reference transcriptome to estimate transcript abundances.

### Step 4: Differential Gene Expression (DGE)
* **Tool:** `DESeq2` (R/Bioconductor)
* Performed LFC shrinkage using the `apeglm` method for reliable effect size estimation.
* **Thresholds:** `padj < 0.05` and `|log2FC| > 0.5`.

### Step 5: Functional Genomics (GSEA)
* **Tool:** `clusterProfiler`
* Ranked genes by a custom metric for Gene Set Enrichment Analysis (GSEA) against GO Biological Processes.
* Visualized gene-concept networks (Cnetplots) to identify central "hub" regulators.
