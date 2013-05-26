---
layout: post
title: Multidimensional Arrays
tags:
- java
- tutorial 33
alias: /post/10683046970/multidimensional-arrays
---
You can create multidimensional array by by using `[][]` instead of `[], []` is
used to create just one array.

You can call the elements in the multidimensional array by using `firstarray[0][1]` (calls the first element in the first array).
{% raw %}
```java
class apples {
  public static main(String[] args){
    int firstarray[][] = {{1,2,3,4}, {5,6,7,8}};
    int secondarray[][] = {{10,11,12,13}, {14,15,16,17,}};
  }
}
```
{% endraw %}