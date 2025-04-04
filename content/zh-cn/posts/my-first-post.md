---
author:
categories:
- draft
comment: false
date: "2025-03-15T22:53:50+08:00"
draft: false
hiddenFromFeed: false
hiddenFromHomePage: false
hiddenFromRelated: false
hiddenFromSearch: false
lightgallery: false
math: false
repost:
  enable: true
resources:
- name: featured-image
  src: featured-image.jpg
- name: featured-image-preview
  src: featured-image-preview.jpg
slug: 583bc6c
tags:
- python
title: My First Post
toc: true
weight: 0
---



```python
import micropip
await micropip.install('numpy')  
import numpy as np
a = np.random.rand(3,2)
b = np.random.rand(2,5)

print(a@b)

```
```python


import matplotlib.pyplot as plt

fig, ax = plt.subplots()             # Create a figure containing a single Axes.
ax.plot([1, 2, 3, 10], [1, 4, 2, 3])  # Plot some data on the Axes.
plt.show()                           # Show the figure.
```