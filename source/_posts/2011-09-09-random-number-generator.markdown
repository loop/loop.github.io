---
layout: post
title: Random Number Generator
tags:
- java
- tutorial 26
alias: /post/9996612726/random-number-generator
---
``` java
import java.util.Random;

class apples{
    public static void main (String[] args) {
    	Random dice = new Random();
    	int number;

    	for(int counter=1;counter<=10;counter++){
    		number = 1+dice.nextInt(6);
    		System.out.println(number + " ");
    	}
    }
}
```

