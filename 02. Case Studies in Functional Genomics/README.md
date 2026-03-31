
# PH525.6x: Case Studies in Functional Genomics

This repository documents the advanced computational methods for analyzing Next-Generation Sequencing (NGS) data, including **RNA-seq, DNA Methylation, and ChIP-seq**, as part of the PH525x series.

## Section 1: RNA-seq
This section covers the transition from raw sequencing reads to biological insights regarding gene and isoform expression.

*   **Introduction to RNA sequencing**: RNA-seq is a powerful protocol for **quantifying the types and amounts of RNA molecules** in a sample. Early foundational work in this field includes studies by Mortazavi (2008) and Marioni (2008).
*   **RNA-seq alignment**: The process involves extracting FASTQ files using the **SRA toolkit** and aligning them to a reference genome using tools like **Bowtie2, Tophat2, or STAR**. Alternatively, transcript-level alignment can be performed using **RSEM**.
*   **Normalization and EDA of gene counts**: Raw count data typically exhibits **increased variance as the expected value (mean) increases**. Exploratory Data Analysis (EDA) utilizes transformations like **rlog or Variance Stabilizing Transformation (VST)** to stabilize this variance for downstream tasks like **Principal Component Analysis (PCA)** and hierarchical clustering.
*   **Differential expression at gene-level**: Tools like **DESeq2** and **edgeR** use a **Negative Binomial distribution** to model raw counts while accounting for sequencing depth via **size factors**. This approach allows for statistically robust comparisons across biological replicates.
*   **Differential expression across isoforms**: While gene-level analysis counts reads over all exons, isoform-level analysis considers **differential exon usage** or transcript resolution. Key tools for this include **DEXSeq** for exon-level testing and **Cufflinks/cummeRbund** for visualizing isoform switching.

## Section 2: DNA Methylation
This section details the measurement and statistical analysis of epigenetic modifications.

*   **Introduction to DNA methylation**: Analysis often utilizes data from the **Illumina 450K array**, which provides methylation measurements across the genome.
*   **DNA Methylation Measurement**: Raw data is typically delivered in **IDAT files** (red and green channels), which are processed using the **minfi** package. Preprocessing includes mapping CpGs to the genome to obtain accurate methylation values and genomic locations.
*   **Data Analysis and Integration**: Initial analysis involves computing **t-statistics** for each CpG to find differences between conditions (e.g., cancer vs. normal), often visualized via **volcano plots**. Integrated objects like **SummarizedExperiment** can bundle methylation estimates with clinical metadata.
*   **Whole Genome Analysis**: Instead of looking at single points, **regional analysis** is preferred. The **bumphunter** algorithm automates the detection of differentially methylated regions (bumps) by assuming the underlying signal is smooth. Results can be explored interactively using the **epiviz** platform via the **epivizr** package.

## Section 3: ChIP-seq
This section explores the localization of protein-DNA interactions.

*   **Introduction to ChIP-seq**: ChIP-seq is used to infer the locations where **proteins are bound to DNA**. The data is characterized by **peaks** formed by aligned NGS reads.
*   **Advanced ChIP-seq Analysis**: 
    *   **Peak Calling**: Tools like **MACS** are used to identify these peaks, though different algorithms may be better suited for sharp peaks (transcription factors) versus broad peaks (modified histones).
    *   **Differential Binding**: The **DiffBind** package facilitates the comparison of peak signals across different conditions or cell lines, allowing for the normalization of sequencing depth and testing for significant binding affinity changes.
    *   **Motif Finding**: Analysis often involves searching for **common DNA sequences (motifs)** within peaks, as specific proteins prefer binding to certain DNA strings.


