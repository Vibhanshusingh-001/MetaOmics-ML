
### Sample_1 (ERR14218891):
<img width="1912" height="582" alt="Screenshot 2025-08-16 092652" src="https://github.com/user-attachments/assets/606b8e39-2c05-4ef6-9910-124088d9b812" />

- **Summary**:
  - Threshold: 10
  - Number of species with reads > threshold: 230
  - Number of species with reads < threshold: 810
  - Total reads kept at species level (reads > threshold): 28,125
  - Total reads discarded (species reads < threshold): 1,510
  - Reads not distributed (e.g., no species above threshold): 384
  - Unclassified reads: 116,208

### Sample_2 (ERR14218664):
<img width="1899" height="578" alt="Screenshot 2025-08-16 092714" src="https://github.com/user-attachments/assets/7a357ac5-5338-4876-ad97-213b0aa40789" />

- **Summary**:
  - Threshold: 10
  - Number of species with reads > threshold: 188
  - Number of species with reads < threshold: 554
  - Total reads kept at species level (reads > threshold): 40,018
  - Total reads discarded (species reads < threshold): 1,079
  - Reads not distributed (e.g., no species above threshold): 279
  - Unclassified reads: 127,530

### Key Observations:
- Both runs used a read length of 100 (-r 100) and species-level analysis (-l S) with a threshold of 10 reads.
- The second dataset (ERR14218664) had more total reads kept (40,018 vs. 28,125) and fewer discarded reads (1,079 vs. 1,510), indicating a higher proportion of meaningful classifications.
- Unclassified reads are significant in both cases, suggesting a substantial portion of the data could not be assigned to known species.

Based on the Bracken analysis:

| **Metric**                   | **ERR14218891** | **ERR14218664** |
|------------------------------|-----------------|-----------------|
| Threshold                    | 10              | 10              |
| Species with reads > threshold | 230             | 188             |
| Species with reads < threshold | 810             | 554             |
| Total reads kept (reads > threshold) | 28,125       | 40,018          |
| Total reads discarded (reads < threshold) | 1,510     | 1,079           |
| Reads not distributed        | 384             | 279             |
| Unclassified reads           | 116,208         | 127,530         |

## output 
<img width="1912" height="892" alt="image" src="https://github.com/user-attachments/assets/675a8c55-c267-453e-ab2f-ca06de75fb0e" />

## output 
<img width="1912" height="893" alt="image" src="https://github.com/user-attachments/assets/7604b26b-5807-4217-ac1b-170e00c049f5" />

## Interpreatation 
1. **Percentage**: The percentage of reads assigned to the given taxon.
2. **Number of Reads**: The absolute number of reads assigned to the taxon.
3. **Taxonomic Rank**: A single-letter code indicating the taxonomic level (e.g., R = root, K = kingdom, P = phylum, C = class, O = order, F = family, G = genus, S = species).
4. **Taxon Name**: The scientific name of the taxon.
## Command to merge braken outputs
```bash
python ../combine_bracken_outuptu.py --files  *out -o combined_otu_data.tsv
