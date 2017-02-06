---
layout: post
title: Hacker rank 解题笔记 - Kangaroo
---

# [Kangaroo](https://www.hackerrank.com/challenges/kangaroo)

> There are two kangaroos on an x-axis ready to jump in the positive direction (i.e, toward positive infinity). The first kangaroo starts at location  and moves at a rate of  meters per jump. The second kangaroo starts at location  and moves at a rate of  meters per jump. Given the starting locations and movement rates for each kangaroo, can you determine if they'll ever land at the same location at the same time?

思路：转化为求是否存在t为自然数满足 x1 + t * v1 = x2 + t * v2 的问题

```
#!/bin/python3

import sys


x1,v1,x2,v2 = input().strip().split(' ')
x1,v1,x2,v2 = [int(x1),int(v1),int(x2),int(v2)]

if v1 == v2:
    print('YES' if x1 == x2 else 'NO')
else:
    t = (x1 - x2) / (v2 - v1)
    print('YES' if t.is_integer() and t >= 0 else 'NO')

```