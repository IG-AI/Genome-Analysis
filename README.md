# Genome assembly and analysis of Durio zibethinus
[Genome Analysis (1MB462)](https://www.uu.se/en/admissions/freestanding-courses/course-syllabus/?kKod=1MB462&lasar=), [Uppsala University](https://www.uu.se/en) - Author: Daniel Ågstrand
##
During this project a genome de novo assembly of the Musang King cultivars of Durian, Durio zibethinus species will be performed using PacBio reads which will be corrected with shorter Illumina reads. The quality of the reads will first be assessed with FastQC and low-quality reads will be corrected and/or trimmed with the help of Canu for the PacBio long reads and with Trimmomatic for the Illumina short reads. When this is done the PacBio long reads will be used with Canu to assemble the genome and then the quality of the assembly will be assessed with help of QUAST. The Illumina short read will be used to correct the assembled genome assembled by first map those read to the genome with help of BWA and then align the mapped reads with pilon. Afterward, RNA-seq Illumina short reads from different subspecies and parts of Durio zibethinus will be mapped to the assembled genome with the software Star and then those mapped reads will be assembled into a transcriptome with Trinity. The assembled genome and transcriptome will then be used to perform an automatic structural and functional annotation with help from Maker which also will be manually curated to determine the functional regions and identify genes responsible for producing sulfur odor molecules. The gene products that will be identified as the sulfur odor molecules will later be blast against gene products from Allium cepa (onions), which is also known to produce sulfur molecules to hopefully be able to verify the annotation. A differential expression analysis will also be performed to identify how different regions and subspecies express genes. First, the RNA-Seq reads need to be mapped to the assembled genome with the software Star, then the data from this will be used in HTSeq to count the reads from the mapped genome. Last the software DESeq2 will be used to calculates the variance-mean dependence in the counted reads expressed under different conditions.
