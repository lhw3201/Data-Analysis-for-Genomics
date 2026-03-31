# PH525.5x: Introduction to Bioconductor

This repository contains materials and documentation related to the **PH525x series**, covering the use of Bioconductor for genomic data analysis and management.

## Course Overview

The course focuses on highly reliable and efficient methods for managing **genome-scale data**, emphasizing that customary lab practices like using spreadsheets can be risky. Key principles include the **unification of assay, sample characteristics, and experiment metadata** into formal object classes and the **endomorphic** nature of these objects when filtering features or samples.

---

## Introduction and Resources
*   **Programming prerequisites and R resources**
*   **Getting started with Bioconductor**
*   **Pre-Course Survey**

## Section 1: What We Measure, Why, and How
This section explores the technologies used to generate biomedical data.
*   **What we measure and why**: Introduction to the fundamental biological questions in genomics.
*   **Microarray technologies**: Exploration of array-based gene expression and DNA methylation measures.
*   **Next-Generation Sequencing (NGS)**: Overview of short-read sequencing technologies used for RNA-seq and other assays.

## Section 2: Bioconductor Basics with GRanges and Biostrings
Focuses on the core Bioconductor infrastructure for genomic intervals.
*   **IRanges and GRanges**: 
    *   **IRanges** define integer intervals and support **intra-range operations** and **inter-range operations**.
    *   **GRanges** extend IRanges by adding **chromosome (seqnames)** and **strand** information, which are essential for uniquely referring to DNA regions.
*   **Using GRanges for genomic analysis**: Utilizing `findOverlaps` to compare sets of genomic ranges and `mcols` to handle metadata for each range.
*   **Biostrings**: Infrastructure for efficiently handling biological sequences and specialized structures like **Views** for looking into large sequences without loading them fully into memory.

## Section 3: Management of Genome-Scale Data with Bioconductor
This module details how to organize and access large biological datasets.
*   **Organizing microarray data with ExpressionSet**: Using the `ExpressionSet` container to bundle numerical expression values (`exprs`), sample data (`pData`), and feature metadata (`fData`).
*   **Organizing NGS data with SummarizedExperiment**: Implementing a flexible container where features are identified primarily through **genomic coordinates**.
*   **Public data repositories**:
    *   **GEOquery**: For harvesting data from the NCBI Gene Expression Omnibus (GEO).
    *   **ArrayExpress**: For direct interrogation of the EMBL-EBI archive.
*   **Advanced Storage**: Utilizing **HDF5Array** for external storage of massive assay data to control memory consumption and **GenomicFiles** to manage large collections of BAM or BED files.
*   **Multiomics**: Introduction to **MultiAssayExperiment**, which unifies diverse assays (like RNA-seq and copy number variants) collected on a single cohort.

## Section 4: Genomic Annotation with Bioconductor
Covers the tools used to map genomic features to known biological information.
*   **Annotation of genes and transcripts**
*   **AnnotationHub, liftOver, and rtracklayer**: Tools for retrieving and converting genomic annotations across different builds and formats.
*   **Annotation tools for systems biology**

## Section 5: Inference for Genomics with Bioconductor
Practical applications of statistical inference in high-throughput biology.
*   **Differential expression and multiple comparisons**: Statistical methods for identifying significant changes in gene activity.
*   **Gene set analysis**: Performing inference on coordinated expression changes across biological pathways.

