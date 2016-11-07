---
layout:     post
title:      Rosalind_StringAlgorithms_Finding a Motif in DNA
author:     He Ting
tags:       Rosalind Java code
subtitle:   combing through the haystack
category:  code
fulview: true
---
### [Question](http://rosalind.info/problems/subs/)
Finding the same interval of DNA in the genomes of two different organisms (often taken from different species) is highly suggestive that the interval has the same function in both organisms.

We define a motif as such a commonly shared interval of DNA. A common task in molecular biology is to search an organism's genome for a known motif.

The situation is complicated by the fact that genomes are riddled with intervals of DNA that occur multiple times (possibly with slight modifications), called repeats. These repeats occur far more often than would be dictated by random chance, indicating that genomes are anything but random and in fact illustrate that the language of DNA must be very powerful (compare with the frequent reuse of common words in any human language).

Example:

Given: Two DNA strings s and t(each of length at most 1 kbp). 

Return: All locations of t as a substring of s.

### Solution
{% highlight Java %}
import java.io.*;                                                               
public class findingamotifindnatest5{
public static void main(String[] args)throws IOException{
FileReader f =new FileReader("/home/administrator/下载/subs.txt");
BufferedReader br =new BufferedReader(f);
int n=0,j=0; 
String str1=br.readLine();
String str2=br.readLine();

n=str1.indexOf(str2);
System.out.print(n+1 + " ");

while(n!=-1){
n=str1.indexOf(str2, n+1);
j=n+1; 
System.out.print(j+" ");}

br.close();
}
} 
{% endhighlight %}
