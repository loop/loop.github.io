---
layout: post
title: Enhanced for Loop
tags:
- java
- tutorial 31
alias: /post/10682864701/enhanced-for-loop
---
This type of for statement loops through all the elements in an array so you
can do something with them.

``` java
    class apples{
    	public static void main (String[] args) {
    		int codelog[]={4,5,6,7};
    		int total=0;

    		for(int x: codelog) {
    			total+=x;
    		}

    		System.out.println(total);
    	}
    }
```