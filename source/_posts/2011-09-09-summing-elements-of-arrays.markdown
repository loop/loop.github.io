---
layout: post
title: Summing Elements of Arrays
tags:
- java
- tutorial 29
alias: /post/9997236831/summing-elements-of-arrays
---
``` java
class apples{
    public static void main (String[] args) {
    	int codelog[]={28,18,66,8,4,12};
    	int total=0;

    	for(int counter=0;counter<codelog.length;counter++) {
    		total+=codelog[counter];
    	}

    	System.out.println("The sum of these number is " +total);
    }
}
```