
 ## Sankey diagram:
 **it visualizes how sequencing reads are distributed across different taxonomic levels from kingdom to species.**
* Each colored band represents the **flow of read counts** from one taxonomic rank to the next.
* The thickness of each band is proportional to the number of reads assigned.
* Input file is .k2report(output of kraken2 tool)
* You can try out Pavian at https://fbreitwieser.shinyapps.io/pavian/.

---

### **2. Structure of the Sankey plot**

* **Left to right flow**:

  * **K (Kingdom)** → **P (Phylum)** → **F (Family)** → **G (Genus)** → **S (Species)**.
  * You can see these letters along the bottom axis.
* Each node  is a taxon at a specific level.
* Numbers near the nodes indicate the **abundance (read counts)** classified to that group.

---

### **5. Purpose of this visualization**

* To quickly identify:

  * Which **taxa dominate** the sample.
  * How reads are distributed from **high-level taxa to specific species**.
  * Possible **biological interpretation**, dominance of gut-associated bacteria (*Bacteroides*, *Faecalibacterium*, *Akkermansia*).

---
## Sankey diagram

<img width="1350" height="773" alt="Screenshot 2025-08-16 100915" src="https://github.com/user-attachments/assets/56257628-e761-4e5c-b861-cff07e76b7aa" />

## comparison of samples 
<img width="1915" height="539" alt="Screenshot 2025-08-30 140030" src="https://github.com/user-attachments/assets/17420f37-be91-4435-8121-c96a801babf0" />

## comparison of samples 
<img width="1884" height="884" alt="Screenshot 2025-08-30 140123" src="https://github.com/user-attachments/assets/bac73e88-8056-4de7-9009-f44a0cebe2b6" />
<img width="1872" height="806" alt="Screenshot 2025-08-30 140323" src="https://github.com/user-attachments/assets/a189b76e-58c9-4fbf-b602-88109194cfd8" />


