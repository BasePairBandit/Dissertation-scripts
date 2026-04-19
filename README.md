# Dissertation Scripts-Msc Genomic medicine

This repository contains seven analysis scripts developed during my MSc research project.
The scripts were used to analyse gene expression datasets, identify differentially expressed genes, test associations between gene sets, and interpret biological pathways through enrichment analysis.

The analytical workflow integrates statistical modelling, pathway analysis, and data visualisation to identify biologically meaningful patterns in gene expression data.

## Research Overview

High-throughput transcriptomic experiments generate large gene expression datasets that require robust statistical and computational methods for interpretation.

This project aimed to:

Identify differentially expressed genes between biological conditions
Assess statistical associations between gene lists
Interpret biological meaning using pathway enrichment analysis
Reduce redundancy in pathway results through network-based clustering

The scripts in this repository support these objectives using widely adopted bioinformatics tools and statistical frameworks in R.

## **Scripts**
LIMMA Script – Differential Gene Expression Analysis

This script performs differential expression analysis using the LIMMA (Linear Models for Microarray Data) framework.

Key Steps
Reads gene expression and phenotype datasets from CSV files
Filters samples with complete phenotype data
Aligns expression and phenotype datasets by sample ID
Constructs a design matrix including:
Primary phenotype variable
Covariates such as age and BMI
Fits linear models using limma
Applies empirical Bayes moderation to improve variance estimates
Generates ranked gene results
Outputs
Differential expression results (topTable)
Log-fold change values
Adjusted p-values (FDR corrected)
CSV files containing:
All genes
Significant genes
Visualisations

The script also generates:

MA plot
Volcano plot
Annotation of the top 100 significant genes

These visualisations help interpret gene expression changes and highlight biologically relevant genes.

Fisher’s Exact Test Script – Gene List Association Analysis

This script evaluates statistical relationships between gene lists.

Function

perform_fishers_test

Method

For each pair of gene lists:

A contingency table is created
Fisher’s Exact Test is applied
A p-value is returned
Interpretation
P-value	Interpretation
< 0.05	Significant association between gene lists
≥ 0.05	No significant association (overlap likely random)

This analysis helps determine whether overlapping genes between datasets occur more frequently than expected by chance.

ClusterProfiler Script – Pathway Enrichment and Network Analysis

Gene Set Enrichment Analysis (GSEA) is used to identify biological pathways associated with differentially expressed genes.

However, enrichment analysis often produces large numbers of overlapping pathways, making interpretation difficult.

This script uses the ClusterProfiler R package to improve interpretability.

Key Features

ClusterProfiler:

Calculates similarity between pathway gene sets
Clusters related pathways
Assigns descriptive biological labels to clusters
Generates enrichment network visualisations
Analysis Performed

Four gene lists were analysed to:

Identify enriched biological pathways
Cluster related pathways
Visualise pathway interaction networks
Compare enrichment overlap across gene lists

This approach simplifies complex enrichment outputs and highlights the key biological processes associated with the experimental condition.

Technologies Used
R
LIMMA
ClusterProfiler
ggplot2
Bioconductor packages
Statistical genomics workflows
Example Outputs

The scripts generate several visual outputs commonly used in transcriptomic studies:

Volcano plots
MA plots
Enrichment network plots
Ranked differential expression tables

These outputs help identify significant genes and biologically relevant pathways.

Reproducibility

These scripts were written to support the analyses performed in the MSc dissertation project.
They may require modification for different datasets or experimental designs.

Typical inputs include:

Gene expression matrix (CSV)
Phenotype metadata (CSV)
Gene lists for enrichment analysis
