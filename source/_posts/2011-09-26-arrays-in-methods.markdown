---
layout: post
title: Arrays in Methods
tags:
- java
- tutorial 32
alias: /post/10682942882/arrays-in-methods
---
Made an array, and take the array and take it through method change. The method then takes each of the values and adds 5, after it does that then it goes back and sees what it has to do which is print it out using a [enhanced for loop](http://codelog.org/2011/09/26/enhanced-for-loop.html).
``` java
class apples{

    public static void main (String[] args) {
    	int codelog[]={3,4,5,6,7};
    	change(codelog);

    	for(int y:codelog)
    		System.out.println(y);
    	}

    public static void change(int x[]){
    	for(int counter=0;counter<x.length;counter++)
    	x[counter]+=5;
    }

}
```