---
layout:     post
title:      Rosalind-Rabbits and Recurrence Relations
author:     He Ting
tags:       Rosalind Java code DynamicProgramming
subtitle:   wascally wabbits
category:  code
fulview: true
---
### [Question](http://rosalind.info/problems/fib/)
European rabbits were introduced to Australia in the mid 19th Century, a place with no real indigenous predators for them. Within 50 years, the rabbits had already eradicated many plant species across the continent, leading to irreversible changes in the Australian ecosystem and turning much of its grasslands into eroded, practically uninhabitable parts of the modern Outback

Example:

Given: Positive integers n≤40 and k≤5.

Return: The total number of rabbit pairs that will be present after n months, if we begin with 1 pair and in each generation, every pair of reproduction-age rabbits produces a litter of k rabbit pairs (instead of only 1 pair).

### Code
{% highlight Java %}
import java.io.*;
public class RecurrenceRelationstest1{
static class rabbit{//所以这里要static
	int generation=0;
	int offspring=0;
	long fibi(int gener,int off){
	generation=gener;
	offspring=off;
	if(generation==1){
	return 1;}
	else if(generation==2){
	return 1;}
	else {return fibi(gener-1,off-1)+4*fibi(gener-2,off-2);}}}

static rabbit r1=new rabbit();//static关键字的作用方便在没有创建对象的情况下来进行调用
public static void main(String args[]){
System.out.print(r1.fibi(32,4));}}
{% endhighlight %}

