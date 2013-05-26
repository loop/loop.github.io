---
layout: post
title: Variable Length Arguments
tags:
- java
- tutorial 35
alias: /post/10683337446/variable-length-arguments
---
If you don't know how many variables there are going to be in a list you can
use an ellipse to say "I don't know how many there are going to be but I want
you to do the same method no matter how many variables there are".
``` java
class apples {

  public static void main(String[] args) {
    System.out.println(average(43,56,44,7,546,55));
  }

  public static double average (int...numbers) {
    int total=0;
    for(int x:numbers) {
      total+=x;
      return total/(double)numbers.length;
    }
  }

}
```