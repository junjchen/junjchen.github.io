---
layout: post
title: Hacker rank 解题笔记 - Apple and Orange
---

# [Apple and Orange](https://www.hackerrank.com/challenges/apple-and-orange)

思路：通过list comprehension找出水果list中距离在房屋边界内的水果，再计算过滤后的个数

```
#!/bin/python3

import sys


s,t = input().strip().split(' ')
s,t = [int(s),int(t)]
a,b = input().strip().split(' ')
a,b = [int(a),int(b)]
m,n = input().strip().split(' ')
m,n = [int(m),int(n)]
apple = [int(apple_temp) for apple_temp in input().strip().split(' ')]
orange = [int(orange_temp) for orange_temp in input().strip().split(' ')]

print(len([x for x in apple if x >= (s-a) and x <= (t-a)]))
print(len([x for x in orange if x <= (t-b) and x >= (s-b)]))
```