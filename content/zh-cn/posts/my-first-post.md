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



\`\`\`python exec="true"
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(0, 10, 100)
plt.plot(x, np.sin(x))
plt.savefig('sin_plot.png') \# 保存图片
print("![sin wave](sin_plot.png)") \# 嵌入图片


    ```jupyter
    import numpy as np
    plt.plot(np.sin(np.linspace(0, 10, 100)))
