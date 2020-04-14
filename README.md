# Genome assembly and analysis of Durio zibethinus
[Genome Analysis (1MB462)](https://www.uu.se/en/admissions/freestanding-courses/course-syllabus/?kKod=1MB462&lasar=), [Uppsala University](https://www.uu.se/en) - Author: Daniel Ågstrand

## Table of Contents
1. [Overview](#Overview)
2. [Goals](#Goals)
3. [Method](#Method)
4. [Data](#Data)
5. [Timeplan](#Timeplan)
6. [Results](#Results)
7. [Discussion](#Discussion)

## Overview
During this project a genome de novo assembly of the Musang King cultivars of Durian, Durio zibethinus species will be performed using PacBio reads which will be corrected with shorter Illumina reads. The quality of the reads will first be assessed and low quality reads will be removed with the help of Canu from the PAcBio reads and FastQC for the Illumina reads. The reads will also go through adapters trimming where the adapter sequence from the 3’-ends will be removed. When this is done the good quality PacBio long reads will be used with Canu to assemble the genome and then the quality of the assembly will be assessed by assembling the good quality, trimmed Illumina short read with the assembled PacBio genome as reference with Spades. Afterward RNA-seq Illumuna short reads from Musang King, Durio zibethinus will be assembled to perform a transcriptome assembly with Trinity1. Then the assembled genome and transcriptome will then be used to perform an automatic structural and functional annotation with the help from Maker2 which also will be manual curated to determine the functional regions and identify genes responsible for producing sulphur odor molecules. The gene products that will be identified as the sulphur odor molecules will later be blast against gene products of the Monthong cultivars of the same species and against Allium cepa (onions), which is also known to produce sulphur molecules to hopefully be able to verify the annotation. Finally a differential expression analysis will be performed to identify how different regions are expressed under different conditions with the software DESeq2 which calculates the variance-mean dependence in the counted reads expressed under different conditions.

## Goals
Durian is highly sought after fruit in many countries in east and southeast asia. It’s highly nutritious and really tasty, but it also has an odor that has been described as “pig-shit, turpentine and onions, garnished with a gym sock”. Which makes it hard or almost impossible to be introduced to the westen market. But with help of genome analysis the genes responsible for the foul smell could be identified and with help of either gene manipulate those regions so it either could be completely removed or regulated to be expressed less depending on if those genes only are responsible for the odor or if it has some other function as well. Alternative the differential expression analyses could show which conditions would produce less foul odor molecules so Durians could be grown under those conditions to produce less odor molecules. Those GMO or specially grown Durians with a less foul odor or even completely without it could then be introduced to the westen market, so people in the western world also could enjoy those tasty, highly nutritious fruits. 

## Method
### Software
| Software    | Data                         | Analyse                          |
|-------------|------------------------------|----------------------------------|
| inside Canu | PacBio reads                 | PacBio - Reads Quality Control   |
| FastQC      | Illumina reads               | Illumina - Reads Quality Control |
| Trimmomatic | Illumina reads               | Adapter trimming                 |
| Canu        | PacBio reads                 | DNA assembly                     |
| Pilon	      | PacBio reads   	             | DNA assembly correction	        |
| Trinity1    | Illumina RNA                 | Transcriptome assembly           |
| Maker2      | Eukaryotes information       | Annotation                       |
| Tophat      | Assembled Genome and Illumina RNA      | Map RNA-Seq reads to genome, differential expression |
| HTSeq       | Mapped genome	             | Counting reads mapped to genome, differential expression  |
| Deseq2      | Data from HTSeq       | Statistical analysis of HTSeq data, differential expression |
| Blastp      | Protein sequences            | Gene compersion                  |

## Data
1. PacBio long DNA reads of Musang King, Durio zibethinus from the Sequence Read Archive (SRA), NCBI
2. Illumina short DNA reads of Musang King, Durio zibethinus from the Sequence Read Archive (SRA), NCBI
3. Illumina short RNA reads of Musang King, Durio zibethinus from the Sequence Read Archive (SRA), NCBI
4. Protein sequence of sulphur producing odor molecule in Allium cepa from NCBI
5. Protein sequence of sulphur producing odor molecule of Monthong, Durio zibethinus from NCBI

### Data Structure
```
genome_analyses/
|----analyses
|    |----preprocesses
|    |    |----pacBio
|    |    |----illumina
|    |----assembly
|    |    |----pacBio
|    |    |----illumina
|    |----transcriptome_assembly
|    |----annotation
|    |----differential_expression
|    |    |----tophat
|    |    |----htseq
|    |    |----deseq2
|    |----gene compersion
|----code
|    |----PacBio-DNA-Assemble.sh
|    |----Illumina-DNA-Preprocesses.sh
|    |----Illumina-DNA-Assembly.sh
|    |----Transcriptome-Assembly.sh
|    |----Annotation.sh
|    |----Differential-Expression.sh
|    |----Gene-Compersion.sh
|----data
|    |----metadata
|    |----raw_data
|    |    |----SRR6037732_scaffold_06.fq.gzcd
|    |----trimmed_data
|    |----assemble_data
|    |----corrected_data
```

## Timeplan
| Task                                                    | Time period          | Predicted time duration |
|---------------------------------------------------------|----------------------|-------------------------|
| Collect data                                            | 30/03-20 - 05/04-20  | 7 days                  |
| Quality assessment of reads                             | 06/04-20 - 07/04-20  | 2 days                  |
| Adapters trimming                                       | 08/04-20 - 08/04-20  | 1 day                   |
| Genome assembly                                         | 13/04-20 - 19/04-20  | 7 days                  | 
| Genome assembly quality assessment                      | 20/04-20 - 26/04-20  | 7 days                  |
| Transcriptome assembly                                  | 27/04-20 - 03/05-20  | 7 days                  |
| Genome annotation                                       | 04/05-20 - 10/05-20  | 7 days                  |
| Identify and collect sulphur gene productions sequences | 11/05-20 - 14/05-20  | 4 days                  |
| Blast own identified sulphur gene productions against other species sulphur gene productions  | 15/05-20 - 17/05-20  | 3 days |
| Analyse the result and complete the report | 18/05-20 - 23/07-20  | 7 days                  |


## Results

## Discussion

