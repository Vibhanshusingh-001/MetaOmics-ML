### Quality checks using tools like FastQC and summarize quality metrics (e.g., sequence counts, per-base quality, read duplication levels)
	# command to run fastqc
	fastqc <filename.fastq> -o <output_directory>

 ### Basic statistics 
 <img width="747" height="453" alt="image" src="https://github.com/user-attachments/assets/fbc32ba1-78f0-4bad-b078-8ba07c8eace6" />

The basic statistics of a sequencing file include several important measures. The **filename** refers to the original name of the file that was analyzed. The **file type** indicates whether the file contained actual base calls or colorspace data that required conversion into base calls. The **encoding** specifies which ASCII encoding scheme was used for the quality values within the file. The **total sequences** measure provides a count of the number of sequences processed; while both actual and estimated values are reported, they are currently always the same because analyzing only a subset of sequences is disabled, as problematic sequences are not evenly distributed throughout a file. The **filtered sequences** field, applicable in Casava mode, reports the number of sequences flagged and removed from analysis; these are excluded from the total sequence count, which only reflects sequences used for further processing. The **sequence length** shows the length of the shortest and longest reads in the dataset, with a single value reported if all reads are uniform in length. Finally, **%GC** represents the overall guanine–cytosine content across all sequences, an important feature for evaluating the composition and quality of sequencing data.

### Per Base Sequence Quality
The graph in this section shows the quality scores for each base position in the sequencing reads. The quality score is shown by the y-axis, while the read’s location is represented by the x-axis. The graph’s line or bars show how the quality scores vary with the length of the reads.
![image](https://github.com/user-attachments/assets/4e121559-4399-463e-82f9-93f9c529221e)
### Sequence Duplication level
This metric reveals if specific sequences are overrepresented as a result of biases in the library preparation or sequencing process by giving insights into the degree of duplication within a sequencing dataset. Increased duplication levels may indicate that particular sequences were amplified or enriched more frequently than others during library preparation. The results of subsequent investigations, including variant calling or differential gene expression analysis, may become skewed as a result of biassed representation.
![image](https://github.com/user-attachments/assets/f8139186-d3b7-4125-a2db-a43511714464)
### Per Sequence Quality Scores
The graph in this section shows the average quality score distribution over all sequences. The number or percentage of sequences with that average quality score is shown on the y-axis, which is parallel to the x-axis and displays quality scores.
![image](https://github.com/user-attachments/assets/a8b3bf4b-2115-4327-b6f4-97dfe996e58a)
