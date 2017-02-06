---
layout: post
title: Hacker rank 解题笔记 - Designer PDF Viewer
---

# [DEsigner PDF Viewer]()

思路：把词分切成字母，通过ord()得到字母"a"的ASCII码，并计算每个字母相对字母a的索引差，通过一次循环找出各字母对应的最大高度

```
#!/bin/python3

import sys


h = list(map(int, input().strip().split(' ')))
word = input().strip()

a_index = ord('a')
max_height = 0
letters = list(word)
index_list = map(lambda x: ord(x) - a_index, letters)

for x in index_list:
    xh = h[x]
    if xh > max_height:
        max_height = xh

print(max_height * len(letters))

```