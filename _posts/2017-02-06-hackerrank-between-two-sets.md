---
layout: post
title: Hacker rank 解题笔记 - Between Two Sets
---

# [Between Two Sets](https://www.hackerrank.com/challenges/between-two-sets)

思路:
* 找出B中最小数bmin
* 找出A中最大数amax
* 对范围在amax-bmin之间的数遍历找出符合要求的数

```
#!/bin/python3

import sys


n,m = input().strip().split(' ')
n,m = [int(n),int(m)]
a = [int(a_temp) for a_temp in input().strip().split(' ')]
b = [int(b_temp) for b_temp in input().strip().split(' ')]

counter = 0
amax = max(a)
bmin = min(b)

def areFactorsOf(list, num):
    for x in list:
        if num % x != 0:
            return False
    return True

def isFactorOf(num, list):
    for x in list:
        if x % num != 0:
            return False
    return True

for x in range(amax, bmin + 1):
    if areFactorsOf(a, x) and isFactorOf(x, b):
        counter += 1

print(counter)
```