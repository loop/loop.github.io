---
layout: post
title: Creating an Array Table
tags:
- java
- tutorial 28
alias: /post/9997119719/creating-an-array-table
---
``` java
class apples {
    public static void main (String[] args) {

    	System.out.println("Index	Value");
    	int codelog[]={32,19,17,55,2,8};

    	for (int counter=0;counter<codelog.length;counter++){
    		System.out.println(counter + "	" + codelog[counter]);
    	}
    }
}
```