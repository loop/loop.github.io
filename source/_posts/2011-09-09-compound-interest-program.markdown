---
layout: post
title: Compound Interest Program
tags:
- java
- tutorial 22
---
``` java
import java.util.Scanner;

class apples{
  public static void main (String[] args) {
    double amount;
    double principle = 10000;
    double rate = .01;

    for (int day=1;day<=20;day++){
      amount=principle*Math.pow(1 + rate, day);
      System.out.println(day + "   "+ amount);
    }
  }
}
```