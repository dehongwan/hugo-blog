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
import numpy as np
a = np.random.rand(3,2)
b = np.random.rand(2,5)

print(a@b)

```
```python exec="true"
from pyecharts.charts import Bar

attr = ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
v1 = [5, 20, 36, 10, 75, 90]
v2 = [10, 25, 8, 60, 20, 80]
bar = Bar()
bar.add_xaxis(attr)
bar.add_yaxis("商家A", v1)
bar.add_yaxis("商家B", v2)

chart = bar_stack()
chart.render_notebook()
```