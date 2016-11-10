---
layout:     post
title:      Rosalind-SMS 2 DNA stats
author:     He Ting
tags:       Rosalind Java code BioinformaticsTools
subtitle:   Let's be practical!
category:  code
fulview: true
---
### [Question](http://rosalind.info/problems/ini/)
Of the many tools for DNA sequence analysis, one of the most popular is the Seqence Manipulation Suite. Commonly known as SMS 2, it comprises a collection of programs for generating, formatting, and analyzing short strands of DNA and polypeptides.

One in the simplest SMS 2 programs, called "DNA stats", counts the number of occurrences of each nucleotide in a given strand of DNA. An online interface for DNAstats can be found here.[link](http://www.bioinformatics.org/sms2/dna_stats.html)

Example:

Given:A DNA string s of length at most 1000 bp.

Return:Four integers (separated by spaces) representing the respective number of times that the symbols 'A', 'C', 'G', and 'T' occur in s.

### Note
In this topic, Bioinformatics Tools, we will familiarize ourselves with a sampling of some of the more popular bioinformatics tools taken from "out of the box" software.

### Code
{% highlight Java %}
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class SMS2DNAstats {
private static BufferedReader br;

public static void main(String[] args) throws IOException{
FileReader f=new FileReader("/home/hheting/Downloads/rosalind_ini.txt");
br = new BufferedReader(f);
String str=br.readLine();
	int a=0,g=0,c=0,t=0;
	int counta=0,countg=0,countc=0,countt=0;
	
	a=str.indexOf('A');
	while(a!=-1){
		a=str.indexOf('A',a+1);
		counta=counta+1;
	}
	
	g=str.indexOf('G');
	while(g!=-1){
		g=str.indexOf('G',g+1);
		countg=countg+1;
	}
	
	c=str.indexOf('C');
	while(c!=-1){
		c=str.indexOf('C',c+1);
		countc=countc+1;
	}
	
	t=str.indexOf('T');
	while(t!=-1){
		t=str.indexOf('T',t+1);
		countt=countt+1;
	}

System.out.print(counta+" ");
System.out.print(countc+" ");
System.out.print(countg+" ");
System.out.print(countt);

}

}
{% endhighlight %}
