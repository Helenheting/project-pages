---
layout:     post
title:      Rosalind_StringAlgorithms_Computing GC Content
author:     He Ting
tags:       Rosalind Java code
subtitle:   identifying unknown DNA quickly
category:  code
fulview: true
---
### [Question](http://rosalind.info/problems/gc/)
The biological analog of identifying unknown text arises when researchers encounter a molecule of DNA deriving from an unknown species. Because of the base pairing relations of the two DNA strands, cytosine and guanine will always appear in equal amounts in a double-stranded DNA molecule. Thus, to analyze the symbol frequencies of DNA for comparison against a database, we compute the molecule's GC-content, or the percentage of its bases that are either cytosine or guanine.

In practice, the GC-content of most eukaryotic genomes hovers around 50%. However, because genomes are so long, we may be able to distinguish species based on very small discrepancies in GC-content; furthermore, most prokaryotes have a GC-content significantly higher than 50%, so that GC-content can be used to quickly differentiate many prokaryotes and eukaryotes by using relatively small DNA samples.

Example:

Given: At most 10 DNA strings in FASTA format (of length at most 1 kbp each).

Return: The ID of the string having the highest GC-content, followed by the GC-content of that string. Rosalind allows for a default error of 0.001 in all decimal answers unless otherwise stated; please see the note on absolute error below.
### Code
{% highlight Java %}
import java.io.*;                                                              
public class countinggccontenttest2{
public static void main(String args[])throws IOException{
FileReader f=new FileReader("/home/administrator/下载/rosalind_gc.txt");
BufferedReader br=new BufferedReader(f);
String str=br.readLine();
String stmo="Rosalind";
int n=0,countn=0,m=0,countm=0,countnm=0;
double len=0;
while(str!=null){
        while(str.contains(stmo)){
        System.out.print(str +"\n");
        str=br.readLine();
        }
        while(!str.contains(stmo)){
        n=str.indexOf("G");
        m=str.indexOf("C");
        len=len+str.length();
                        while(n!=-1){
                        n=str.indexOf("G",n+1);
                        countn=countn+1;}       
                        while(m!=-1){
                        m=str.indexOf("C",m+1);
                        countm=countm+1;}   
        countnm=countn+countm;
        str=br.readLine();
        }
        System.out.print("The number of G is:" + countn +"\n"); 
        System.out.print("The number of C is:" + countm +"\n");
        System.out.print("The number of G&C is:" + countnm +"\n");
        System.out.print("The length of this sequence is:" + len +"\n"); 
        System.out.print("The GC content is:" + (countnm/len)*100+"\n");
        countn=0;
        countm=0;
        countnm=0;
        len=0;  
        }
}
}
{% endhighlight %}
