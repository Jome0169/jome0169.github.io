---
layout: post
title:  "Running Peakranger Bcp"
date:   2018-01-19 9:00 -0600
category: Old Postings
share: false
image:
---

So, I was interestd in running the software peakranger bcp recently, but
stumbeled into a rather irritating probelm. I kept getting the classic message
`Segmentation fault (core dumped)`. Upon looking around for the solution to
this problem I found nothing. So I thought I would document briefly what I did
to fix it.

### Initial Output
```
program version:          1.18
Data files:
 File format:             bam
 Sample file:             chip_rep1_BWA.sorted.bam
 Control file:            input_rep1_BWA.sorted.bam
Qualities:
 P value cut off:         0.0001
 sliding window size:     500
 Read extension length:   200
Output:
 Regions:                 test_region.bed
 HTML reports:            Disabled(--report not specified)

Reads statistics:

 Treatment reads +:       12002431
 Treatment reads -:       11987889
 Average read length:     30
 Control reads +:         11301505
 Control reads -:         11298535
 Average read length:     30
 Verifying reads...
Warning: B73V4_ctg162 only contains reads in the positive strand. The chromosome is removed.
Warning: B73V4_ctg162 only contains reads in the positive strand. The chromosome is removed.

Reads statistics after correction:

 Treatment reads +:       12002424
 Treatment reads -:       11987889
 Control reads +:         11301503
 Control reads -:         11298535

 Calling peaks...

Segmentation fault (core dumped)
```

Upon investigating this further, I decided to see if the issue was coming from the scaffold reported in the error, B73V4_ctg162. To see check this I first analysed how many reads were aligning to this contig in the maize genome using  using a quick samtools command: 

```
#Command:
samtools idxstats chip_B73_ear_H3K36me3_rep1_bowtie2algn.sorted.bam | grep B73V4_ctg162

#Output:
B73V4_ctg162    40634   0       0
```

So, there were ZERO reads aligning to this contig. Making me think the software might be chocking on this scaffold. But after removing this scaffold from the SAM file, I was still being greated by `Segmentation fault (core dumped)` . So, in order to try again I took a more drastic measure removed all scaffolds that had CTG in them. I did this after checking the gff3 file for all scaffolds/contigs, and coming to the conclusion that none of them are particularly gene rich and/or interesting for my questions. I removed ALL of these scaffolds using the following command:

```
grep -v "B73V4_ctg*" chip_rep1_bowtie2algn.sam  > chip_rep1_bowtie2algn.noctg_scaff.sam && grep -v "B73V4_ctg*" chip_rep1_bowtie2algn.sam  > chip_rep1_bowtie2algn.noctg_scaff.sam 
``` 

I eventuall re-ran this software using these generated SAM (I didn't want to take the extra step of going from `samtools view | grep _v ` back to sam) files, and was eventually rewarded with:

### Final output:

```
program version:          1.18
Data files:
 File format:             sam
 Sample file:             chip_rep1_bowtie2algn.noctg_scaff.sam
 Control file:            chip_input_rep1_bowtie2algn.noctg_scaff.sam
Qualities:
 P value cut off:         0.0001
 sliding window size:     500
 Read extension length:   200
Output:
 Regions:                 test_sam_no162_region.bed
 HTML reports:            Disabled(--report not specified)

Reads statistics:

 Treatment reads +:       20131985
 Treatment reads -:       20126418
 Average read length:     76
 Control reads +:         15762557
 Control reads -:         15771271
 Average read length:     76
 Verifying reads...

Reads statistics after correction:

 Treatment reads +:       20131985
 Treatment reads -:       20126418
 Control reads +:         15762557
 Control reads -:         15771271

 Calling peaks...

Discovered 2693 regions in 1.
Discovered 1222 regions in 10.
Discovered 2065 regions in 2.
Discovered 1902 regions in 3.
Discovered 1879 regions in 4.
Discovered 2085 regions in 5.
Discovered 1538 regions in 6.
Discovered 1445 regions in 7.
Discovered 1649 regions in 8.
Discovered 1396 regions in 9.
Discovered 3    regions in Mt.
Discovered 0    regions in Pt.



Total regions discovered:       17877
```

Success! It appears that those nasty scaffolds/contigs were proving to be quite troublesome for this software. But, this isn't an ideal solution. We're still casting out genomic information that I would prefer to keep for analysis. So... There has to be a smarter way of doing this. Maybe pin pointing the exact scaffolds that were failing and why? But in my case, this got me the desired results I needed.










