---
layout:     post
title:      Rosalind-Calculating Protein Mass
author:     He Ting
tags:       Rosalind Java code ComputationalMassSpectrometry
subtitle:   chaining the Amino Acids
category:  code
fulview: true
---
### [Question](http://rosalind.info/problems/prtm/)
In a weighted alphabet, every symbol is assigned a positive real number called a weight. A string formed from a weighted alphabet is called a weighted string, and its weight is equal to the sum of the weights of its symbols.

The standard weight assigned to each member of the 20-symbol amino acid alphabet is the monoisotopic mass of the corresponding amino acid.

Example:

Given: A protein string P of length at most 1000 aa.

Return: The total weight of P. Consult the monoisotopic mass table.

### Note
1.When two amino acids link together, they form a peptide bond, which releases a molecule of water, after that they link together into a polypeptide. And you can call "residue" as a molecule from which a water molecule has been removed.

2.We can know the mass of a protein is the sum of masses of all its residue plus the mass of a single water molecule.

3.There are two standard ways of computing the mass of a residue by summing the masses of its individual atoms. Its monoisotopic mass is computed by using the principal(mosy abundant)isotope of each atom in the amino acid, whereas its average mass is taken by taking the average mass of each atom in the molecule. Many applications in protemoics rely on mass spectrometry, an analytical technique used to determine the mass, elemental composition, and structure of molecules.

4.The standard unit used in mass spectrometry for measuring mass is the atomic mass unit, which is also called the dalton(Da) and is defined as one twelfth of the mass of neutral atom of carbon-12.

### Solution
Step 1: Use "split" to save the data as array.

Step 2: Add each amino acid's mass.

Step 3: Output the mass in total.

### Code 
{% highlight Java %}
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class CalcuProteinMass {
public static void main(String[] args)throws IOException{
	FileReader u=new FileReader("/home/hheting/Downloads/rosalind_prtm.txt");
	
	BufferedReader br= new BufferedReader(u);
	
	String str=br.readLine();
	
	double a=71.03711;
	double c=103.00919;
	double d=115.02694;
	double e=129.04259;
	double f=147.06841;
	double g=57.02146;
	double h=137.05891;
	double i=113.08406;
	double k=128.09496;
	double l=113.08406;
	double m=131.04049;
	double n=114.04293;
	double p=97.05276;
	double q=128.05858;
	double r=156.10111;
	double s=87.03203;
	double t=101.04768;
	double v=99.06841;
	double w=186.07931;
	double y=163.06333;
	double mass=0.0;
	
	String[] arr=str.split("(?<=\\G.{1})");
	
	for(int z=0;z<arr.length;z++){
		
		if(arr[z].contains("A")){
			
			mass=mass+a;
		}
		
		if(arr[z].contains("C")){
			
			mass=mass+c;
		}
		
		if(arr[z].contains("D")){
			
			mass=mass+d;
		}
		
		if(arr[z].contains("E")){
			
			mass=mass+e;
		}
		
		if(arr[z].contains("F")){
			
			mass=mass+f;
		}
		
		if(arr[z].contains("G")){
			
			mass=mass+g;
		}
		
		if(arr[z].contains("H")){
			
			mass=mass+h;
		}
		
		if(arr[z].contains("I")){
			
			mass=mass+i;
		}
		
		if(arr[z].contains("K")){
			
			mass=mass+k;
		}
		
		if(arr[z].contains("L")){
			
			mass=mass+l;
		}
		
		if(arr[z].contains("M")){
			
			mass=mass+m;
		}
		
		if(arr[z].contains("N")){
			
			mass=mass+n;
		}
		
		if(arr[z].contains("P")){
			
			mass=mass+p;
		}
		
		if(arr[z].contains("Q")){
			
			mass=mass+q;
		}
		
		if(arr[z].contains("R")){
			
			mass=mass+r;
		}
		
		if(arr[z].contains("S")){
			
			mass=mass+s;
		}
		
		if(arr[z].contains("T")){
			
			mass=mass+t;
		}
		
		if(arr[z].contains("V")){
			
			mass=mass+v;
		}
		
		if(arr[z].contains("W")){
			
			mass=mass+w;
		}
		
		if(arr[z].contains("Y")){
			
			mass=mass+y;
		}
	}
	
	System.out.print(mass);
	
}
}
{% endhighlight %}
