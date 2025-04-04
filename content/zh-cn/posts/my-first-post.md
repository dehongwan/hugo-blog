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



```javascript
// 需要Obsidian启用JavaScript渲染
const chartDiv = document.createElement('div');
chartDiv.id = 'myChart';
document.body.appendChild(chartDiv);

// 动态加载Chart.js
const script = document.createElement('script');
script.src = 'https://cdn.jsdelivr.net/npm/chart.js';
script.onload = () => {
    const ctx = document.getElementById('myChart').getContext('2d');
    new Chart(ctx, {
        type: 'line',
        data: {
            labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
            datasets: [{
                label: 'Sales 2023',
                data: [12, 19, 3, 5, 2],
                borderWidth: 1
            }]
        }
    });
};
document.head.appendChild(script);
```

```python 
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

```python
print("Hello, Obsidian!")
```