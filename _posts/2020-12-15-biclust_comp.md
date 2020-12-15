---
title:  "Comparison of sparse biclustering algorithms for gene expression datasets"
date:   2020-12-15 13:46:25 +0000
layout: publication
categories:
  - research
  - biclustering

# Paper information
post_type: Paper
ref-title: "Comparison of sparse biclustering algorithms for gene expression dataset"
ref-authors: "Kath Nicholls and Chris Wallace"
ref-year: 2020
ref-pdf: "assets/files/biclust_comp_main.pdf"
ref-code: "https://github.com/nichollskc/biclust_comp"
ref-journal: "Submitted"
ref-slug: "biclust_comp"
---

Comparison study of eight sparse biclustering algorithms on gene expression datasets. I am interested in biclustering as a way to find groups of genes that have high connectivity in the gene regulatory network of the human immune system.

## Abstract

Gene clustering and sample clustering are commonly used to find patterns in gene expression datasets. However, in heterogeneous samples (e.g. different tissues or disease states), genes may cluster differently. Biclustering algorithms aim to solve this issue by performing sample clustering and gene clustering simultaneously. Existing reviews of biclustering algorithms have yet to include a number of more recent algorithms and have based comparisons on simplistic simulated datasets without specific evaluation of biclusters in real datasets, using less robust metrics.

In this study we compared four classes of sparse biclustering algorithms on a range of simulated and real datasets. In particular we use a knockout mouse RNA-seq dataset to evaluate each algorithm’s ability to simultaneously cluster genes and cluster samples across multiple tissues. We found that Bayesian algorithms with strict sparsity constraints had high accuracy on the simulated datasets and didn't require any post-processing, but were considerably slower than other algorithm classes. We assessed whether non-negative matrix factorisation algorithms can be repurposed for biclustering and found that, although the raw output was poor, after using a sparsity-inducing post-processing procedure we introduce, one such algorithm was one of the most highly ranked on real datasets. We also exhibit the limitations of biclustering algorithms by varying the complexity of simulated datasets. The algorithms generally struggled on simulated datasets with a large number of implanted factors, or with a large number of genes. In real datasets, the algorithms rarely returned clusters containing samples from multiple tissues, which highlights the need for further thought in the design and analysis of multi-tissue studies to avoid differences between tissues dominating the analysis.

## Further links

Code to run the analysis is available on [GitHub](https://github.com/nichollskc/biclust_comp), including wrappers for each algorithm, implementations of evaluation metrics, and code to simulate datasets and perform pre- and post-processing.

The full tables of results are available on [Zenodo](https://doi.org/10.5281/zenodo.4317556).

The preprint is available to download [here](/assets/files/biclust_comp.pdf) along with [Supplementary information](/]assets/files/biclust_comp_supplementary.pdf).

Talk given at MGM Michaelmas workshop: <i class="far fa-file-pdf"></i> [Slides](/assets/files/biclust_comp_MGM.pdf)

Talk focusing on the plan for the project, and the motivation for biclustering: <i class="far fa-file-pdf"></i> [Slides](/assets/files/biclust_comp_plan.pdf)
