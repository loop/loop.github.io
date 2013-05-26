---
layout: post
title: Conditional Operators
tags:
- java
- tutorial 20
alias: /post/9995064332/conditional-operators
---
Another way of writing if else statements, add question mark after the
condition. Treats it as boolean expression. Give it two options. True =
executes first option else second option.

``` java
import java.util.Scanner;

class apples{
  public static void main (String[] args) {
    int age = 66;
    System.out.println(age > 50 ? "You are old" : "You are young");
  }
}
```

