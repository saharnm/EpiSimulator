# 🧬 EpiSimulator: ML-Guided Epigenomics Target Reprogramming in Cancer

EpiSimulator is an AI-assisted framework for identifying and prioritizing CpG methylation sites whose targeted epigenetic editing could shift tumor gene expression profiles toward a normal-like state.

## Overview
EpiSimulator integrates DNA methylation and gene expression data from Lung Adenocarcinoma (LUAD) patients in The Cancer Genome Atlas (TCGA) to uncover methylation sites most likely to influence transcription level. By combining statistical modeling, multi-task machine learning, and in silico methylation reversion, it ranks differentially methylated regions (DMRs) based on their predicted impact on gene expression, providing a rational foundation for epigenetic therapy target discovery.

## What It Does
EpiSimulator integrates matched tumor and normal methylation and gene expression data to:
* Differential Expression Analysis: DESeq2 (R)
* Differential Methylation Analysis: statistical comparison across tumor/normal pairs
* DMR Definition: CpG clustering and region mapping
* Predictive Modeling: Multi-task ElasticNet regression linking methylation (DMRs) to expression changes after dimensionality reduction by PCA
* Simulation: In silico reprogramming of DMRs (tumor → normal) to rank loci by expression impact

## Results
* Simulated “methylation reprogramming” effect scores to identify DMRs with strongest expression response
* List of Genes with strongest expression change after  “methylation reprogramming”

## Data Sources
`RNA-seq` and Illumina 450K `methylation array `data were downloaded from UCSC Xena public links for TCGA-LUAD:
* Methylation: "https://tcga.xenahubs.net/download/TCGA.LUAD.sampleMap/HumanMethylation450.gz"
* Expression: "https://tcga.xenahubs.net/download/TCGA.LUAD.sampleMap/HiSeqV2.gz"

## Tools and Technologies:
* Programming Languages: Python, R
* Core Libraries (Python): pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn, statsmodels, scipy
* R Packages: DESeq2, limma, edgeR, survival, ggplot2
* Machine Learning & Modeling: ElasticNetCV, MultiTaskElasticNetCV, xgboost, scikit-learn pipelines
* Data Handling: pandas, numpy, gcsfs, pyarrow, joblib
* Visualization: matplotlib, seaborn
* Platforms & Environments: Jupyter Notebook, Google Colab, Conda (local), GitHub
* Version Control: Git + GitHub for reproducible project tracking

## Usage
Execute these notebooks sequentially:
* **1_TCGA_LUAD_meth_expression_data_fetcher_processor_MVP.ipynb**: `Data loading and preprocessing`
* **2_DifferentiallyExpressedGenes_selection_byDESeq2_MVP.ipynb**: `Statistical analysis to identify DEGs`
* **3_Differentially_mathylated_CpG_selection_MVP.ipynb**: `Statistical analysis to identify  differentially methylated CpGs`
* **4_Define_DMRs_From_CpGs_MVP.ipynb**: `Grouping CpGs into DMRs`
* **5_EpiWrite_MultiTaskElasticNetCV_DMR_Simulation_MVP.ipynb**: `Machine learning modeling and tumor to normal DMR simulation`


## Use Cases
- Preclinical epigenetic therapy design
- CRISPR epigenome targeting (dCas9-TET/MeCP2)

## Contact
[Sahar Malakshah] — [saharnm@gmail.com]
