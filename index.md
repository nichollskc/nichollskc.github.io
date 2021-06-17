---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
author_profile: true
title: "About"
---

I am a PhD student in Mathematics, Genomics and Medicine at the University of Cambridge, funded by the Wellcome Trust. I am interested in improving understanding of the immune system by constructing networks describing the interactions between genes using genomics data.

## PhD University of Cambridge 2019-2022

The main aim of my PhD was to construct gene networks: networks which describe the interactions between the genes in the immune system. This is a difficult problem for a number of reasons. In particular:

- **Gene vs Protein**: Proteins are the real molecules of interest in the cell, but it is hard to measure how abundant they are in the cell. However, it turns out we *can* easily measure something called the gene expression (discussed in more detail in [this blog post](/biology/gene-expression)) which is related to the abundance of proteins. Unfortunately however, this relationship isn't quite as simple as you might hope and so it makes it harder to interpret the resulting network.
- **Scale**: There are thousands of genes involved in the immune system, which naively requires that you consider millions of possible interactions. This makes the problem computationally challenging, even for modern computers.
- **Interpretation**: The resulting network, if it does consist of thousands of genes, is difficult to interpret. An added complication is that most network construction methods don't produce a network where the edges have an intuitive meaning. For me, the most intuitive would be a causal network e.g. when you have an edge from A to B, that means that gene A causally affects the expression of gene B.

My plan in the PhD is to aim to improve network construction by focusing on ways to alleviate the **Scale** and **Interpretation** problems by breaking down the network in modules. The idea is to use the fact that these networks seem to be modular, with the thousands of genes split into relatively small modules of genes (perhaps 50-500 in a module) and that the network will have many connections within modules but few connections between modules. This means that construction now focuses on much smaller groups of genes, and that the resulting network will be easier to understand because of its modular structure.

My plan is to find these modules using a class of method called biclustering, which tries to find groups of genes with similar expression in a subset of the samples. The first project in my PhD was to [compare biclustering methods](/research/biclustering/biclust_comp) to find a good method to use for analysing a big immune cell dataset. Subsequent projects focus on using biclustering to aid gene network construction, and then applying this idea to real immune cell datasets.

## MRes University of Cambridge 2018-2019

During my MRes year I studied a number of courses in Machine Learning, Statistics, Biology, Genomics and Bioinformatics. I also completed two research rotations. The first was a starting point for my current PhD project in constructing gene regulatory networks with Chris Wallace, MRC Biostatistics Unit, and Ken Smith, CITIID, Department of Medicine. The second was feature design for predicting whether two peptide fragments will bind together, with potential application in research in Alzheimer's Disease. This was a joint project with Michele Vendrusculo at the Centre for Misfolding Diseases, Chemistry, Pietro Lio' in Computer Science and Paul Kirk in MRC Biostatistics Unit.

## Before Cambridge

I studied Mathematics (MMath) at the University of Oxford from 2012-2016, focusing on pure mathematics in the early years but with a greater focus on statistics in later years. I think the greatest skill I gained from this degree was the ability to look at a dense page of information, none of which I understand, and slowly work out its meaning piece by piece. I have found this a useful skill when studying in many different fields, and in programming.

I've always had an interest in coding. In 2015 I completed a summer internship at a software engineering company and started a job at the same company after my graduation in 2016. I learned how to code in C and python and improved key coding skills such as design and test generation.

