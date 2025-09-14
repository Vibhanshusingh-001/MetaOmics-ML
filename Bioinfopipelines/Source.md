# Metagenomic Tutorial Resources

- **[microtable Class Documentation](https://chiliubio.github.io/microeco_tutorial/basic-class.html#microtable-class)**  
  Learn about the `microtable` class, a key component of the `microeco` package for microbiome data manipulation, analysis, and visualization.

- **[file2meco Package Documentation](https://chiliubio.github.io/microeco_tutorial/file2meco-package.html#qiime2)**  
  A guide to using the `file2meco` package for converting microbiome data formats, such as QIIME2, into a `microeco`-compatible format.

- **[file2meco GitHub Repository](https://github.com/ChiLiubio/file2meco)**  
  Access the official GitHub repository for the `file2meco` package for source code and further details.


# Machine learning
- https://github.com/GeostatsGuy/MachineLearningCourse/blob/main/2025_MLProjects/OverfitRandomForest_Dinghan_Wang.ipynb


# Phage annotation guideline
- Phage Annotation Guide: Guidelines for Assembly and High-Quality Annotation: https://www.liebertpub.com/doi/full/10.1089/phage.2021.0013


***Statistical Analysis of Microbiome Data:*** https://quadram.ac.uk/wp-content/uploads/2021/06/8.-Statistical-Analysis-of-Microbiome-Data-v1.0.pdf
- Above original link: https://quadram.ac.uk/6-shotgun-metagenomic-illumina-library-preparation/



# 🧬 Bioinformatics Tools and Resources

This document provides a categorized list of widely used bioinformatics tools, pipelines, and resources across various sequencing platforms and analysis stages. Each tool includes a short description and a link to its official GitHub repository or documentation.

---

## 🔬 Sequencing System Software

### **Illumina**
- **bcl2fastq**: Converts base call (BCL) files to FASTQ format.  
  🔗 [GitHub](https://github.com/brwnj/bcl2fastq)

- **SRA Toolkit**: Toolkit for accessing and downloading sequence data from the NCBI SRA database.  
  🔗 [Installation Guide](https://github.com/ncbi/sra-tools/wiki/02.-Installing-SRA-Toolkit)

### **PacBio**
- **SMRT Analysis**: Suite for analyzing Single Molecule, Real-Time (SMRT) sequencing data.  
  🔗 [GitHub](https://github.com/PacificBiosciences)

---

## 🧰 General Bioinformatics Tools

| Tool | Description | Link |
|------|-------------|------|
| **BWA** | Maps short reads to a reference genome | [GitHub](https://github.com/bwa-mem2/bwa-mem2) |
| **Bowtie2** | Ultrafast and memory-efficient aligner | [GitHub](https://github.com/BenLangmead/bowtie2) |
| **Samtools** | Manipulates SAM/BAM files | [GitHub](https://github.com/samtools/samtools) |
| **Picard** | Toolkit for high-throughput sequencing data | [GitHub](https://github.com/broadinstitute/picard) |
| **bedtools** | Genome arithmetic toolkit | [GitHub](https://github.com/arq5x/bedtools2) |
| **STAR** | RNA-Seq aligner | [GitHub](https://github.com/alexdobin/STAR) |
| **SPAdes** | Genome assembler for single-cell and multi-cell datasets | [GitHub](https://github.com/ablab/spades) |
| **BBMap** | Read alignment and assembly tool | [Website](https://jgi.doe.gov/data-and-tools/bbtools/) |
| **Snippy** | Variant calling and core genome alignment | [GitHub](https://github.com/tseemann/snippy) |
| **Trans-ABySS** | de novo genome assembly tool | [GitHub](https://github.com/bcgsc/transabyss) |
| **Salmon** | Alignment-free quantification of RNA-seq reads | [Docs](https://salmon.readthedocs.io/en/latest/) |
| **Subread** | RNA-Seq alignment and quantification | [Website](http://subread.sourceforge.net/) |
| **HTSeq** | Read count generation from RNA-seq data | [Docs](https://htseq.readthedocs.io/en/latest/) |
| **VEP** | Variant effect prediction tool | [Docs](https://www.ensembl.org/info/docs/tools/vep/index.html) |
| **SnpEff** | SNP and indel effect annotation | [Website](http://snpeff.sourceforge.net/) |
| **RSEM** | RNA-seq quantification using statistical modeling | [Website](http://deweylab.github.io/RSEM/) |
| **fastp** | Quality trimming and filtering of FASTQ reads | [GitHub](https://github.com/OpenGene/fastp) |
| **Trim Galore** | Trimming Illumina adapters and low-quality reads | [Website](https://www.bioinformatics.babraham.ac.uk/projects/trim_galore/) |
| **Trinity** | de novo transcriptome assembly | [GitHub](https://github.com/trinityrnaseq/trinityrnaseq) |
| **Unicycler** | Hybrid assembler for bacterial genomes | [GitHub](https://github.com/rrwick/Unicycler) |
| **Canu** | Genome assembler for noisy single-molecule reads | [GitHub](https://github.com/marbl/canu) |
| **Hisat2** | Fast and sensitive spliced alignment tool | [Docs](https://daehwankimlab.github.io/hisat2/manual/) |
| **minimap2** | Alignment tool for DNA and mRNA sequences | [GitHub](https://github.com/lh3/minimap2) |
| **FastQC** | Quality control tool for sequencing reads | [GitHub](https://github.com/golharam/FastQC) |
| **GATK** | Variant discovery toolkit from Broad Institute | [GitHub](https://github.com/broadinstitute/gatk) |

---

## 🧪 Quality Control & Visualization Tools

| Tool | Description | Link |
|------|-------------|------|
| **MultiQC** | Aggregates QC metrics into a single report | [GitHub](https://github.com/MultiQC/MultiQC) |
| **IGV** | Interactive Genomics Viewer for large datasets | [GitHub](https://github.com/igvteam/igv) |
| **FastQC** | Read quality assessment tool | [GitHub](https://github.com/golharam/FastQC) |

---

## ⚙️ Workflow / Pipeline Management

| Tool | Description | Link |
|------|-------------|------|
| **Snakemake** | Workflow management system | [GitHub](https://github.com/snakemake/snakemake) |
| **Nextflow** | Parallel and scalable workflow manager | [GitHub](https://github.com/nextflow-io/nextflow) |

---

## 🧹 Data Preprocessing

| Tool | Description | Link |
|------|-------------|------|
| **Trimmomatic** | Read trimming and filtering | [GitHub](https://github.com/usadellab/Trimmomatic) |
| **Trim Galore** | Adapter and quality trimming | [Website](https://www.bioinformatics.babraham.ac.uk/projects/trim_galore/) |
| **fastp** | All-in-one FASTQ preprocessing tool | [GitHub](https://github.com/OpenGene/fastp) |

---

## 🧬 Alignment Tools

| Tool | Description | Link |
|------|-------------|------|
| **BWA** | Short-read aligner | [GitHub](https://github.com/bwa-mem2/bwa-mem2) |
| **Bowtie2** | Efficient short-read aligner | [GitHub](https://github.com/BenLangmead/bowtie2) |
| **minimap2** | Long-read alignment tool | [GitHub](https://github.com/lh3/minimap2) |
| **Hisat2** | RNA-seq spliced aligner | [Docs](https://daehwankimlab.github.io/hisat2/manual/) |

---

## 🔍 Functional Annotation Tools

| Tool | Description | Link |
|------|-------------|------|
| **KEGG** | Pathway-based gene annotation | [Website](https://www.genome.jp/kegg/) |
| **COG** | Orthologous gene functional groups | [Summary](http://www.pdg.cnb.uam.es/cursos/Leon2002/pages/software/DatabasesListNAR2002/summary/7.html) |
| **eggNOG** | Orthologous group annotation | ❗[Link Incorrect – replace with correct source] |

---

## 🧫 Metagenomics Tools

| Tool | Description | Link |
|------|-------------|------|
| **MetagenomeSeq** | Statistical analysis of metagenomic data | [Bioconductor](https://www.bioconductor.org/packages/release/bioc/html/metagenomeSeq.html) |
| **Prodigal** | Gene prediction in metagenomes | [GitHub](https://github.com/hyattpd/Prodigal) |

---

## 📊 Microbiome Data Visualization

| Tool | Description | Link |
|------|-------------|------|
| **QIIME2** | Analysis and visualization of microbiome data | [GitHub](https://github.com/qiime2/qiime2) |

---

