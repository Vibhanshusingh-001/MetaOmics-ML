# NCBI SRA Data Retrieval and FASTQ Preparation

This guide explains how to obtain raw sequencing data from the NCBI Sequence Read Archive (SRA) and transform it into FASTQ format for further bioinformatics workflows. The dataset used here belongs to BioProject **PRJEB72526**, with two example runs: `ERR14218891` and `ERR14218664`.

---

## Goal
The objective is to fetch `.sra` files for the above runs and generate compressed FASTQ files ready for downstream tasks such as **RNA-Seq analysis** or **metagenomic profiling**. The workflow is performed on a Linux machine using the **SRA Toolkit**.

---

## Requirements
- **Operating System**: Linux (Ubuntu/CentOS recommended)  
- **Tools**: `conda`, `sra-tools`  
- **Disk Space**: Large enough to hold multiple gigabytes of sequencing data  
- **Permissions**: Ability to create directories and write data  


- **Input Parameters**:
  - Output directory: `sra_data`
  - SRA IDs: `ERR14218891`, `ERR14218664`
  - FASTQ directories: `sra_data/<SRA_ID>`
  - SRA file paths: `sra_data/<SRA_ID>/<SRA_ID>.sra`

## Step-by-Step Workflow

### Step 1: Create and Activate Conda Environment

```bash
conda create -n sra python=3.8
conda activate sra
```

### Step 2: Install SRA Toolkit

I will install the SRA Toolkit using the `bioconda` channel

```bash
conda install -c bioconda sra-tools
```

### Step 3: Create Output Directory

Then create a folder to store the output name `sra_data`
```bash
mkdir -p sra_data
```

### Step 4: Download SRA Files

```bash
prefetch --output-directory sra_data ERR14218891
prefetch --output-directory sra_data ERR14218664
```

### Step 5: Create FASTQ Directories

```bash
mkdir -p sra_data/ERR14218891
mkdir -p sra_data/ERR14218664
```

### Step 6: Convert to FASTQ
 Command to `convert .sra` files into compressed FASTQ files using `fastq-dump`:

This step ensures that we generate high-quality, compressed FASTQ files from the .sra archive, suitable for downstream analysis.

```bash
fastq-dump --outdir sra_data/ERR14218891 --gzip --skip-technical --readids --read-filter pass --dumpbase --split-files --clip sra_data/ERR14218891/ERR14218891.sra

fastq-dump --outdir sra_data/ERR14218664 --gzip --skip-technical --readids --read-filter pass --dumpbase --split-files --clip sra_data/ERR14218664/ERR14218664.sra

```
**Purpose**: Convert the SRA file to FASTQ format, with options to:
- Output to `sra_data/ERR14218891`.
- Compress output files with gzip (`--gzip`).
- Skip technical reads (`--skip-technical`).
- Include read IDs (`--readids`).
- Filter passing reads (`--read-filter pass`).
- Use base calls (`--dumpbase`).
- Split paired-end reads into separate files (`--split-files`).
- Clip adapters (`--clip`).

### Step 7: Verify Outputs

```bash
ls -lh sra_data/ERR14218891/
ls -lh sra_data/ERR14218664/
```
**Purpose**: `ls -lh` List the contents of the FASTQ directory to verify the presence and size of FASTQ files, logging the output.

## Example of Output Files

Once the downloading and FASTQ conversion steps are successfully completed, your output directory will contain files similar to the ones listed below:

```
-rw-r--r-- 1 user group 1864543084 Aug  1 20:39 ERR14218891_pass_1.fastq.gz  
-rw-r--r-- 1 user group 1920189678 Aug  1 20:39 ERR14218891_pass_2.fastq.gz  
-rw-r--r-- 1 user group 2427275592 Aug  1 20:39 ERR14218891.sra  
-rw-r--r-- 1 user group 1844548218 Aug  1 20:40 ERR14218664_pass_1.fastq.gz  
-rw-r--r-- 1 user group 1891657137 Aug  1 20:41 ERR14218664_pass_2.fastq.gz  
-rw-r--r-- 1 user group 2387906889 Aug  1 20:41 ERR14218664.sra  

```

End of the workflow.

