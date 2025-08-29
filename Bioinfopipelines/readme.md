# 🧬 Metagenomic Pipeline for Disease Detection

## 🎯 Aim and Objective
**Aim**: To develop machine learning classifiers that accurately distinguish individuals with colorectal disease (colorectal cancer & adenoma) from healthy controls, based on **gut microbiome profiles**.

---

## 📊 Dataset Overview
- **Total Samples:** 3,741 stool metagenomes  
- **Colorectal Cancer (CRC):** 1,471 samples  
- **Adenoma:** 702 samples  
- **Controls:** 1,568 samples  

**📈 Class Distribution:**  
- **Disease (CRC + Adenoma):** 58%  
- **Control:** 42%  

---

# 🧪 Bioinformatics Preprocessing Pipeline

This pipeline converts raw sequencing data (**FASTQ format**) into a clean, quantitative **abundance matrix (microbes × samples)** for downstream microbiome and ML analysis.  

All steps are reproducible with widely used **open-source tools**.

---

## 📋 Workflow Overview

1. **Data Retrieval (SRA RunSelector)**  
2. **Initial Quality Check (FastQC)**  
3. **Read Trimming & QC (fastp)**  
4. **Host (human) read removal (Bowtie2)**  
5. **Taxonomic Profiling (Kraken2)**  
6. **Abundance Estimation (Bracken)**  

---

## 🔧 Tools & Resources

| Step | Tool | Description | Link |
|------|------|-------------|------|
| 1 | **SRA RunSelector** | Retrieve raw sequencing data (FASTQ) from NCBI SRA; filter by study, sample type, metadata | [SRA RunSelector](https://www.ncbi.nlm.nih.gov/Traces/study/) |
| 2 | **FastQC** | Generate detailed QC reports on raw FASTQ files (per-base quality, GC content, duplication, adapters) | [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) |
| 3 | **fastp** | Adapter trimming, filtering low-quality reads, and QC summary reports | [fastp GitHub](https://github.com/OpenGene/fastp) |
| 4 | **Bowtie2** | Remove host (human) reads by aligning against reference genome (GRCh38) | [Bowtie2 GitHub](https://github.com/BenLangmead/bowtie2) |
| 5 | **Kraken2** | Fast k-mer–based taxonomic classification of metagenomic reads | [Kraken2 GitHub](https://github.com/DerrickWood/kraken2) |
| 6 | **Bracken** | Refines Kraken2 outputs to estimate species/strain-level abundance | [Bracken GitHub](https://github.com/jenniferlu717/Bracken) |

---

## 🛠 Detailed Pipeline Steps

1. **📥 Data Retrieval (SRA RunSelector)**  
   - Download raw **FASTQ files** from NCBI’s SRA.  
   - Filter by study accession, disease condition, and metadata before downloading.  

2. **🔍 Quality Check (FastQC)**  
   - Assess raw data quality:  
     - Per-base sequence quality  
     - Adapter contamination  
     - GC distribution  
   - Helps decide trimming thresholds.  

3. **✂️ Read Trimming & Filtering (fastp)**  
   - Remove adapters & low-quality bases  
   - Discard too-short reads  
   - Generate HTML reports for QC  

4. **🧑‍⚕️ Host Read Removal (Bowtie2)**  
   - Map reads to **human reference genome (GRCh38)**  
   - Discard host-matching reads  
   - Keep only microbial reads  

5. **🧬 Taxonomic Profiling (Kraken2)**  
   - Classify reads to taxa using **UHGG v2.0.2 database**  
   - Output taxonomic labels (species/strain level)  

6. **📊 Abundance Estimation (Bracken)**  
   - Adjust Kraken2 classification to provide accurate **relative abundances**  
   - Generate species × sample abundance matrix  

---

## 📚 Reference Study

**Title**: *Pooled analysis of 3,741 stool metagenomes from 18 cohorts for cross-stage and strain-level reproducible microbial biomarkers of colorectal cancer*  
**Journal**: Nature Medicine (2025)  
**DOI**: [10.1038/s41591-025-03693-9](https://www.nature.com/articles/s41591-025-03693-9)

- 🔗 [View Paper Online](https://www.nature.com/articles/s41591-025-03693-9)  
- 📄 [Full PDF](https://drive.google.com/file/d/18kJxAy7d0toaeW5wx4t0bc24A4dFRj6w/view?usp=sharing)  
- 📊 [Supplementary Metadata (XLSX)](https://static-content.springer.com/esm/art%3A10.1038%2Fs41591-025-03693-9/MediaObjects/41591_2025_3693_MOESM2_ESM.xlsx)  

---

## 🚀 Final Output
A **microbial abundance matrix** ready for machine learning modeling:
- **Rows:** Microbial taxa (species/strains)  
- **Columns:** Sample IDs  
- **Values:** Normalized relative abundance  

This matrix feeds into ML classifiers to **predict disease status (CRC vs Adenoma vs Control)**.
