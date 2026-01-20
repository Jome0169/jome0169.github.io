---
layout: post
title: Identifying RNA-Seq strandedneess
date: 2019-06-20 16:32 -0400
tags: old-postings
share: false
image:
---

Often times it's essential to know the strand orientation of your library. If
for instance you have overlapping genes, or very closely nested genes, you wont
be able to accuretly calculate transcription units unless you know the strand
of origin of both your RNA library and your genes
of interest. 

In order to identify the strand orientation of RNA NGS libraries I
downloaded from SRA I stumpbled upon this excellent little tool called
`infer_experiment.py` from the [RseqC](http://rseqc.sourceforge.net). It's
a great resource for this kind of thing. `infer_experiment.py` takes in a bam
file (aligned to your genome) and a BED file of genes with known strandedness.

So - to run it in parallel on all my bam libraries I just did a simple
parallel command to expedite it as it's quite quick.

```
parallel -j 2 "infer_experiment.py -r Zea_mays.AGPv4.36.gene_only_strand.bed -i {} > library_type_id_{/.}.txt" ::: ../all_aligned_files_sorted/*.bam
```

After this runs, the output looks like 
```
This is PairEnd Data
Fraction of reads failed to determine: 0.0067
Fraction of reads explained by "1++,1--,2+-,2-+": 0.4973
Fraction of reads explained by "1+-,1-+,2++,2--": 0.4960


This is PairEnd Data
Fraction of reads failed to determine: 0.0104
Fraction of reads explained by "1++,1--,2+-,2-+": 0.5001
Fraction of reads explained by "1+-,1-+,2++,2--": 0.4895
```

So, what this output is telling you is that the reads are coming from either
hte posotive or negative strand, and do NOT agree with the strandedness of the
genes they're aligning to. So this is an UNSTRANDED library.

In case you're looking for some extra reading on strand libraries I found the
following links extemely useful

<https://chipster.csc.fi/manual/library-type-summary.html>

<http://onetipperday.sterding.com/2012/07/how-to-tell-which-library-type-to-use.html>

