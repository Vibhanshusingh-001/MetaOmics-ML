
---

## 🖼️ (Sample1: `ERR14218664`)

**Command Breakdown**

<img width="1110" height="364" alt="Screenshot 2025-08-15 220249" src="https://github.com/user-attachments/assets/354c38fa-6804-4f46-8950-c532000b4811" />

**Output Summary**

* **Total sequences processed**: `2,078,436` (\~209.14 Mbp)
* **Run time**: `6801.849s` (\~1.9 hrs)
* **Processing speed**: `18.3 Kseq/min` (\~1.84 Mbp/min)
* **Classified sequences**: `803,406` (**38.65%**)
* **Unclassified sequences**: `1,275,030` (**61.35%**)

👉 **Interpretation**:
About **39% of reads matched known taxa** in the Kraken2 database, while **61% had no confident match**. This indicates either (1) many reads come from organisms not present in the reference database, (2) low-quality/ambiguous reads reduced classification.

---

## 🖼️  (Sample2: `ERR14218891`)

**Command Breakdown**

<img width="1066" height="365" alt="Screenshot 2025-08-15 220315" src="https://github.com/user-attachments/assets/0de79eea-5278-46f0-a247-bee8867bec26" />


**Output Summary**

* **Total sequences processed**: `1,633,910` (\~164.48 Mbp)
* **Run time**: `5640.289s` (\~1.6 hrs)
* **Processing speed**: `17.4 Kseq/min` (\~1.75 Mbp/min)
* **Classified sequences**: `471,825` (**28.88%**)
* **Unclassified sequences**: `1,162,085` (**71.12%**)

👉 **Interpretation**:
Here, only **\~29% of reads were classified**, with a much higher **71% unclassified**. This suggests the sample has more sequences not represented in the database (or possibly more contamination/low-quality data).

---

## 🔑 Key Comparison Between the Two Runs

| Metric                      | ERR14218664 | ERR14218891 |
| --------------------------- | ----------- | ----------- |
| Total sequences             | 2,078,436   | 1,633,910   |
| Classified %                | **38.65%**  | **28.88%**  |
| Unclassified %              | 61.35%      | 71.12%      |
| Processing speed (Kseq/min) | 18.3        | 17.4        |
| Runtime (s)                 | 6801.8      | 5640.3      |

📌 **Conclusion**:

* Sample `ERR14218664` had **better classification (39%)** compared to `ERR14218891` (29%).
* The second sample (`ERR14218891`) may contain more **novel sequences**, **low-quality reads**, or **organisms absent in the Kraken2 database**.

---

