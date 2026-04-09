# RNA-seq-analysis-Zebrafish-NanoPlastics-Toxicity-From-Raw-to-GSEA-Pipeline-
This project presents a comprehensive and rigorous RNA-seq analysis from Raw data to GSEA. It addresses the serious environmental pollution problem of polystyrene nanoparticle (PS-NP) contamination by analyzing its impact on the early developmental stages of zebrafish (larvae). 
From raw sequencing reads → preprocessing → quantification → differential expression → functional enrichment (GSEA).

1-Data AcquisitionSource:
NCBI Sequence Read Archive (SRA).
BioProject ID: PRJNA1175381
Dataset: 6 Samples (3 Control vs. 3 PS-NP Exposed).

📊 3. Post-QC Validation
Re-ran FastQC
Aggregated with MultiQC

✅ Confirmed improved quality
✅ Reduced technical bias

⚡ Phase II: Quantification (Pseudo-alignment)
Tool: Kallisto to estimate transcript abundance (TPM)
Reference: Danio rerio (GRCz11)


📈 Phase III: Differential Expression Analysis
Tool: DESeq2

✔️ Normalization (size factors & dispersion)
✔️ LFC Shrinkage using apeglm
✔️ Statistical filtering:

padj < 0.05
|log2FC| > 0.5

🧠 Phase IV: Functional Analysis (GSEA)
Tool: clusterProfiler
📊 Outputs:

GSEA plots
Ridge plots
Dotplots
