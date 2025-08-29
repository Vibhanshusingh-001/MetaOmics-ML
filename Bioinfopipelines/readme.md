

## Aim and Objective
**Aim**: To develop machine learning classifiers that accurately distinguish individuals with colorectal disease (including colorectal cancer and adenoma) from healthy controls, based on gut microbiome profiles

**Result& Metadata:** https://docs.google.com/spreadsheets/d/18WWJrcXGsIk4-389QhQFa8nPFdpFN0PTc-ahViWF3XQ/edit?usp=sharing

**📊 1. Dataset Overview:**  
- **Total Samples:** 3,741 stool metagenomes  
- **Colorectal Cancer (CRC):** 1,471 samples  
- **Adenoma:** 702 samples  
- **Controls:** 1,568 samples

**📈 Class Distribution:** 
- **Disease (CRC + Adenoma):** 58%  
- **Control:** 42%
  
# 🧬 Bioinformatics Preprocessing Pipeline

This pipeline converts raw FASTQ sequencing data into a clean, quantitative **abundance matrix (microbes × samples)** suitable for downstream microbiome and machine learning analyses.

All bioinformatics preprocessing scripts—from quality control to host decontamination and taxonomic profiling—are available in the linked repository:

---

## 📋 Overview

The pipeline includes the following key steps:

1. **Raw data quality control**  
2. **Host (human) read removal**  
3. **Taxonomic profiling**  

Each step leverages widely-used, open-source tools in the metagenomics community.

---

## 🔧 Tools & Resources

| Step | Tool | Description | Link |
|------|------|-------------|------|
| 2.1 | `fastp` | Quality control, adapter trimming, filtering | [GitHub: fastp](https://github.com/OpenGene/fastp) |
| 2.2 | `bowtie2` | Host contamination removal (align to human genome) | [GitHub: bowtie2](https://github.com/BenLangmead/bowtie2) |
| 2.3 | `Kraken2` | Taxonomic classification | [GitHub: Kraken2](https://github.com/DerrickWood/kraken2/tree/master) |
| 2.3 | `Bracken` | Abundance estimation from Kraken2 outputs | [GitHub: Bracken](https://github.com/jenniferlu717/Bracken) |


📥 **Download the Kraken2 database here:**  
👉 [https://ftp.ebi.ac.uk/pub/databases/metagenomics/mgnify_genomes/human-gut/v2.0.2/kraken2_db_uhgg_v2.0.2/](https://ftp.ebi.ac.uk/pub/databases/metagenomics/mgnify_genomes/human-gut/v2.0.2/kraken2_db_uhgg_v2.0.2/)

📖 **Reference publication:**  
Almeida A., Mitchell A. L., Boland M. et al. (2021).  
**A unified catalog of 204,938 reference genomes from the human gut microbiome**. *Nature Biotechnology*.  
🔗 [https://www.nature.com/articles/s41587-020-0603-3](https://www.nature.com/articles/s41587-020-0603-3)

---

## 🧪 Project Note

> For transparency and reproducibility, we are planning to deposit a separate script for the analysis of **each prevalence-filtered input file**. These scripts will cover preprocessing, feature selection, model training, and evaluation, and will be available **after completion of model training** in the `pipelines/` directory of this repository.

This will allow researchers and developers to easily trace, run, and reproduce the results across individual datasets.

## 📚 Reference

We are reanalyzing publicly available data from the following published study using our in-house machine learning pipelines:

**Title**: Pooled analysis of 3,741 stool metagenomes from 18 cohorts for cross-stage and strain-level reproducible microbial biomarkers of colorectal cancer 
**Journal**: *Nature Medicine*, 2025  
**DOI**: [10.1038/s41591-025-03693-9](https://www.nature.com/articles/s41591-025-03693-9)

- 🔗 [View Paper Online](https://www.nature.com/articles/s41591-025-03693-9)  
- 📄 [Download Full PDF](https://drive.google.com/file/d/18kJxAy7d0toaeW5wx4t0bc24A4dFRj6w/view?usp=sharing)  
- 📊 [Download Supplementary Metadata (XLSX)](https://static-content.springer.com/esm/art%3A10.1038%2Fs41591-025-03693-9/MediaObjects/41591_2025_3693_MOESM2_ESM.xlsx)

## 📚 Important Papers

For the papers, you can find them at the following link:  
🔗 [Google Drive Folder – NGS Training Papers](https://drive.google.com/drive/folders/1meIVNmFXHy9Qo5T83KYYJYNQk1OZzIoQ?usp=sharing)

---
## 🧪 Processing Pipeline (CRC dataset)

I would like to bring your attention to the fact that, for this training session, I will run each script one by one, following a step-by-step approach. During the process, I will handle each sample individually to ensure clarity and understanding at every stage. Later on, I will integrate all the scripts into a single automated pipeline, which will allow me to execute multiple tools simultaneously within one comprehensive script.

The reason for this approach is to help you understand the basics first. You will learn how to run each tool independently, and then how to combine them to run on a server or high-performance computing system efficiently.

---

### 🔧 Pipeline Overview

The following steps are executed in order:

1. **Activate conda environment** (`bioinfo_training`)
2. **Input check and setup**
3. **Quality control using **``
4. **Host (human) read removal using **``
5. **Taxonomic classification using **``
6. **Abundance estimation using **``
---

# 🧬 Metagenomic Data Processing Pipeline

This pipeline processes **paired-end** metagenomic sequencing data in **FASTQ** or **FASTQ.GZ** format.
---

## 🛠 Tools Overview

| Step         | Tool      | Purpose                                                   |
| ------------ | --------- | --------------------------------------------------------- |
| QC           | `fastp`   | Quality filtering, adapter trimming, and basic QC reports |
| Host Removal | `Bowtie2` | Remove host (human) reads by mapping to GRCh38            |
| Taxonomy     | `Kraken2` | Taxonomic classification using UHGG v2.0.2 database       |
| Abundance    | `Bracken` | Species-level abundance estimation                        |

---
