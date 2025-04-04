---
title: My First Post
subtitle: 
date: 2025-03-15T22:53:50+08:00
slug: 583bc6c
draft: false
author:
  name: 
  link: 
  email: 
  avatar: 
description: 
keywords: 
license: 
comment: false
weight: 0
tags:
  - python
categories:
  - draft
hiddenFromHomePage: false
hiddenFromSearch: false
hiddenFromRelated: false
hiddenFromFeed: false
summary: 
resources:
  - name: featured-image
    src: featured-image.jpg
  - name: featured-image-preview
    src: featured-image-preview.jpg
toc: true
math: false
lightgallery: false
password: 
message: 
repost:
  enable: true
  url:
---

```python exec="true"
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x))
plt.savefig('sin_plot.png')  # 保存图片
print("![sin wave](sin_plot.png)")  # 嵌入图片
```

```jupyter
import numpy as np
plt.plot(np.sin(np.linspace(0, 10, 100)))
```