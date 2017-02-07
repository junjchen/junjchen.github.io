---
layout: post
title: Hacker rank 解题笔记 - Divisible Sum Pairs
---

# [Divisible Sum Pairs](https://www.hackerrank.com/challenges/divisible-sum-pairs)

思路：两次循环遍历

```
#!/bin/python3

import sys


n,k = input().strip().split(' ')
n,k = [int(n),int(k)]
a = [int(a_temp) for a_temp in input().strip().split(' ')]

count = 0

for i in range(n-1):
    for x in a[i+1:]:
        if (a[i] + x) % k == 0:
            count += 1

print(count)
```