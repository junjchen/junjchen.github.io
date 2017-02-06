---
layout: post
title: Hacker rank 解题笔记
---

# [Mini-Max Sum](https://www.hackerrank.com/challenges/mini-max-sum)

> Given five positive integers, find the minimum and maximum values that can be calculated by summing exactly four of the five integers. Then print the respective minimum and maximum values as a single line of two space-separated long integers.

思路：一次遍历找出最大和最小数字，然后从5个数字之和中分别减去，得到最小4数之和和最大4数之和

```
#!/bin/python

import sys


a,b,c,d,e = input().strip().split(' ')
a,b,c,d,e = [int(a),int(b),int(c),int(d),int(e)]

list = [a, b, c, d, e]
max, min = a, a
sum = sum(list)

for x in list:
    if x > max:
        max = x
    elif x < min:
        min = x

print(sum-max, sum-min)

```