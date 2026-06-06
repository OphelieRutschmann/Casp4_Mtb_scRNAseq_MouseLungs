# **Caspase-4 Expression in a scRNAseq dataset of Mtb-infected Macrophages**

### **Author:** Ophélie Rutschmann 
(Work done during my PhD Project in Prof. McKinney's laboratory at the Swiss Federal Institute for Technology (EPFL))  
### **Date:** September 2023

---

## **Overview**

This repository contains the scripts to analyse Caspase-4 (Caspase-11) expression across macrophage populations in a **single-cell RNA sequencing** dataset of *Mycobacterium tuberculosis*-infected mouse lungs.

Cells are separated by infection status (**infected**, **bystander**, and **uninfected**) and differential expression is assessed within each macrophage subpopulation. The analysis also includes pathway enrichment and a quantitative breakdown of Casp4+ cell distributions across populations.

> **Data source:** Pisu D, Huang L, Narang V, et al. *Single cell analysis of M. tuberculosis phenotype and macrophage lineages in the infected lung.* J Exp Med. 2021;218(9):e20210615. doi:[10.1084/jem.20210615](https://doi.org/10.1084/jem.20210615)

---

## **Repository Structure**

```
.
├── Caspase4_Analysis.Rmd   # Main analysis notebook
├── figures/                # Output plots and visualisations
└── README.md
```
 

The input dataset (`GSE167232_mtb_integrated.RDS`) is not included in this repository. It can be downloaded directly from NCBI GEO:  
🔗 [https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE167232](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE167232)

---

## **Analysis**

### 1. Alveolar Macrophage Subpopulations (AM_1 - AM_4)
Differential expression between infected, bystander, and uninfected cells for each AM subpopulation. Casp4 is notably upregulated in **infected AM_1** cells only.

### 2. Interstitial Macrophage Subpopulations (IM_1 - IM_4)
Equivalent analysis for IM subpopulations. IM_3 has insufficient uninfected cells for full Differential Expression analysis. DotPlots are used as a complementary view.

### 3. Other Myeloid Populations
- **Neutrophils**: Casp4 is upregulated in both bystander and infected cells
- **Monocytes**: Casp4 is upregulated in both bystander and infected cells
- **Dendritic cells**: No Casp4 upregulation detected

### 4. Casp4+ vs. Casp4− Differential Expression Analysis of Infected Interstitial Macrophages
Comparison of transcriptional profiles between Casp4-expressing and non-expressing cells within the infected IM compartment, followed by GO and KEGG pathway enrichment analysis.

### 5. Percentage & Distribution Analysis
This analysis focuses on determining the following:
- Proportion of Casp4+ cells per macrophage subpopulation among infected cells
- Cell-type composition of Casp4+ bystander macrophages (pie chart)
- Split violin plots of Casp4 expression values by infection status
- UMAP visualisations and DotPlots across all three infection statuses

---

## **Requirements**

### R packages


- `Seurat`: Single-cell data handling and visualisation
- `ggplot2`: Plotting
- `patchwork` Plot composition
- `cowplot` Plot theming
- `vioplot` Split violin plots
- `dplyr` / `plyr`: Data manipulation
- `clusterProfiler`: GO and KEGG enrichment
- `enrichplot`: Enrichment visualisations
- `org.Mm.eg.db`: Mouse gene annotation
- `ggupset`: Upset plots


## **Usage**

1. Download the dataset from GEO (accession [GSE167232](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE167232)) and place `GSE167232_mtb_integrated.RDS` in the same directory as the `.Rmd` file.

2. Open `Caspase4_Analysis.Rmd` in RStudio and knit to HTML or PDF.

## **Citation**

If you use this analysis or build upon it, please cite the original dataset:

> Pisu D, Huang L, Narang V, Theriault M, Lê-Bury G, Lee B, Lakudzala AE, Mzinza DT, Mhango DV, Mitini-Nkhoma SC, Jambo KC, Singhal A, Mwandumba HC, Russell DG. Single cell analysis of M. tuberculosis phenotype and macrophage lineages in the infected lung. *J Exp Med.* 2021 Sep 6;218(9):e20210615. doi: 10.1084/jem.20210615.
