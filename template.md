---
title: "Project Report"
output: html_document
---

# Project report

* This section of the report should contain a few sentences describing the experimental setup.
* This should include information about the biological questions being asked, treatments and controls, replicates, sequencing depth and technology used, etc.

## Part 1: Raw reads summary table
* This section of the report should contain a table containing a summary of the initial FastQC run.

| **Library**    | **# of Raw Reads**   | **Sequence Length**  | **# of poor quality sequences**  | **%GC**   |
|:-----------------:|:-----------------:|:-----------------:|:-----------------:|:-----------------:|
| Experiment_A_1    | 50000000 | 150  | 0  |  50 |

## Part 2: Trimmed reads summary table
* A second QC analyses of trimmed reads goes here, be sure to include information about trimming parameters used.

| **Library**    | **# of Raw Reads**   | **Sequence Length**  | **# of poor quality sequences**  | **%GC**   |
|:-----------------:|:-----------------:|:-----------------:|:-----------------:|:-----------------:|
| Experiment_A_1    | 50000000 | 150  | 0  |  50 |

## Part 3: Read quality plots
* These are additional outputs from FastQC, images should be stored in the assets folder.
| **Library** | **Raw reads**  | **Trimmed reads** |
|:------:|:-----------:|:----------:|
| Experiment_A_1   | ![](assets/raw_reads/Experiment_A_1/per_base_quality.png) | ![](assets/trimmed_reads/Experiment_A_1/per_base_quality.png) |

## Part 4: GC content plots
* These are additional outputs from FastQC, images should be stored in the assets folder.
| **Library** | **Raw reads**  | **Trimmed reads** |
|:------:|:-----------:|:----------:|
| Experiment_A_1 | ![](assets/raw_reads/Experiment_A_1/per_sequence_gc_content.png) | ![](assets/trimmed_reads/Experiment_A_1/per_sequence_gc_content.png) |

## Part 5: Kmer content plots
* These are additional outputs from FastQC, images should be stored in the assets folder.
| **Library** | **Raw reads**  | **Trimmed reads** |
|:------:|:-----------:|:----------:|
| Experiment_A_1 | ![](assets/raw_reads/Experiment_A_1/kmer_profiles.png) | ![](assets/trimmed_reads/Experiment_A_1/kmer_profiles.png) |

## Part 6: Read QC summaryD
* A few sentences here describing the QC results -- do any libraries look particularly unusual?

## Part 7: Read alignment
* A few sentences here describing how alignments were performed.
* Include which reference was used (where it was downloaded, what version of patch #, etc.)
* Also include the software used for indexing and aligning reads, as well as parameters and flags.
* Include metrics reported by PicardTools as well as the definition of each metric.

## Part 8: Alignment summary statistics
| **LIBRARY** | **TOTAL_READS** | **READS_ALIGNED_IN_PAIRS** |
|:---:|:---:|:---:|
| Experiment_A_1 | 120000000 |  110000000 |

* LIBRARY:	The library for which statistics are reported.
* TOTAL_READS:	The total number of reads including all PF and non-PF reads. When CATEGORY equals PAIR this value will be 2x the number of clusters.
* READS_ALIGNED_IN_PAIRS:	The number of aligned reads whose mate pair was also aligned to the reference.

## Part 9: WGS summary statistics
| **LIBRARY** | **MEAN_COVERAGE** | **SD_COVERAGE** | **PCT_EXC_MAPQ** | **PCT_EXC_UNPAIRED** | **PCT_EXC_BASEQ** | **PCT_EXC_OVERLAP** | **PCT_EXC_CAPPED** | **PCT_EXC_TOTAL** |
|:-------:| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| Experiment_A_1 |  3.74 | 3.42 | 0.11  | 1.10E-04 | 7.14E-03 | 0.27 | 0.011 | 0.40 |

* LIBRARY:	The library for which statistics are reported.
* MEAN_COVERAGE:	The mean coverage in bases of the genome territory, after all filters are applied.
* SD_COVERAGE:	The standard deviation of coverage of the genome after all filters are applied.
* MEDIAN_COVERAGE:	The median coverage in bases of the genome territory, after all filters are applied.
* PCT_EXC_MAPQ:	The fraction of aligned bases that were filtered out because they were in reads with low mapping quality (default is < 20).
* PCT_EXC_DUPE:	The fraction of aligned bases that were filtered out because they were in reads marked as duplicates.
* PCT_EXC_UNPAIRED:	The fraction of aligned bases that were filtered out because they were in reads without a mapped mate pair.
* PCT_EXC_BASEQ:	The fraction of aligned bases that were filtered out because they were of low base quality (default is < 20).
* PCT_EXC_OVERLAP:	The fraction of aligned bases that were filtered out because they were the second observation from an insert with overlapping reads.
* PCT_EXC_CAPPED:	The fraction of aligned bases that were filtered out because they would have raised coverage above the capped value (default cap = 250x).
* PCT_EXC_TOTAL:	The total fraction of aligned bases excluded due to all filters.

## Part 10: Duplication statistics
| **LIBRARY**  | **READ_PAIRS_EXAMINED** | **SECONDARY_OR_SUPPLEMENTARY_RDS** | **UNMAPPED_READS**  | **PERCENT_DUPLICATION** | **ESTIMATED_LIBRARY_SIZE** |
|  :-------:  | :-------: |  :-------:  |  :-------:  |  :-------:  |  :-------:  |
| Experiment_A_1  | 59776401 | 681633 | 659975   | 0.16 | 178349158 |

* LIBRARY:	The library on which the duplicate marking was performed.
* READ_PAIRS_EXAMINED:	The number of mapped read pairs examined.
* SECONDARY_OR_SUPPLEMENTARY_RDS:	The number of reads that were either secondary or supplementary
* UNMAPPED_READS: The total number of unmapped reads examined.
* PERCENT_DUPLICATION:	The fraction of mapped sequence that is marked as duplicate.
* ESTIMATED_LIBRARY_SIZE:	The estimated number of unique molecules in the library based on PE duplication.

## Part 11: Alignment Summary
* A few sentences here summarizing the alignments -- do any of the libraries look unusual?

## Part 12: Peak calling using MACS2
* Describe the parameters used for peak calling, including which libraries were treatment and which were control.

## Part 13: Overlapping peaks
* Describe the overlapping peaks protocol used -- what command was used, which experiments were compared, etc.

## Part 14: Annotate HO1-specific peaks
* How were peaks annotated? Which file was used to create a txdb?

## Part 15: Testing for significance of peaks
* Plot the distibution of q-values across all peaks

### GroupA q-value distribution
![](assets/Experiment_A_1-log10qValue_histogram.png)

## Part 16: Peak locations in the context of genomic features
* To determine the peak locations in the context of genomic features, we used ChipSeeker `plotAnnoPie` and `plotDisttoTSS`.

### **plotAnnoPie**

![](assets/Experiment_A_1_peaks_plotAnnoPie.png)

### **plotDisttoTSS**

![](assets/Experiment_A_1_peaks_plotDistToTSS.png)

## Part 17: Distribution and width of peaks across chromosomes
* Plot histograms to get a better understanding of the distribution of peaks across chromosomes.

![](assets/peaks_per_chromosome_Experiment_A_1_specific.png)

![](assets/peak_width_per_chromosome_Experiment_A_1_specific.png)

## Part 18: Summary
* Wrap with a summary statement regarding how many peaks were detected, etc.
* Might be a good place to suggest next steps (references to chip-qPCR, pathway enrichment, etc.)
* Might also want to make a list of files that will be returned to investigator
