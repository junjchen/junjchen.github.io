---
layout: post
title: Hacker rank 解题笔记 - Bon Appetit
---

# [Bon Appetit](https://www.hackerrank.com/challenges/bon-appetit)

```
#!/bin/python3

import sys

n,k = input().strip().split(' ')
n,k = [int(n),int(k)]
c = [int(c_temp) for c_temp in input().strip().split(' ')]
b = int(input().strip())

total = 0
for i in range(n):
    if i != k:
        total += c[i]

d =  b - round(total / 2)
if d == 0:
    print("Bon Appetit")
else:
    print(d)
```