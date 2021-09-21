---
layout: post
title: Improve Tree's Performance
subtitle: 
author: pizida
date: 2021-09-21 15:10:05 +0800
categories: 
tag: blog
---
This post records some methods which can improve tree's performance. 
## 1. Use Tail Recursion
Many compilers implement ***Tail call optimization***. It is much more
convenient to implement a tree using recursion than using stacks in many cases. 
However, recursion can lead to significant function call overhead. 

Try to use tail recursion (instead of normal recursion), which doesn't have such
overhead. 