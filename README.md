# Gene-Expression-Analysis
Gene Expression Analysis of ERBB2 Amplified Breast Cancer

This code performs gene expression analysis of ERBB2 amplified breast cancer data using DESeq2 and visualizes the results using PCA and pathway enrichment analysis.

1. Downloading and Preprocessing the Data Set

The code starts by setting up the working directory and downloading the necessary data files. The data files are then preprocessed by removing duplicates and converting gene symbols to Entrez IDs.

2. Reading and Preparing the Data

The code reads the RNA-seq, patient data, and copy number aberration data from the downloaded files. The RNA-seq data is filtered to only include samples with matching patient IDs across the three data sets.

3. Matching the RNASeq patient ids with the CNA ids and Patient Data ids

The code matches the patient IDs across the three data sets using the gsub() and intersect() functions. The matching patient IDs are then used to filter the CNA data and RNA-seq data.

4. Creating Metadata

The code creates metadata for the ERBB2 status using the ifelse() function. The metadata is then added to the DESeqDataSetFromMatrix function in the next step.

5. Data Normalization and Differential Expression using DESEQ2

The code normalizes and performs differential expression analysis using DESeq2. The DESeq pipeline normalizes the data and fits a generalized linear model to the expression data. The results of the differential expression analysis are stored in the res variable.

6. Top 10 Differentially Expressed Genes Ranked by Fold Change

The code calculates the absolute log fold change (FC) for each gene and extracts the top 10 DEGs. The DEGs are then reformatted and plotted.

7. Visualization of PCA

The code performs a PCA analysis of the normalized data and plots the results using the plotPCA() function.

8. Pathway Enrichment Analysis

The code performs pathway enrichment analysis using the enrichKEGG() function from the clusterProfiler package. The results are plotted using the barplot() function.

9. Sample clustering

To perform sample clustering, the heatmap() function from the pheatmap package is used. The sampleDists and sampleDistMatrix variables are created using the dist() and as.matrix() functions respectively.
