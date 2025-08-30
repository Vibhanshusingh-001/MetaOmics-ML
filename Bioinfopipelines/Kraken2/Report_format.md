
---

## **1. Sample_1: `ERR14218664.k2report`**

#### This is the *Kraken2 report file*. It summarizes how many reads were assigned to different taxonomic groups.

<img width="1903" height="889" alt="Screenshot 2025-08-30 130936" src="https://github.com/user-attachments/assets/e40855c2-9f6f-4437-a18e-16683e03f389" />

### Column meanings:

1. **% (Column 1)** → Percentage of reads assigned (including those classified at a lower level).
2. **Reads (Column 2)** → Number of reads (including those below in the hierarchy).
3. **Direct Reads (Column 3)** → Number of reads assigned **directly** to this taxon.
4. **Rank Code (Column 4)** →

   * `U` → Unclassified
   * `R` → Root
   * `D` → Domain
   * `P` → Phylum
   * `C` → Class
   * `O` → Order
   * `F` → Family
   * `G` → Genus
   * `S` → Species
   * `-` → Other ranks (strain, subspecies, etc.)
5. **NCBI Taxonomy ID (Column 5)** → Taxonomic identifier.
6. **Scientific Name (Column 6)** → Taxon name.

### Example lines:

* `61.35 1275030 1275030 U 0 unclassified`
  → 61.35% of reads could not be classified.
* `30.97 643595 897 K 3379134 Pseudomonadati`
  → 30.97% of reads mapped to the taxon *Pseudomonadati*.
* Many reads fall under **Bacteroidota**, with specific species like *Bacteroides uniformis*, *Bacteroides fragilis*, etc.

👉 This file is hierarchical — the indentation shows lineage from kingdom → phylum → class → genus → species → strain.

---

## **2. Ssample_2: `ERR14218664.kraken2.out`**

This is the **Kraken2 classification output file**, which lists the classification result for each individual read.
<img width="1914" height="888" alt="Screenshot 2025-08-30 131019" src="https://github.com/user-attachments/assets/7e17a874-f213-4a14-b33e-600b26cfd2b1" />

### Column meanings:

1. **C/U** →

   * `C` → Classified
   * `U` → Unclassified
2. **Read ID** → Identifier of the read (e.g., `ERR14218664.17.1`).
3. **NCBI TaxID** → Taxon the read was classified to (0 if unclassified).
4. **Length of sequence** → Usually 101 bp in your case.
5. **Classification mapping** → Shows how k-mers from the read mapped across taxa in the Kraken database, e.g.:

   * `816:2 0:10 816:1` → means 2 k-mers mapped to taxon 816, 10 mapped to unclassified (0), 1 mapped to taxon 816, etc.

### Example lines:

* `U ERR14218664.17.1 0 101 0:67`
  → Read unclassified, all 67 k-mers unassigned.
* `C ERR14218664.21.1 816 101 816:2 0:10 816:1`
  → Read classified, assigned to TaxID `816` (a species of *Bacteroides*).
* `C ERR14218664.23.1 375288 101 375288:5 0:35`
  → Classified to TaxID `375288`.

---

✅ **In summary**:

* The **`.k2report` file** is a **summary table** (read counts and percentages at each taxonomic rank).
* The **`.kraken2.out` file** is a **per-read classification file** (shows classification of each read and how its k-mers mapped).

Would you like me to also create a **Markdown summary table** for these two outputs (like a report format you can use in documentation)?
