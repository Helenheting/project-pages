---
layout:     post
title:      Rosalind Consensus and Profile
author:     He Ting
tags:       Rosalind Java code
subtitle:   finding a most likely common ancestor
category:  code
fulview: true
---
### [Question](http://rosalind.info/problems/cons/)
We have several homologous strands that we wish to analyze simultaneously. Then the natural problem is to find an average-case strand to represent the most likely common ancestor of the given strands.

Example:
Given: A collection of at most 10 DNA strings of equal length(at most 1kbp)in FASTA format.
Return: A consensus string and profile matrix for the collection.(if several possible consensus strings exist, then you may return any one of them.)

### Solution
step 1:I read the FASTA format file whitout the titles.
step 2:I used ArrayList to save gene strands and then changed datas to save as 2D-array, after that returned the transpose of this matrix.
step 3:I counted the "A G C T" in the each lines
ste 4:Outputted the most common symbol in each position.

### Code
{%gist ceaae1f0f976133c95a18b05fef288b1%}
