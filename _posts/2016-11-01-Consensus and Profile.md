---
layout:     post
title:      Rosalind_StringAlgorithms_Consensus and Profile
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
step 1:Try to read the FASTA format file whitout the titles.

step 2:Use ArrayList to save gene strands and then change them in 2D-array, after that return the transpose of this matrix.

step 3:Output the number of A/G/C/T in each lines

ste 4:When meet the largest number, print out the most common symbol in each position.

### Code
{% highlight Java %}
nes (28 sloc) 717 Bytes
import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class ConsensusandProfile1 {
public static void main(String[] args)throws IOException{
	FileReader f=new FileReader("/home/hheting/Downloads/rosalind_cons.txt");
	BufferedReader br=new BufferedReader(f);
	FileWriter w=new FileWriter("/home/hheting/Downloads/rosalind_cons_out.txt");
	BufferedWriter bw=new BufferedWriter(w);
	String str=br.readLine();
	if(str.contains("Rosalind")){
		str=br.readLine();
	}
	while(str!=null){
		if(str.contains("Rosalind")){
			bw.write("\n");
		}
		else{
			bw.write(str);
		}
		str=br.readLine();
	}
	br.close();
	bw.close();
}
}


import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
import java.util.ArrayList;

public class ConsensusandProfile2 {
public static void main(String[] args)throws IOException{
	FileReader f=new FileReader("/home/hheting/Downloads/rosalind_cons_out.txt");
	BufferedReader br=new BufferedReader(f);
	FileWriter w=new FileWriter("/home/hheting/Downloads/cons_pofile.txt");
	BufferedWriter bw=new BufferedWriter(w);
	String str=br.readLine();
	str=br.readLine();
	ArrayList<String[]>arrayList =new ArrayList();//using ArrayList<String[]> to save two-dimensional array data
	while(str!=null){
		String[] a=str.split("");
			arrayList.add(a);
			str=br.readLine();
	}
	String[][] test =(String [][])arrayList.toArray(new String[0][0]);
	String[][] newarray=new String[test[0].length][test.length];
	for(int i=0;i<test.length;i++){
		for(int j=0;j<test[i].length;j++){
			newarray[j][i]=test[i][j];
			}
	}
	for(int i=0;i<newarray.length;i++){
		for(int j=0;j<newarray[i].length;j++){
			bw.write(newarray[i][j]);	
		}bw.write("\n");
	}
	br.close();bw.close();
}
}


import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;
public class ConsensusandProfile3 {
	public static void main(String[] args)throws IOException{
	FileReader e=new FileReader("/home/hheting/Downloads/cons_pofile.txt");
	BufferedReader be = new BufferedReader(e);
	FileWriter rr=new FileWriter("/home/hheting/Downloads/cons_pofile_results.txt");
	BufferedWriter brr = new BufferedWriter(rr);
	String Line=be.readLine();
	int cA=0,cG=0,cC=0,cT=0;
	int countA=0,countG=0,countC=0,countT=0;
	while (Line!=null){
		cA=Line.indexOf("A");
		cG=Line.indexOf("G");
		cC=Line.indexOf("C");
		cT=Line.indexOf("T");
		while(cA!=-1){
			cA=Line.indexOf("A",cA+1);
			countA=countA+1;
		}
		while(cG!=-1){
			cG=Line.indexOf("G",cG+1);
			countG=countG+1;
		}
		while(cC!=-1){
			cC=Line.indexOf("C",cC+1);
			countC=countC+1;
		}
		while(cT!=-1){
			cT=Line.indexOf("T",cT+1);
			countT=countT+1;
		}
		brr.write(countA+" "+countG+" "+countC+" "+countT+"\n");
		cA=0;cG=0;cC=0;cT=0;
		countA=0;countG=0;countC=0;countT=0;
		Line=be.readLine();
	}
	be.close();
	brr.close();
	}
}


import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ConsensusandProfile4 {
public static void main(String[] args)throws IOException{
	FileReader f=new FileReader("/home/hheting/Downloads/cons_pofile_results.txt");
	BufferedReader br=new BufferedReader(f);
	String str=br.readLine();
	while(str!=null){
		String[] a=str.split(" ");
		int max;
		char c;
		int[] ia=new int[a.length];
		for(int i=0;i<a.length;i++){
			ia[i]=Integer.parseInt(a[i]);//converting String a[i] to int ia[i]
		}
		if(ia[0]>ia[1]){max=ia[0]; c='A'; }
		else {max=ia[1]; c='G';}
		if(max>ia[2]){;}
		else {max=ia[2]; c='C';}
		if(max>ia[3]){;}
		else {max=ia[3]; c='T';}
		System.out.print(c);
		max=0;
		c=' ';
		str=br.readLine();
	}
} 
}
{% endhighlight %}
