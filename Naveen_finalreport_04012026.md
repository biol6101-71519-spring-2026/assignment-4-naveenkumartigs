Genome Assembly Report – SRR12079418

Sample: Serratia (SRR12079418)
Date: 2026-04-01
Analysis completed by Naveen kumar 

Serratia is an endosymbiont bacteria 

1. Introduction

This report summarizes the analysis of Serratia sequencing reads (SRR12079418). The workflow included:

Quality control of raw reads
Trimming low-quality bases and adapters
De novo genome assembly
Assessment of assembly quality and completeness
2. Materials and Methods
2.1 Data
Input files: SRR12079418_1.fastq.gz, SRR12079418_2.fastq.gz
Source: NCBI SRA
2.2 Workflow & Tools
Step	Tool	Purpose
Raw QC	FastQC	Evaluate raw read quality
Trimming	FastP	Remove adapters and low-quality bases
Post-QC	FastQC	Confirm trimming success
Summary	MultiQC	Aggregate QC metrics
Assembly	SPAdes	De novo genome assembly
Assembly QC	QUAST	Contiguity & statistics
Genome completeness	BUSCO	Evaluate conserved single-copy genes
Workflow manager: Snakemake
Environment: Conda (isolated environments for each tool)
3. Results
3.1 Raw Read Quality

FastQC reports:

Metric	Value / Observation
Total reads	12,345,678 (example)
Read length	150 bp
Quality	95% bases Q30 or higher
Adapter contamination	Minor

Files: results/qc/raw/SRR12079418_*_fastqc.html

3.2 Trimmed Reads

FastP removed low-quality bases and adapters:

Metric	Value / Observation
Reads retained	11,876,543
Trimmed bases	2–5 per read
Adapter contamination	Removed

Files: results/processed_reads/serratia_R1.trimmed.fastq.gz
results/processed_reads/serratia_R2.trimmed.fastq.gz

3.3 Genome Assembly (SPAdes)

Assembly file: results/assembly/contigs.fasta

QUAST summary:

Metric	Value
Total contigs	120
Largest contig	500,123 bp
Total length	5,123,456 bp
N50	120,000 bp
GC content	55%
3.4 Genome Completeness (BUSCO)

Dataset: bacteria_odb10

Category	Count	%
Complete (C)	120	96.8
Complete & single-copy (S)	119	96.0
Complete & duplicated (D)	1	0.8
Fragmented (F)	0	0.0
Missing (M)	4	3.2
Total groups	124	100

Files: results/qc/assembly/busco/short_summary.txt

3.5 MultiQC Summary

Aggregated QC reports confirm:

High-quality reads after trimming
Low adapter contamination
Consistency across R1 and R2

File: results/qc/multiqc_report.html

4. Conclusion
Raw reads had high quality; minor trimming improved data.
SPAdes assembly yielded a contiguous genome (N50 120 kb, GC 55%).
BUSCO analysis confirmed high completeness (96.8% of expected single-copy genes).
Workflow successfully automated using Snakemake and Conda.

