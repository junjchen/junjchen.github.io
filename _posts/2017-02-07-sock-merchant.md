---
layout: post
title: Hacker rank 解题笔记 - Sock Merchant
---

# [Sock Merchant](https://www.hackerrank.com/challenges/sock-merchant)

思路：使用一个数组作为比较组，初始为空数组，从原始数组中取出来的袜子与比较组的寻找匹配，如果成功则从比较组移除匹配的袜子并计数加一，否则将该袜子放入比较组

```
#!/bin/python3

import sys


n = int(input().strip())
c = [int(c_temp) for c_temp in input().strip().split(' ')]

m = []
counter = 0

for x in c:
    if x in m:
        m.remove(x)
        counter += 1
    else:
        m.append(x)

print(counter)
```