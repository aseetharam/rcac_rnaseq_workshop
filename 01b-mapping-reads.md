---
source: Rmd
title: Mapping reads to a reference genome
teaching: 15
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can we map raw reads to a reference genome?
- What programs are available for mapping reads to a reference genome?
- What opitons and parameters need to be considered when mapping?
- How do to access the mapping results?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand the process of mapping raw reads to a reference genome.
- Fine tune the mapping process by adjusting parameters.
- Access the mapping results.

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

In this episode, we will learn how to map raw reads to a reference genome. Mapping is the process of aligning short reads to a reference genome. The goal of mapping is to determine the location of the reads in the reference genome. We will use the RNA-seq data that we downloaded (soft-linked) in the previous episode and map them to the reference genome using the STAR aligner. STAR is a fast and accurate RNA-seq aligner that can align reads to the reference genome with high sensitivity and specificity.



:::::::::::::::::::::::::::::::::::::::  prereq

## What mapping programs should I use?

One major requirement for a suitable RNAseq mapping program is that it should be splice-aware. This means the program must be able to handle reads that span exon-exon junctions, which is crucial for RNAseq data since the reads are derived from spliced transcripts. `STAR` is a widely used splice-aware aligner for RNAseq, known for its speed and accuracy when mapping reads to a reference genome. Other popular RNAseq aligners include `HISAT2` and, for certain applications, `Bowtie2`. It’s important not to use DNA aligners like `BWA`, which are not designed to handle spliced reads.

:::::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::  prereq

## How does read quality affect alignment performance?

The quality of the reads can have a significant impact on the alignment performance and thus your downstream analysis. 

- Uneven Read Quality: poor quality of the reads can result in partial alignments or truncated read mapping, leaving you with large portions of the read unmapped.
- Overrepresented Sequences: such as ribosomal RNA, or microbial contamination, can lead to too many multi-mapped reads.
- Poor library preparation: can result in RNAseq reads that consist primarily of adapter sequences without any actual biological content - this can result in too many unmapped reads.
- Short Reads from Over-trimming: an shorten reads to the point where they are too short to align uniquely, leading to either multimapping or unmapped reads.

It is crucial to check the quality of the reads before mapping and also alignment statistics after mapping.

:::::::::::::::::::::::::::::::::::::::


## Structuring your working directory


:::::::::::::::::::::::::::::::::::::::  challenge

## Create the directories for subsequent episodes


::::::::::::::::::::::::::::::::::: solution


:::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::

## Using RStudio project to manage your working directory


## Download the RNA-seq data for subsequent episodes


:::::::::::::::::::::::::::::::::::::::  challenge

## Download the remaining data set files


:::::::::::::::::::::::::::::::::::::  solution


:::::::::::::::::::::::::::::::::::::


:::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 


::::::::::::::::::::::::::::::::::::::::::::::::

