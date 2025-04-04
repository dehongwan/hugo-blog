

```python exec="true"
import plotly.express as px
import pandas as pd


df = pd.DataFrame({'x': [1,2,3,4,5], 'y': [10,20,15,25,30]})

# 创建图表
fig = px.line(df, x='x', y='y', title='动态折线图')

# 保存到 Obsidian 附件目录
fig.write_html("assets/charts/plotly_chart.html")

# 生成嵌入代码
print('<iframe src="assets/charts/plotly_chart.html" width="100%" height="400"></iframe>')
```

```





<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://assets.pyecharts.org/assets/v5/echarts.min.js"></script>


</head>
<body >
    <div id="b759c4fd581847859c4b0a0295829e40" class="chart-container" style="width:900px; height:500px; "></div>
    <script>
        var chart_b759c4fd581847859c4b0a0295829e40 = echarts.init(
            document.getElementById('b759c4fd581847859c4b0a0295829e40'), 'white', {renderer: 'canvas'});
        var option_b759c4fd581847859c4b0a0295829e40 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "color": [
        "#5470c6",
        "#91cc75",
        "#fac858",
        "#ee6666",
        "#73c0de",
        "#3ba272",
        "#fc8452",
        "#9a60b4",
        "#ea7ccc"
    ],
    "series": [
        {
            "type": "bar",
            "name": "\u5546\u5bb6A",
            "legendHoverLink": true,
            "data": [
                5,
                20,
                36,
                10,
                75,
                90
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "\u5546\u5bb6B",
            "legendHoverLink": true,
            "data": [
                10,
                25,
                8,
                60,
                20,
                80
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u5546\u5bb6A",
                "\u5546\u5bb6B"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u886c\u886b",
                "\u7f8a\u6bdb\u886b",
                "\u96ea\u7eba\u886b",
                "\u88e4\u5b50",
                "\u9ad8\u8ddf\u978b",
                "\u889c\u5b50"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_b759c4fd581847859c4b0a0295829e40.setOption(option_b759c4fd581847859c4b0a0295829e40);
    </script>
</body>
</html>





```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker



def bar_stack():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    # stack值一样的系列会堆叠在一起
    bar.add_yaxis('A', Faker.values(), stack='stack1')
    bar.add_yaxis('B', Faker.values(), stack='stack1')
    bar.add_yaxis('C', Faker.values(), stack='stack2')
    return bar



chart = bar_stack()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://assets.pyecharts.org/assets/v5/echarts.min.js"></script>


</head>
<body >
    <div id="17551ba8abb94e08a7e547c6367af388" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_17551ba8abb94e08a7e547c6367af388 = echarts.init(
            document.getElementById('17551ba8abb94e08a7e547c6367af388'), 'light', {renderer: 'canvas'});
        var option_17551ba8abb94e08a7e547c6367af388 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                127,
                139,
                70,
                122,
                53,
                56,
                42
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stack": "stack1",
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                124,
                71,
                54,
                62,
                79,
                46,
                122
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stack": "stack1",
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "C",
            "legendHoverLink": true,
            "data": [
                71,
                99,
                104,
                149,
                99,
                129,
                31
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stack": "stack2",
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B",
                "C"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u54c8\u58eb\u5947",
                "\u8428\u6469\u8036",
                "\u6cf0\u8fea",
                "\u91d1\u6bdb",
                "\u7267\u7f8a\u72ac",
                "\u5409\u5a03\u5a03",
                "\u67ef\u57fa"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_17551ba8abb94e08a7e547c6367af388.setOption(option_17551ba8abb94e08a7e547c6367af388);
    </script>
</body>
</html>




#### 2.关闭坐标轴显示

* 碰上类目标签过长的时候，可以选择关闭坐标轴，将数据&标签直接显示在图形中；


```python
from pyecharts.globals import CurrentConfig
CurrentConfig.ONLINE_HOST = "https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/"
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_axis_off():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('', Faker.values())
    # 碰上类目标签过长的时候，可以选择关闭坐标轴，直接显示在图形中
    bar.set_series_opts(label_opts=opts.LabelOpts(position='insideLeft', formatter='{b}:{c}'))
    bar.set_global_opts(xaxis_opts=opts.AxisOpts(is_show=False),
                        yaxis_opts=opts.AxisOpts(is_show=False))
    bar.reversal_axis()
    return bar


chart = bar_with_axis_off()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="77dd8c219d3a46e1b1d58ffee82dd272" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_77dd8c219d3a46e1b1d58ffee82dd272 = echarts.init(
            document.getElementById('77dd8c219d3a46e1b1d58ffee82dd272'), 'light', {renderer: 'canvas'});
        var option_77dd8c219d3a46e1b1d58ffee82dd272 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "legendHoverLink": true,
            "data": [
                142,
                101,
                105,
                83,
                77,
                87,
                148
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "position": "insideLeft",
                "margin": 8,
                "formatter": "{b}:{c}",
                "valueAnimation": false
            },
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": false,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "yAxis": [
        {
            "show": false,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u53ef\u4e50",
                "\u96ea\u78a7",
                "\u6a59\u6c41",
                "\u7eff\u8336",
                "\u5976\u8336",
                "\u767e\u5a01",
                "\u9752\u5c9b"
            ]
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_77dd8c219d3a46e1b1d58ffee82dd272.setOption(option_77dd8c219d3a46e1b1d58ffee82dd272);
    </script>
</body>
</html>




#### 3.自定义坐标轴标签文本


#### 4.更改坐标轴数据类型

* x轴默认数据类型是使用离散型，在使用散点图的时候可调整为数值型；


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = [random.randint(0, 20) for _ in range(100)]
y_data = [random.randint(0, 50) for _ in range(100)]


def scatter_with_value_xaxis():
    scatter = Scatter(init_opts=opts.InitOpts(theme='light',
                                              width='1000px',
                                              height='600px'))
    scatter.add_xaxis(x_data)
    scatter.add_yaxis('', y_data)
    # X轴默认数据类型为离散数据，设置为数值型
    scatter.set_global_opts(xaxis_opts=opts.AxisOpts(type_="value"))
    return scatter

chart = scatter_with_value_xaxis()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="c8335c09845d4b4bbefcd4fce8bb1d13" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_c8335c09845d4b4bbefcd4fce8bb1d13 = echarts.init(
            document.getElementById('c8335c09845d4b4bbefcd4fce8bb1d13'), 'light', {renderer: 'canvas'});
        var option_c8335c09845d4b4bbefcd4fce8bb1d13 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "symbolSize": 10,
            "data": [
                [
                    4,
                    33
                ],
                [
                    19,
                    31
                ],
                [
                    14,
                    50
                ],
                [
                    6,
                    8
                ],
                [
                    8,
                    13
                ],
                [
                    10,
                    32
                ],
                [
                    19,
                    11
                ],
                [
                    19,
                    16
                ],
                [
                    3,
                    11
                ],
                [
                    6,
                    9
                ],
                [
                    17,
                    19
                ],
                [
                    6,
                    0
                ],
                [
                    5,
                    40
                ],
                [
                    12,
                    23
                ],
                [
                    0,
                    48
                ],
                [
                    10,
                    14
                ],
                [
                    8,
                    4
                ],
                [
                    19,
                    34
                ],
                [
                    13,
                    48
                ],
                [
                    7,
                    29
                ],
                [
                    20,
                    7
                ],
                [
                    0,
                    48
                ],
                [
                    14,
                    18
                ],
                [
                    19,
                    23
                ],
                [
                    2,
                    34
                ],
                [
                    6,
                    20
                ],
                [
                    16,
                    0
                ],
                [
                    6,
                    3
                ],
                [
                    6,
                    36
                ],
                [
                    14,
                    3
                ],
                [
                    12,
                    23
                ],
                [
                    8,
                    1
                ],
                [
                    10,
                    18
                ],
                [
                    14,
                    25
                ],
                [
                    5,
                    37
                ],
                [
                    19,
                    31
                ],
                [
                    2,
                    30
                ],
                [
                    2,
                    2
                ],
                [
                    17,
                    16
                ],
                [
                    11,
                    43
                ],
                [
                    17,
                    46
                ],
                [
                    3,
                    7
                ],
                [
                    18,
                    32
                ],
                [
                    9,
                    19
                ],
                [
                    4,
                    38
                ],
                [
                    10,
                    23
                ],
                [
                    3,
                    34
                ],
                [
                    0,
                    16
                ],
                [
                    3,
                    36
                ],
                [
                    8,
                    14
                ],
                [
                    8,
                    49
                ],
                [
                    16,
                    7
                ],
                [
                    15,
                    37
                ],
                [
                    4,
                    46
                ],
                [
                    10,
                    40
                ],
                [
                    8,
                    14
                ],
                [
                    7,
                    50
                ],
                [
                    17,
                    16
                ],
                [
                    12,
                    42
                ],
                [
                    8,
                    11
                ],
                [
                    9,
                    39
                ],
                [
                    16,
                    7
                ],
                [
                    11,
                    49
                ],
                [
                    16,
                    22
                ],
                [
                    1,
                    38
                ],
                [
                    8,
                    30
                ],
                [
                    17,
                    24
                ],
                [
                    9,
                    17
                ],
                [
                    20,
                    5
                ],
                [
                    7,
                    0
                ],
                [
                    10,
                    45
                ],
                [
                    17,
                    33
                ],
                [
                    7,
                    14
                ],
                [
                    20,
                    34
                ],
                [
                    13,
                    48
                ],
                [
                    1,
                    0
                ],
                [
                    13,
                    41
                ],
                [
                    8,
                    6
                ],
                [
                    13,
                    45
                ],
                [
                    4,
                    36
                ],
                [
                    4,
                    45
                ],
                [
                    19,
                    45
                ],
                [
                    9,
                    40
                ],
                [
                    7,
                    16
                ],
                [
                    6,
                    41
                ],
                [
                    17,
                    18
                ],
                [
                    19,
                    16
                ],
                [
                    4,
                    1
                ],
                [
                    18,
                    5
                ],
                [
                    4,
                    5
                ],
                [
                    16,
                    49
                ],
                [
                    2,
                    15
                ],
                [
                    18,
                    15
                ],
                [
                    17,
                    25
                ],
                [
                    11,
                    16
                ],
                [
                    7,
                    39
                ],
                [
                    3,
                    41
                ],
                [
                    5,
                    6
                ],
                [
                    2,
                    5
                ],
                [
                    5,
                    14
                ]
            ],
            "label": {
                "show": true,
                "position": "right",
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "type": "value",
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                4,
                19,
                14,
                6,
                8,
                10,
                19,
                19,
                3,
                6,
                17,
                6,
                5,
                12,
                0,
                10,
                8,
                19,
                13,
                7,
                20,
                0,
                14,
                19,
                2,
                6,
                16,
                6,
                6,
                14,
                12,
                8,
                10,
                14,
                5,
                19,
                2,
                2,
                17,
                11,
                17,
                3,
                18,
                9,
                4,
                10,
                3,
                0,
                3,
                8,
                8,
                16,
                15,
                4,
                10,
                8,
                7,
                17,
                12,
                8,
                9,
                16,
                11,
                16,
                1,
                8,
                17,
                9,
                20,
                7,
                10,
                17,
                7,
                20,
                13,
                1,
                13,
                8,
                13,
                4,
                4,
                19,
                9,
                7,
                6,
                17,
                19,
                4,
                18,
                4,
                16,
                2,
                18,
                17,
                11,
                7,
                3,
                5,
                2,
                5
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_c8335c09845d4b4bbefcd4fce8bb1d13.setOption(option_c8335c09845d4b4bbefcd4fce8bb1d13);
    </script>
</body>
</html>




#### 5.双Y轴【直方图&折线图】

* 实际是Bar和Line两个图表共用同一套坐标体系，将Bar和Line分别指向不同的Y轴；


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ['香蕉', '梨子', '水蜜桃', '核桃', '西瓜', '苹果']
y_data_1 = [random.randint(10, 50) for _ in range(len(x_data))]
y_data_2 = [random.randint(100, 500) for _ in range(len(x_data))]


def bar_line_combine_with_two_axis():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(x_data)
    # 添加一个Y轴
    bar.extend_axis(yaxis=opts.AxisOpts())
    bar.add_yaxis('左边Y轴', y_data_1, yaxis_index=0)

    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data)
    # 将line数据通过yaxis_index指向后添加的Y轴
    line.add_yaxis('右边Y轴', y_data_2, yaxis_index=1)

    bar.overlap(line)
    return bar


chart = bar_line_combine_with_two_axis()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="49f239a14d62440baa09a0d63cc9196f" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_49f239a14d62440baa09a0d63cc9196f = echarts.init(
            document.getElementById('49f239a14d62440baa09a0d63cc9196f'), 'light', {renderer: 'canvas'});
        var option_49f239a14d62440baa09a0d63cc9196f = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "\u5de6\u8fb9Y\u8f74",
            "yAxisIndex": 0,
            "legendHoverLink": true,
            "data": [
                16,
                21,
                15,
                24,
                23,
                37
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "line",
            "name": "\u53f3\u8fb9Y\u8f74",
            "connectNulls": false,
            "xAxisIndex": 0,
            "yAxisIndex": 1,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u9999\u8549",
                    479
                ],
                [
                    "\u68a8\u5b50",
                    143
                ],
                [
                    "\u6c34\u871c\u6843",
                    428
                ],
                [
                    "\u6838\u6843",
                    459
                ],
                [
                    "\u897f\u74dc",
                    401
                ],
                [
                    "\u82f9\u679c",
                    251
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        }
    ],
    "legend": [
        {
            "data": [
                "\u5de6\u8fb9Y\u8f74",
                "\u53f3\u8fb9Y\u8f74"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u9999\u8549",
                "\u68a8\u5b50",
                "\u6c34\u871c\u6843",
                "\u6838\u6843",
                "\u897f\u74dc",
                "\u82f9\u679c"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_49f239a14d62440baa09a0d63cc9196f.setOption(option_49f239a14d62440baa09a0d63cc9196f);
    </script>
</body>
</html>





```python

```

#### 6.直方图——双Y轴


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ['香蕉', '梨子', '水蜜桃', '核桃', '西瓜', '苹果']
y_data_1 = [random.randint(10, 50) for _ in range(len(x_data))]
y_data_2 = [random.randint(100, 500) for _ in range(len(x_data))]


def bar_with_multiple_axis():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(x_data)
    # 添加一个Y轴
    bar.extend_axis(yaxis=opts.AxisOpts())
    # 分别指定使用的Y轴
    bar.add_yaxis('左边Y轴', y_data_1, yaxis_index=0)
    bar.add_yaxis('右边Y轴', y_data_2, yaxis_index=1)
    return bar


chart = bar_with_multiple_axis()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="d5efee7643334c62950f6fea575e66bd" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_d5efee7643334c62950f6fea575e66bd = echarts.init(
            document.getElementById('d5efee7643334c62950f6fea575e66bd'), 'light', {renderer: 'canvas'});
        var option_d5efee7643334c62950f6fea575e66bd = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "\u5de6\u8fb9Y\u8f74",
            "yAxisIndex": 0,
            "legendHoverLink": true,
            "data": [
                17,
                14,
                11,
                23,
                12,
                24
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "\u53f3\u8fb9Y\u8f74",
            "yAxisIndex": 1,
            "legendHoverLink": true,
            "data": [
                238,
                121,
                188,
                396,
                351,
                216
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u5de6\u8fb9Y\u8f74",
                "\u53f3\u8fb9Y\u8f74"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u9999\u8549",
                "\u68a8\u5b50",
                "\u6c34\u871c\u6843",
                "\u6838\u6843",
                "\u897f\u74dc",
                "\u82f9\u679c"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_d5efee7643334c62950f6fea575e66bd.setOption(option_d5efee7643334c62950f6fea575e66bd);
    </script>
</body>
</html>





```python
#### 7.折线图——双X轴
```


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data_1 = ["2020/10/{}".format(i + 1) for i in range(30)]
x_data_2 = ["2019/10/{}".format(i + 1) for i in range(30)]
y_data_1 = [random.randint(10, 50) for _ in range(30)]
y_data_2 = [random.randint(20, 60) for _ in range(30)]


def line_with_two_xaxis():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data_1)
    # 添加一个x轴
    line.extend_axis(xaxis_data=x_data_2, xaxis=opts.AxisOpts())
    line.add_yaxis('下面X轴', y_data_1)
    line.add_yaxis('上面X轴', y_data_2)
    return line


chart = line_with_two_xaxis()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="5cee256c610c43c894429a488109ce7e" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_5cee256c610c43c894429a488109ce7e = echarts.init(
            document.getElementById('5cee256c610c43c894429a488109ce7e'), 'light', {renderer: 'canvas'});
        var option_5cee256c610c43c894429a488109ce7e = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "name": "\u4e0b\u9762X\u8f74",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    23
                ],
                [
                    "2020/10/2",
                    29
                ],
                [
                    "2020/10/3",
                    50
                ],
                [
                    "2020/10/4",
                    19
                ],
                [
                    "2020/10/5",
                    35
                ],
                [
                    "2020/10/6",
                    47
                ],
                [
                    "2020/10/7",
                    40
                ],
                [
                    "2020/10/8",
                    12
                ],
                [
                    "2020/10/9",
                    11
                ],
                [
                    "2020/10/10",
                    43
                ],
                [
                    "2020/10/11",
                    38
                ],
                [
                    "2020/10/12",
                    16
                ],
                [
                    "2020/10/13",
                    12
                ],
                [
                    "2020/10/14",
                    18
                ],
                [
                    "2020/10/15",
                    50
                ],
                [
                    "2020/10/16",
                    24
                ],
                [
                    "2020/10/17",
                    32
                ],
                [
                    "2020/10/18",
                    17
                ],
                [
                    "2020/10/19",
                    29
                ],
                [
                    "2020/10/20",
                    21
                ],
                [
                    "2020/10/21",
                    49
                ],
                [
                    "2020/10/22",
                    40
                ],
                [
                    "2020/10/23",
                    46
                ],
                [
                    "2020/10/24",
                    48
                ],
                [
                    "2020/10/25",
                    27
                ],
                [
                    "2020/10/26",
                    35
                ],
                [
                    "2020/10/27",
                    25
                ],
                [
                    "2020/10/28",
                    16
                ],
                [
                    "2020/10/29",
                    17
                ],
                [
                    "2020/10/30",
                    20
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        },
        {
            "type": "line",
            "name": "\u4e0a\u9762X\u8f74",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    56
                ],
                [
                    "2020/10/2",
                    53
                ],
                [
                    "2020/10/3",
                    53
                ],
                [
                    "2020/10/4",
                    40
                ],
                [
                    "2020/10/5",
                    48
                ],
                [
                    "2020/10/6",
                    54
                ],
                [
                    "2020/10/7",
                    22
                ],
                [
                    "2020/10/8",
                    58
                ],
                [
                    "2020/10/9",
                    26
                ],
                [
                    "2020/10/10",
                    39
                ],
                [
                    "2020/10/11",
                    26
                ],
                [
                    "2020/10/12",
                    60
                ],
                [
                    "2020/10/13",
                    53
                ],
                [
                    "2020/10/14",
                    25
                ],
                [
                    "2020/10/15",
                    31
                ],
                [
                    "2020/10/16",
                    32
                ],
                [
                    "2020/10/17",
                    53
                ],
                [
                    "2020/10/18",
                    55
                ],
                [
                    "2020/10/19",
                    30
                ],
                [
                    "2020/10/20",
                    28
                ],
                [
                    "2020/10/21",
                    36
                ],
                [
                    "2020/10/22",
                    23
                ],
                [
                    "2020/10/23",
                    40
                ],
                [
                    "2020/10/24",
                    59
                ],
                [
                    "2020/10/25",
                    31
                ],
                [
                    "2020/10/26",
                    20
                ],
                [
                    "2020/10/27",
                    49
                ],
                [
                    "2020/10/28",
                    34
                ],
                [
                    "2020/10/29",
                    27
                ],
                [
                    "2020/10/30",
                    55
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        }
    ],
    "legend": [
        {
            "data": [
                "\u4e0b\u9762X\u8f74",
                "\u4e0a\u9762X\u8f74"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2019/10/1",
                "2019/10/2",
                "2019/10/3",
                "2019/10/4",
                "2019/10/5",
                "2019/10/6",
                "2019/10/7",
                "2019/10/8",
                "2019/10/9",
                "2019/10/10",
                "2019/10/11",
                "2019/10/12",
                "2019/10/13",
                "2019/10/14",
                "2019/10/15",
                "2019/10/16",
                "2019/10/17",
                "2019/10/18",
                "2019/10/19",
                "2019/10/20",
                "2019/10/21",
                "2019/10/22",
                "2019/10/23",
                "2019/10/24",
                "2019/10/25",
                "2019/10/26",
                "2019/10/27",
                "2019/10/28",
                "2019/10/29",
                "2019/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_5cee256c610c43c894429a488109ce7e.setOption(option_5cee256c610c43c894429a488109ce7e);
    </script>
</body>
</html>




#### 8.自定义图例图形

* 当前并不支持同一个图表针对不同的系列设置不同的icon
* 方案是将多个系列的数据拆分到多个图表设置各自的icon，最后通过grid将图表组合起来


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

ios_icon = 'path://M24.734 17.003c-0.040-4.053 3.305-5.996 3.454-6.093-1.88-2.751-4.808-3.127-5.851-3.171-2.492-0.252-4.862 1.467-6.127 1.467-1.261 0-3.213-1.43-5.28-1.392-2.716 0.040-5.221 1.579-6.619 4.012-2.822 4.897-0.723 12.151 2.028 16.123 1.344 1.944 2.947 4.127 5.051 4.049 2.026-0.081 2.793-1.311 5.242-1.311s3.138 1.311 5.283 1.271c2.18-0.041 3.562-1.981 4.897-3.931 1.543-2.255 2.179-4.439 2.216-4.551-0.048-0.022-4.252-1.632-4.294-6.473zM20.705 5.11c1.117-1.355 1.871-3.235 1.665-5.11-1.609 0.066-3.559 1.072-4.713 2.423-1.036 1.199-1.942 3.113-1.699 4.951 1.796 0.14 3.629-0.913 4.747-2.264z'
android_icon = 'path://M28 12c-1.1 0-2 0.9-2 2v8c0 1.1 0.9 2 2 2s2-0.9 2-2v-8c0-1.1-0.9-2-2-2zM4 12c-1.1 0-2 0.9-2 2v8c0 1.1 0.9 2 2 2s2-0.9 2-2v-8c0-1.1-0.9-2-2-2zM7 23c0 1.657 1.343 3 3 3v0 4c0 1.1 0.9 2 2 2s2-0.9 2-2v-4h4v4c0 1.1 0.9 2 2 2s2-0.9 2-2v-4c1.657 0 3-1.343 3-3v-11h-18v11zM24.944 10c-0.304-2.746-1.844-5.119-4.051-6.551l1.001-2.001c0.247-0.494 0.047-1.095-0.447-1.342s-1.095-0.047-1.342 0.447l-1.004 2.009-0.261-0.104c-0.893-0.297-1.848-0.458-2.84-0.458s-1.947 0.161-2.84 0.458l-0.261 0.104-1.004-2.009c-0.247-0.494-0.848-0.694-1.342-0.447s-0.694 0.848-0.447 1.342l1.001 2.001c-2.207 1.433-3.747 3.805-4.051 6.551v1h17.944v-1h-0.056zM13 8c-0.552 0-1-0.448-1-1s0.447-0.999 0.998-1c0.001 0 0.002 0 0.003 0s0.001-0 0.002-0c0.551 0.001 0.998 0.448 0.998 1s-0.448 1-1 1zM19 8c-0.552 0-1-0.448-1-1s0.446-0.999 0.998-1c0 0 0.001 0 0.002 0s0.002-0 0.003-0c0.551 0.001 0.998 0.448 0.998 1s-0.448 1-1 1z'

x_data = ["2020/7/{}".format(i + 1) for i in range(10)]

# 随机生成点数据
y_data_1 = [random.randint(10, 20) for i in range(len(x_data))]
y_data_2 = [random.randint(15, 25) for i in range(len(x_data))]


def bar_custom_legend_symbol():
    # 当前并不支持同一个图表针对不同的系列设置不同的icon
    # 方案是将多个系列的数据拆分到多个图表设置各自的icon，最后通过grid将图表组合起来
    ios_bar = Bar()
    ios_bar.add_xaxis(x_data)
    ios_bar.add_yaxis('IOS', y_data_1)
    ios_bar.set_global_opts(legend_opts=opts.LegendOpts(legend_icon=ios_icon,
                                                        pos_right='15%'))

    az_bar = Bar()
    az_bar.add_xaxis(x_data)
    az_bar.add_yaxis('Android', y_data_2)
    az_bar.set_global_opts(legend_opts=opts.LegendOpts(legend_icon=android_icon,
                                                       pos_right='5%'))

    # 将az_bar和ios_bar组合起来
    grid = Grid(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    grid.add(ios_bar, is_control_axis_index=True, grid_opts=opts.GridOpts())
    grid.add(az_bar, is_control_axis_index=True, grid_opts=opts.GridOpts())
    return grid


chart = bar_custom_legend_symbol()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="7ca69f5f575741a59b279cc9fa1c1498" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_7ca69f5f575741a59b279cc9fa1c1498 = echarts.init(
            document.getElementById('7ca69f5f575741a59b279cc9fa1c1498'), 'light', {renderer: 'canvas'});
        var option_7ca69f5f575741a59b279cc9fa1c1498 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "color": [],
    "series": [
        {
            "type": "bar",
            "name": "IOS",
            "legendHoverLink": true,
            "data": [
                11,
                11,
                15,
                18,
                19,
                19,
                19,
                14,
                12,
                12
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "Android",
            "legendHoverLink": true,
            "data": [
                16,
                21,
                16,
                18,
                17,
                16,
                21,
                17,
                18,
                15
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "IOS"
            ],
            "selected": {},
            "show": true,
            "right": "15%",
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "icon": "path://M24.734 17.003c-0.040-4.053 3.305-5.996 3.454-6.093-1.88-2.751-4.808-3.127-5.851-3.171-2.492-0.252-4.862 1.467-6.127 1.467-1.261 0-3.213-1.43-5.28-1.392-2.716 0.040-5.221 1.579-6.619 4.012-2.822 4.897-0.723 12.151 2.028 16.123 1.344 1.944 2.947 4.127 5.051 4.049 2.026-0.081 2.793-1.311 5.242-1.311s3.138 1.311 5.283 1.271c2.18-0.041 3.562-1.981 4.897-3.931 1.543-2.255 2.179-4.439 2.216-4.551-0.048-0.022-4.252-1.632-4.294-6.473zM20.705 5.11c1.117-1.355 1.871-3.235 1.665-5.11-1.609 0.066-3.559 1.072-4.713 2.423-1.036 1.199-1.942 3.113-1.699 4.951 1.796 0.14 3.629-0.913 4.747-2.264z",
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        },
        {
            "data": [
                "Android"
            ],
            "selected": {},
            "show": true,
            "right": "5%",
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "icon": "path://M28 12c-1.1 0-2 0.9-2 2v8c0 1.1 0.9 2 2 2s2-0.9 2-2v-8c0-1.1-0.9-2-2-2zM4 12c-1.1 0-2 0.9-2 2v8c0 1.1 0.9 2 2 2s2-0.9 2-2v-8c0-1.1-0.9-2-2-2zM7 23c0 1.657 1.343 3 3 3v0 4c0 1.1 0.9 2 2 2s2-0.9 2-2v-4h4v4c0 1.1 0.9 2 2 2s2-0.9 2-2v-4c1.657 0 3-1.343 3-3v-11h-18v11zM24.944 10c-0.304-2.746-1.844-5.119-4.051-6.551l1.001-2.001c0.247-0.494 0.047-1.095-0.447-1.342s-1.095-0.047-1.342 0.447l-1.004 2.009-0.261-0.104c-0.893-0.297-1.848-0.458-2.84-0.458s-1.947 0.161-2.84 0.458l-0.261 0.104-1.004-2.009c-0.247-0.494-0.848-0.694-1.342-0.447s-0.694 0.848-0.447 1.342l1.001 2.001c-2.207 1.433-3.747 3.805-4.051 6.551v1h17.944v-1h-0.056zM13 8c-0.552 0-1-0.448-1-1s0.447-0.999 0.998-1c0.001 0 0.002 0 0.003 0s0.001-0 0.002-0c0.551 0.001 0.998 0.448 0.998 1s-0.448 1-1 1zM19 8c-0.552 0-1-0.448-1-1s0.446-0.999 0.998-1c0 0 0.001 0 0.002 0s0.002-0 0.003-0c0.551 0.001 0.998 0.448 0.998 1s-0.448 1-1 1z",
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/7/1",
                "2020/7/2",
                "2020/7/3",
                "2020/7/4",
                "2020/7/5",
                "2020/7/6",
                "2020/7/7",
                "2020/7/8",
                "2020/7/9",
                "2020/7/10"
            ]
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 1,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/7/1",
                "2020/7/2",
                "2020/7/3",
                "2020/7/4",
                "2020/7/5",
                "2020/7/6",
                "2020/7/7",
                "2020/7/8",
                "2020/7/9",
                "2020/7/10"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 1,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        },
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "grid": [
        {
            "show": false,
            "zlevel": 0,
            "z": 2,
            "containLabel": false,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderWidth": 1,
            "shadowOffsetX": 0,
            "shadowOffsetY": 0
        },
        {
            "show": false,
            "zlevel": 0,
            "z": 2,
            "containLabel": false,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderWidth": 1,
            "shadowOffsetX": 0,
            "shadowOffsetY": 0
        }
    ]
};
        chart_7ca69f5f575741a59b279cc9fa1c1498.setOption(option_7ca69f5f575741a59b279cc9fa1c1498);
    </script>
</body>
</html>




#### 9.图例选择设置单选


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker

def bar_single_selected():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    # 设置图例选择模式为单选
    bar.set_global_opts(legend_opts=opts.LegendOpts(selected_mode='single'))
    return bar


chart = bar_single_selected()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="917054a3f1f6480eaf0a78f045b1e52c" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_917054a3f1f6480eaf0a78f045b1e52c = echarts.init(
            document.getElementById('917054a3f1f6480eaf0a78f045b1e52c'), 'light', {renderer: 'canvas'});
        var option_917054a3f1f6480eaf0a78f045b1e52c = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                23,
                52,
                108,
                126,
                58,
                21,
                57
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                89,
                60,
                43,
                69,
                46,
                106,
                118
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {},
            "selectedMode": "single",
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u886c\u886b",
                "\u6bdb\u8863",
                "\u9886\u5e26",
                "\u88e4\u5b50",
                "\u98ce\u8863",
                "\u9ad8\u8ddf\u978b",
                "\u889c\u5b50"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_917054a3f1f6480eaf0a78f045b1e52c.setOption(option_917054a3f1f6480eaf0a78f045b1e52c);
    </script>
</body>
</html>




#### 10.设置默认选中系列


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_default_selected_series():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    # 默认选中A C
    bar.add_yaxis('A', Faker.values(), is_selected=True)
    bar.add_yaxis('B', Faker.values(), is_selected=False)
    bar.add_yaxis('C', Faker.values(), is_selected=True)
    return bar


chart = bar_with_default_selected_series()
from IPython.display import HTML
HTML(chart.render_embed())
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[25], line 18
         14     bar.add_yaxis('C', Faker.values(), is_selected=True)
         15     return bar
    ---> 18 chart = bar_with_default_selected_series()
         19 from IPython.display import HTML
         20 HTML(chart.render_embed())
    

    Cell In[25], line 12, in bar_with_default_selected_series()
         10 bar.add_xaxis(Faker.choose())
         11 # 默认选中A C
    ---> 12 bar.add_yaxis('A', Faker.values(), is_selected=True)
         13 bar.add_yaxis('B', Faker.values(), is_selected=False)
         14 bar.add_yaxis('C', Faker.values(), is_selected=True)
    

    TypeError: Bar.add_yaxis() got an unexpected keyword argument 'is_selected'


#### 11.缩略轴——inside组件


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data = [random.randint(10, 20) for i in range(len(x_data))]


def bar_datazoom_inside():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(x_data)
    bar.add_yaxis('', y_data)
    bar.set_global_opts(datazoom_opts=opts.DataZoomOpts(type_='inside',
                                                        range_start=50,   # 设置起止位置，50%-100%
                                                        range_end=100))
    return bar


chart = bar_datazoom_inside()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="81ed8fc3857e4cd186b3ba4316a53a74" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_81ed8fc3857e4cd186b3ba4316a53a74 = echarts.init(
            document.getElementById('81ed8fc3857e4cd186b3ba4316a53a74'), 'light', {renderer: 'canvas'});
        var option_81ed8fc3857e4cd186b3ba4316a53a74 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "legendHoverLink": true,
            "data": [
                15,
                13,
                15,
                18,
                11,
                20,
                16,
                20,
                15,
                16,
                12,
                19,
                16,
                16,
                11,
                14,
                17,
                17,
                20,
                13,
                20,
                15,
                11,
                18,
                12,
                14,
                13,
                13,
                18,
                12
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "dataZoom": {
        "show": true,
        "type": "inside",
        "showDetail": true,
        "showDataShadow": true,
        "realtime": true,
        "start": 50,
        "end": 100,
        "orient": "horizontal",
        "zoomLock": false,
        "filterMode": "filter",
        "disabled": false,
        "zoomOnMouseWheel": true,
        "moveOnMouseMove": true,
        "moveOnMouseWheel": true,
        "preventDefaultMouseMove": true
    }
};
        chart_81ed8fc3857e4cd186b3ba4316a53a74.setOption(option_81ed8fc3857e4cd186b3ba4316a53a74);
    </script>
</body>
</html>




#### 12.缩略轴——slider组件


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data = [random.randint(10, 20) for i in range(len(x_data))]


def bar_with_datazoom_slider():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(x_data)
    bar.add_yaxis('', y_data)
    bar.set_global_opts(datazoom_opts=opts.DataZoomOpts(range_start=50,   # 设置起止位置，50%-100%
                                                        range_end=100))
    return bar


chart = bar_with_datazoom_slider()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="6a7ad5262e404696a7ec7551a8c05bcb" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_6a7ad5262e404696a7ec7551a8c05bcb = echarts.init(
            document.getElementById('6a7ad5262e404696a7ec7551a8c05bcb'), 'light', {renderer: 'canvas'});
        var option_6a7ad5262e404696a7ec7551a8c05bcb = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "legendHoverLink": true,
            "data": [
                11,
                17,
                10,
                19,
                15,
                10,
                15,
                12,
                17,
                10,
                14,
                11,
                12,
                13,
                14,
                10,
                15,
                20,
                13,
                15,
                16,
                17,
                17,
                17,
                16,
                20,
                15,
                20,
                17,
                18
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "dataZoom": {
        "show": true,
        "type": "slider",
        "showDetail": true,
        "showDataShadow": true,
        "realtime": true,
        "start": 50,
        "end": 100,
        "orient": "horizontal",
        "zoomLock": false,
        "filterMode": "filter"
    }
};
        chart_6a7ad5262e404696a7ec7551a8c05bcb.setOption(option_6a7ad5262e404696a7ec7551a8c05bcb);
    </script>
</body>
</html>




#### 13.缩略轴——slider组件&inside组件


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data = [random.randint(10, 20) for i in range(len(x_data))]


def bar_datazoom_both_way():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(x_data)
    bar.add_yaxis('', y_data)
    # 通过list传入两个datazoom_opts
    bar.set_global_opts(datazoom_opts=[opts.DataZoomOpts(),
                                       opts.DataZoomOpts(type_='inside', range_start=50, range_end=100)])
    return bar


chart = bar_datazoom_both_way()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="091f136639c24cb4a224cbeccf6f8a52" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_091f136639c24cb4a224cbeccf6f8a52 = echarts.init(
            document.getElementById('091f136639c24cb4a224cbeccf6f8a52'), 'light', {renderer: 'canvas'});
        var option_091f136639c24cb4a224cbeccf6f8a52 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "legendHoverLink": true,
            "data": [
                13,
                14,
                16,
                11,
                19,
                15,
                19,
                12,
                17,
                16,
                17,
                14,
                14,
                12,
                19,
                17,
                13,
                20,
                14,
                19,
                10,
                19,
                14,
                17,
                19,
                20,
                14,
                13,
                18,
                18
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "dataZoom": [
        {
            "show": true,
            "type": "slider",
            "showDetail": true,
            "showDataShadow": true,
            "realtime": true,
            "start": 20,
            "end": 80,
            "orient": "horizontal",
            "zoomLock": false,
            "filterMode": "filter"
        },
        {
            "show": true,
            "type": "inside",
            "showDetail": true,
            "showDataShadow": true,
            "realtime": true,
            "start": 50,
            "end": 100,
            "orient": "horizontal",
            "zoomLock": false,
            "filterMode": "filter",
            "disabled": false,
            "zoomOnMouseWheel": true,
            "moveOnMouseMove": true,
            "moveOnMouseWheel": true,
            "preventDefaultMouseMove": true
        }
    ]
};
        chart_091f136639c24cb4a224cbeccf6f8a52.setOption(option_091f136639c24cb4a224cbeccf6f8a52);
    </script>
</body>
</html>




#### 14.XY轴翻转


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_reverse_axis():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    # x,y轴翻转
    bar.reversal_axis()
    return bar


chart = bar_reverse_axis()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="0c5b1e0e0ec343d99d0e07eaa9706a53" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_0c5b1e0e0ec343d99d0e07eaa9706a53 = echarts.init(
            document.getElementById('0c5b1e0e0ec343d99d0e07eaa9706a53'), 'light', {renderer: 'canvas'});
        var option_0c5b1e0e0ec343d99d0e07eaa9706a53 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                130,
                69,
                60,
                106,
                44,
                86,
                135
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                148,
                66,
                41,
                52,
                120,
                38,
                142
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u54c8\u58eb\u5947",
                "\u8428\u6469\u8036",
                "\u6cf0\u8fea",
                "\u91d1\u6bdb",
                "\u7267\u7f8a\u72ac",
                "\u5409\u5a03\u5a03",
                "\u67ef\u57fa"
            ]
        }
    ]
};
        chart_0c5b1e0e0ec343d99d0e07eaa9706a53.setOption(option_0c5b1e0e0ec343d99d0e07eaa9706a53);
    </script>
</body>
</html>




#### 15.设置动画效果

* 在图表加载前会有一段动画效果；
* 更多动画效果可参见：https://echarts.apache.org/examples/zh/editor.html?c=line-easing


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker

"""
更多动画效果可参见：https://echarts.apache.org/examples/zh/editor.html?c=line-easing
"""


def bar_with_animation():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px',
                                      animation_opts=opts.AnimationOpts(animation_delay=1000,   # 动画延时
                                                                        animation_easing='bounceIn')
                                      )
              )
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    return bar


chart = bar_with_animation()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="e0c864d845ee42218e355b308c71489b" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_e0c864d845ee42218e355b308c71489b = echarts.init(
            document.getElementById('e0c864d845ee42218e355b308c71489b'), 'light', {renderer: 'canvas'});
        var option_e0c864d845ee42218e355b308c71489b = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "bounceIn",
    "animationDelay": 1000,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                140,
                61,
                126,
                67,
                37,
                36,
                56
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                143,
                21,
                24,
                115,
                86,
                52,
                70
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u6cb3\u9a6c",
                "\u87d2\u86c7",
                "\u8001\u864e",
                "\u5927\u8c61",
                "\u5154\u5b50",
                "\u718a\u732b",
                "\u72ee\u5b50"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_e0c864d845ee42218e355b308c71489b.setOption(option_e0c864d845ee42218e355b308c71489b);
    </script>
</body>
</html>




#### 15.直方图带视觉组件


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_visualmap_color():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    # 设置视觉组件，默认通过颜色映射数据，数值范围为0-100，可通过min_和max_进行自定义
    bar.set_global_opts(visualmap_opts=opts.VisualMapOpts())
    return bar


chart = bar_with_visualmap_color()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="a5c24c70dc2546ef835525bcf85a4310" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_a5c24c70dc2546ef835525bcf85a4310 = echarts.init(
            document.getElementById('a5c24c70dc2546ef835525bcf85a4310'), 'light', {renderer: 'canvas'});
        var option_a5c24c70dc2546ef835525bcf85a4310 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                55,
                95,
                52,
                95,
                86,
                50,
                127
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                108,
                96,
                23,
                85,
                28,
                66,
                25
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u6cb3\u9a6c",
                "\u87d2\u86c7",
                "\u8001\u864e",
                "\u5927\u8c61",
                "\u5154\u5b50",
                "\u718a\u732b",
                "\u72ee\u5b50"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": {
        "show": true,
        "type": "continuous",
        "min": 0,
        "max": 100,
        "inRange": {
            "color": [
                "#50a3ba",
                "#eac763",
                "#d94e5d"
            ]
        },
        "calculable": true,
        "inverse": false,
        "splitNumber": 5,
        "hoverLink": true,
        "orient": "vertical",
        "padding": 5,
        "showLabel": true,
        "itemWidth": 20,
        "itemHeight": 140,
        "borderWidth": 0
    }
};
        chart_a5c24c70dc2546ef835525bcf85a4310.setOption(option_a5c24c70dc2546ef835525bcf85a4310);
    </script>
</body>
</html>




#### 16.设置渐变色(线性渐变)


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker
from pyecharts.commons.utils import JsCode

color_js = """
            new echarts.graphic.LinearGradient(
                                0, 
                                1, 
                                0, 
                                0,
                                [{offset: 0, color: '#008B8B'}, 
                                 {offset: 1, color: '#FF6347'}], 
                                false)
           """


def bar_with_linear_gradient_color():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('', Faker.values(),
                  # 使用JsCode执行渐变色代码
                  itemstyle_opts=opts.ItemStyleOpts(color=JsCode(color_js)))

    return bar


chart = bar_with_linear_gradient_color()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="9cc8ef20bbc4414a89735a2a1d9706ff" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_9cc8ef20bbc4414a89735a2a1d9706ff = echarts.init(
            document.getElementById('9cc8ef20bbc4414a89735a2a1d9706ff'), 'light', {renderer: 'canvas'});
        var option_9cc8ef20bbc4414a89735a2a1d9706ff = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "legendHoverLink": true,
            "data": [
                24,
                90,
                62,
                145,
                76,
                147,
                51
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "itemStyle": {
                "color":             new echarts.graphic.LinearGradient(                                0,                                 1,                                 0,                                 0,                                [{offset: 0, color: '#008B8B'},                                  {offset: 1, color: '#FF6347'}],                                 false)           
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u6cb3\u9a6c",
                "\u87d2\u86c7",
                "\u8001\u864e",
                "\u5927\u8c61",
                "\u5154\u5b50",
                "\u718a\u732b",
                "\u72ee\u5b50"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_9cc8ef20bbc4414a89735a2a1d9706ff.setOption(option_9cc8ef20bbc4414a89735a2a1d9706ff);
    </script>
</body>
</html>




#### 17.设置渐变色(径向渐变)


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker
from pyecharts.commons.utils import JsCode

color_js = """new echarts.graphic.RadialGradient(
                    0.4, 0.3, 1,
                    [{offset: 0,
                      color: '#F8F8FF'},
                     {offset: 1,
                      color: '#00BFFF'}
                      ])"""


def scatter_with_radial_gradient_color():
    scatter = Scatter(init_opts=opts.InitOpts(theme='light',
                                              width='1000px',
                                              height='600px'))
    scatter.add_xaxis(Faker.choose())

    scatter.add_yaxis("", Faker.values(),
                      symbol_size=50,
                      # 渐变配色
                      itemstyle_opts=opts.ItemStyleOpts(color=JsCode(color_js)))
    return scatter


chart = scatter_with_radial_gradient_color()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="21a69ff4d6b240139067cc05240b170e" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_21a69ff4d6b240139067cc05240b170e = echarts.init(
            document.getElementById('21a69ff4d6b240139067cc05240b170e'), 'light', {renderer: 'canvas'});
        var option_21a69ff4d6b240139067cc05240b170e = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "symbolSize": 50,
            "data": [
                [
                    "\u5c0f\u7c73",
                    122
                ],
                [
                    "\u4e09\u661f",
                    144
                ],
                [
                    "\u534e\u4e3a",
                    24
                ],
                [
                    "\u82f9\u679c",
                    48
                ],
                [
                    "\u9b45\u65cf",
                    123
                ],
                [
                    "VIVO",
                    59
                ],
                [
                    "OPPO",
                    79
                ]
            ],
            "label": {
                "show": true,
                "position": "right",
                "margin": 8,
                "valueAnimation": false
            },
            "itemStyle": {
                "color": new echarts.graphic.RadialGradient(                    0.4, 0.3, 1,                    [{offset: 0,                      color: '#F8F8FF'},                     {offset: 1,                      color: '#00BFFF'}                      ])
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5c0f\u7c73",
                "\u4e09\u661f",
                "\u534e\u4e3a",
                "\u82f9\u679c",
                "\u9b45\u65cf",
                "VIVO",
                "OPPO"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_21a69ff4d6b240139067cc05240b170e.setOption(option_21a69ff4d6b240139067cc05240b170e);
    </script>
</body>
</html>




#### 18.设置分割线


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_custom_splitline():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    # 设置分割线
    bar.set_global_opts(yaxis_opts=opts.AxisOpts(
        splitline_opts=opts.SplitLineOpts(is_show=True,
                                          linestyle_opts=opts.LineStyleOpts(type_='dotted'))))
    return bar


chart = bar_with_custom_splitline()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="71927b44c3584c07bab7432597582a19" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_71927b44c3584c07bab7432597582a19 = echarts.init(
            document.getElementById('71927b44c3584c07bab7432597582a19'), 'light', {renderer: 'canvas'});
        var option_71927b44c3584c07bab7432597582a19 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                47,
                27,
                149,
                149,
                141,
                33,
                111
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                103,
                113,
                145,
                109,
                95,
                102,
                24
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5468\u4e00",
                "\u5468\u4e8c",
                "\u5468\u4e09",
                "\u5468\u56db",
                "\u5468\u4e94",
                "\u5468\u516d",
                "\u5468\u65e5"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "dotted"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_71927b44c3584c07bab7432597582a19.setOption(option_71927b44c3584c07bab7432597582a19);
    </script>
</body>
</html>




#### 19.设置分割区域


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_custom_splitarea():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    # 设置分割区域
    bar.set_global_opts(yaxis_opts=opts.AxisOpts(
        splitarea_opts=opts.SplitAreaOpts(is_show=True,
                                          areastyle_opts=opts.AreaStyleOpts(opacity=1))))
    return bar


chart = bar_with_custom_splitarea()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="d9e3dfda2fb647258314e4e8549bbc5b" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_d9e3dfda2fb647258314e4e8549bbc5b = echarts.init(
            document.getElementById('d9e3dfda2fb647258314e4e8549bbc5b'), 'light', {renderer: 'canvas'});
        var option_d9e3dfda2fb647258314e4e8549bbc5b = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                110,
                41,
                88,
                122,
                64,
                84,
                30
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                29,
                100,
                100,
                134,
                65,
                117,
                54
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5468\u4e00",
                "\u5468\u4e8c",
                "\u5468\u4e09",
                "\u5468\u56db",
                "\u5468\u4e94",
                "\u5468\u516d",
                "\u5468\u65e5"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "splitArea": {
                "show": true,
                "areaStyle": {
                    "opacity": 1
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_d9e3dfda2fb647258314e4e8549bbc5b.setOption(option_d9e3dfda2fb647258314e4e8549bbc5b);
    </script>
</body>
</html>




#### 20.通过字典配置


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_dict_config():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('', Faker.values())
    # 通过字典配置itemstyle
    bar.set_series_opts(itemstyle_opts=dict(color='#008B8B', opacity=0.8))
    return bar


chart = bar_with_dict_config()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="5559d7e10625474087351d2e2fdd561d" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_5559d7e10625474087351d2e2fdd561d = echarts.init(
            document.getElementById('5559d7e10625474087351d2e2fdd561d'), 'light', {renderer: 'canvas'});
        var option_5559d7e10625474087351d2e2fdd561d = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "legendHoverLink": true,
            "data": [
                116,
                136,
                114,
                138,
                101,
                99,
                48
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "itemStyle": {
                "color": "#008B8B",
                "opacity": 0.8
            },
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5c0f\u7c73",
                "\u4e09\u661f",
                "\u534e\u4e3a",
                "\u82f9\u679c",
                "\u9b45\u65cf",
                "VIVO",
                "OPPO"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_5559d7e10625474087351d2e2fdd561d.setOption(option_5559d7e10625474087351d2e2fdd561d);
    </script>
</body>
</html>




#### 21.面积图
* 实现方式就是在**折线图先填充区域**；


```python

from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data = [i + random.randint(10, 20) for i in range(len(x_data))]


def line_with_area():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data)
    line.add_yaxis('', y_data)
    # opacity 默认为0，即透明
    line.set_series_opts(areastyle_opts=opts.AreaStyleOpts(opacity=0.5))

    return line


chart = line_with_area()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="4b406db03be84a93887cf9916b0a5ec9" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_4b406db03be84a93887cf9916b0a5ec9 = echarts.init(
            document.getElementById('4b406db03be84a93887cf9916b0a5ec9'), 'light', {renderer: 'canvas'});
        var option_4b406db03be84a93887cf9916b0a5ec9 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    15
                ],
                [
                    "2020/10/2",
                    19
                ],
                [
                    "2020/10/3",
                    22
                ],
                [
                    "2020/10/4",
                    22
                ],
                [
                    "2020/10/5",
                    22
                ],
                [
                    "2020/10/6",
                    24
                ],
                [
                    "2020/10/7",
                    17
                ],
                [
                    "2020/10/8",
                    25
                ],
                [
                    "2020/10/9",
                    20
                ],
                [
                    "2020/10/10",
                    29
                ],
                [
                    "2020/10/11",
                    29
                ],
                [
                    "2020/10/12",
                    31
                ],
                [
                    "2020/10/13",
                    22
                ],
                [
                    "2020/10/14",
                    28
                ],
                [
                    "2020/10/15",
                    25
                ],
                [
                    "2020/10/16",
                    27
                ],
                [
                    "2020/10/17",
                    32
                ],
                [
                    "2020/10/18",
                    37
                ],
                [
                    "2020/10/19",
                    36
                ],
                [
                    "2020/10/20",
                    34
                ],
                [
                    "2020/10/21",
                    37
                ],
                [
                    "2020/10/22",
                    34
                ],
                [
                    "2020/10/23",
                    35
                ],
                [
                    "2020/10/24",
                    33
                ],
                [
                    "2020/10/25",
                    37
                ],
                [
                    "2020/10/26",
                    35
                ],
                [
                    "2020/10/27",
                    43
                ],
                [
                    "2020/10/28",
                    46
                ],
                [
                    "2020/10/29",
                    48
                ],
                [
                    "2020/10/30",
                    47
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0.5
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_4b406db03be84a93887cf9916b0a5ec9.setOption(option_4b406db03be84a93887cf9916b0a5ec9);
    </script>
</body>
</html>




#### 22.堆叠面积图


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def line_stack_area():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(Faker.choose())
    line.add_yaxis('A',
                   Faker.values(),
                   stack='stack')
    line.add_yaxis('B',
                   Faker.values(),
                   stack='stack')
    line.add_yaxis('C',
                   Faker.values(),
                   stack='stack')
    # opacity 默认为0，即透明
    line.set_series_opts(areastyle_opts=opts.AreaStyleOpts(opacity=0.5))

    return line


chart = line_stack_area()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="43f667fe83504ae48cb6d0240c6dea6c" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_43f667fe83504ae48cb6d0240c6dea6c = echarts.init(
            document.getElementById('43f667fe83504ae48cb6d0240c6dea6c'), 'light', {renderer: 'canvas'});
        var option_43f667fe83504ae48cb6d0240c6dea6c = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "name": "A",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stack": "stack",
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u53ef\u4e50",
                    51
                ],
                [
                    "\u96ea\u78a7",
                    103
                ],
                [
                    "\u6a59\u6c41",
                    100
                ],
                [
                    "\u7eff\u8336",
                    97
                ],
                [
                    "\u5976\u8336",
                    109
                ],
                [
                    "\u767e\u5a01",
                    89
                ],
                [
                    "\u9752\u5c9b",
                    48
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0.5
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        },
        {
            "type": "line",
            "name": "B",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stack": "stack",
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u53ef\u4e50",
                    24
                ],
                [
                    "\u96ea\u78a7",
                    44
                ],
                [
                    "\u6a59\u6c41",
                    94
                ],
                [
                    "\u7eff\u8336",
                    36
                ],
                [
                    "\u5976\u8336",
                    145
                ],
                [
                    "\u767e\u5a01",
                    25
                ],
                [
                    "\u9752\u5c9b",
                    103
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0.5
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        },
        {
            "type": "line",
            "name": "C",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stack": "stack",
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u53ef\u4e50",
                    69
                ],
                [
                    "\u96ea\u78a7",
                    59
                ],
                [
                    "\u6a59\u6c41",
                    134
                ],
                [
                    "\u7eff\u8336",
                    148
                ],
                [
                    "\u5976\u8336",
                    60
                ],
                [
                    "\u767e\u5a01",
                    69
                ],
                [
                    "\u9752\u5c9b",
                    96
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0.5
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B",
                "C"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u53ef\u4e50",
                "\u96ea\u78a7",
                "\u6a59\u6c41",
                "\u7eff\u8336",
                "\u5976\u8336",
                "\u767e\u5a01",
                "\u9752\u5c9b"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_43f667fe83504ae48cb6d0240c6dea6c.setOption(option_43f667fe83504ae48cb6d0240c6dea6c);
    </script>
</body>
</html>




#### 23.自定义线样式（LineStyleOpts）


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def line_with_custom_linestyle():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(Faker.choose())
    line.add_yaxis('样式1',
                   Faker.values(),
                   linestyle_opts=opts.LineStyleOpts(width=5,
                                                     curve=0,
                                                     opacity=0.7,
                                                     type_='solid',
                                                     color='red')
                   )
    line.add_yaxis('样式2',
                   Faker.values(),
                   linestyle_opts=opts.LineStyleOpts(width=3,
                                                     curve=0.5,
                                                     opacity=0.9,
                                                     type_='dashed',
                                                     color='yellow')
                   )
    line.add_yaxis('样式3',
                   Faker.values(),
                   linestyle_opts=opts.LineStyleOpts(width=1,
                                                     curve=1,
                                                     opacity=0.5,
                                                     type_='dotted',
                                                     color='green')
                   )
    return line


chart = line_with_custom_linestyle()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="25c5f191c19f49cdae8dbe8e11bd7965" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_25c5f191c19f49cdae8dbe8e11bd7965 = echarts.init(
            document.getElementById('25c5f191c19f49cdae8dbe8e11bd7965'), 'light', {renderer: 'canvas'});
        var option_25c5f191c19f49cdae8dbe8e11bd7965 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "name": "\u6837\u5f0f1",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u5468\u4e00",
                    98
                ],
                [
                    "\u5468\u4e8c",
                    99
                ],
                [
                    "\u5468\u4e09",
                    45
                ],
                [
                    "\u5468\u56db",
                    106
                ],
                [
                    "\u5468\u4e94",
                    30
                ],
                [
                    "\u5468\u516d",
                    28
                ],
                [
                    "\u5468\u65e5",
                    46
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 5,
                "opacity": 0.7,
                "curveness": 0,
                "type": "solid",
                "color": "red"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        },
        {
            "type": "line",
            "name": "\u6837\u5f0f2",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u5468\u4e00",
                    35
                ],
                [
                    "\u5468\u4e8c",
                    146
                ],
                [
                    "\u5468\u4e09",
                    70
                ],
                [
                    "\u5468\u56db",
                    115
                ],
                [
                    "\u5468\u4e94",
                    100
                ],
                [
                    "\u5468\u516d",
                    65
                ],
                [
                    "\u5468\u65e5",
                    139
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 3,
                "opacity": 0.9,
                "curveness": 0.5,
                "type": "dashed",
                "color": "yellow"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        },
        {
            "type": "line",
            "name": "\u6837\u5f0f3",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u5468\u4e00",
                    60
                ],
                [
                    "\u5468\u4e8c",
                    82
                ],
                [
                    "\u5468\u4e09",
                    142
                ],
                [
                    "\u5468\u56db",
                    83
                ],
                [
                    "\u5468\u4e94",
                    28
                ],
                [
                    "\u5468\u516d",
                    59
                ],
                [
                    "\u5468\u65e5",
                    114
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 0.5,
                "curveness": 1,
                "type": "dotted",
                "color": "green"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        }
    ],
    "legend": [
        {
            "data": [
                "\u6837\u5f0f1",
                "\u6837\u5f0f2",
                "\u6837\u5f0f3"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5468\u4e00",
                "\u5468\u4e8c",
                "\u5468\u4e09",
                "\u5468\u56db",
                "\u5468\u4e94",
                "\u5468\u516d",
                "\u5468\u65e5"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_25c5f191c19f49cdae8dbe8e11bd7965.setOption(option_25c5f191c19f49cdae8dbe8e11bd7965);
    </script>
</body>
</html>




#### 24. 带阴影效果折线图

* `linestyle_opts`在默认参数中并不支持直接配置阴影效果，可选择通过dict传入`shadowOffsetX`等参数来实现；


```python

from pyecharts.charts import *
from pyecharts import options as opts
import random

line_style = {
    'normal': {
        'width': 4,  # 设置线宽
        'shadowColor': 'rgba(155, 18, 184, .3)',  # 阴影颜色
        'shadowBlur': 10,  # 阴影大小
        'shadowOffsetY': 10,  # Y轴方向阴影偏移
        'shadowOffsetX': 10,  # x轴方向阴影偏移
        'curve': 0.5  # 线弯曲程度，1表示不弯曲
    }
}

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data_1 = [i + random.randint(10, 20) for i in range(len(x_data))]
y_data_2 = [i + random.randint(15, 25) for i in range(len(x_data))]


def line_with_shadow():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data)
    line.add_yaxis("Android",
                   y_data_1,
                   is_symbol_show=False,
                   is_smooth=True,
                   # 传入线风格参数
                   linestyle_opts=line_style)
    line.add_yaxis("IOS",
                   y_data_2,
                   is_symbol_show=False,
                   is_smooth=True,
                   # 传入线风格参数
                   linestyle_opts=line_style)
    line.set_global_opts(title_opts=opts.TitleOpts(title="终端日活趋势"))
    return line


chart = line_with_shadow()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="221039faa93b4fad82fd9f62839fccb0" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_221039faa93b4fad82fd9f62839fccb0 = echarts.init(
            document.getElementById('221039faa93b4fad82fd9f62839fccb0'), 'light', {renderer: 'canvas'});
        var option_221039faa93b4fad82fd9f62839fccb0 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "name": "Android",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": false,
            "smooth": true,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    20
                ],
                [
                    "2020/10/2",
                    15
                ],
                [
                    "2020/10/3",
                    16
                ],
                [
                    "2020/10/4",
                    17
                ],
                [
                    "2020/10/5",
                    20
                ],
                [
                    "2020/10/6",
                    20
                ],
                [
                    "2020/10/7",
                    20
                ],
                [
                    "2020/10/8",
                    17
                ],
                [
                    "2020/10/9",
                    27
                ],
                [
                    "2020/10/10",
                    20
                ],
                [
                    "2020/10/11",
                    23
                ],
                [
                    "2020/10/12",
                    21
                ],
                [
                    "2020/10/13",
                    30
                ],
                [
                    "2020/10/14",
                    30
                ],
                [
                    "2020/10/15",
                    28
                ],
                [
                    "2020/10/16",
                    29
                ],
                [
                    "2020/10/17",
                    35
                ],
                [
                    "2020/10/18",
                    36
                ],
                [
                    "2020/10/19",
                    33
                ],
                [
                    "2020/10/20",
                    29
                ],
                [
                    "2020/10/21",
                    35
                ],
                [
                    "2020/10/22",
                    37
                ],
                [
                    "2020/10/23",
                    39
                ],
                [
                    "2020/10/24",
                    34
                ],
                [
                    "2020/10/25",
                    36
                ],
                [
                    "2020/10/26",
                    35
                ],
                [
                    "2020/10/27",
                    42
                ],
                [
                    "2020/10/28",
                    39
                ],
                [
                    "2020/10/29",
                    42
                ],
                [
                    "2020/10/30",
                    43
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "normal": {
                    "width": 4,
                    "shadowColor": "rgba(155, 18, 184, .3)",
                    "shadowBlur": 10,
                    "shadowOffsetY": 10,
                    "shadowOffsetX": 10,
                    "curve": 0.5
                }
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        },
        {
            "type": "line",
            "name": "IOS",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": false,
            "smooth": true,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    25
                ],
                [
                    "2020/10/2",
                    26
                ],
                [
                    "2020/10/3",
                    23
                ],
                [
                    "2020/10/4",
                    24
                ],
                [
                    "2020/10/5",
                    24
                ],
                [
                    "2020/10/6",
                    22
                ],
                [
                    "2020/10/7",
                    29
                ],
                [
                    "2020/10/8",
                    29
                ],
                [
                    "2020/10/9",
                    33
                ],
                [
                    "2020/10/10",
                    28
                ],
                [
                    "2020/10/11",
                    27
                ],
                [
                    "2020/10/12",
                    26
                ],
                [
                    "2020/10/13",
                    36
                ],
                [
                    "2020/10/14",
                    35
                ],
                [
                    "2020/10/15",
                    29
                ],
                [
                    "2020/10/16",
                    33
                ],
                [
                    "2020/10/17",
                    40
                ],
                [
                    "2020/10/18",
                    42
                ],
                [
                    "2020/10/19",
                    39
                ],
                [
                    "2020/10/20",
                    43
                ],
                [
                    "2020/10/21",
                    41
                ],
                [
                    "2020/10/22",
                    44
                ],
                [
                    "2020/10/23",
                    37
                ],
                [
                    "2020/10/24",
                    43
                ],
                [
                    "2020/10/25",
                    45
                ],
                [
                    "2020/10/26",
                    47
                ],
                [
                    "2020/10/27",
                    47
                ],
                [
                    "2020/10/28",
                    46
                ],
                [
                    "2020/10/29",
                    49
                ],
                [
                    "2020/10/30",
                    52
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "normal": {
                    "width": 4,
                    "shadowColor": "rgba(155, 18, 184, .3)",
                    "shadowBlur": 10,
                    "shadowOffsetY": 10,
                    "shadowOffsetX": 10,
                    "curve": 0.5
                }
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        }
    ],
    "legend": [
        {
            "data": [
                "Android",
                "IOS"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "text": "\u7ec8\u7aef\u65e5\u6d3b\u8d8b\u52bf",
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_221039faa93b4fad82fd9f62839fccb0.setOption(option_221039faa93b4fad82fd9f62839fccb0);
    </script>
</body>
</html>




#### 25.折线图平滑处理


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def line_with_smooth_connect():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(Faker.choose())
    # 设置is_smooth=True来平滑曲线
    line.add_yaxis('平滑曲线', Faker.values(), is_smooth=True)
    line.add_yaxis('直线', Faker.values(), is_smooth=False)

    return line


chart = line_with_smooth_connect()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="d87925855806453cb2cdf3bcd45fa463" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_d87925855806453cb2cdf3bcd45fa463 = echarts.init(
            document.getElementById('d87925855806453cb2cdf3bcd45fa463'), 'light', {renderer: 'canvas'});
        var option_d87925855806453cb2cdf3bcd45fa463 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "name": "\u5e73\u6ed1\u66f2\u7ebf",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": true,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u6cb3\u9a6c",
                    26
                ],
                [
                    "\u87d2\u86c7",
                    123
                ],
                [
                    "\u8001\u864e",
                    46
                ],
                [
                    "\u5927\u8c61",
                    62
                ],
                [
                    "\u5154\u5b50",
                    59
                ],
                [
                    "\u718a\u732b",
                    20
                ],
                [
                    "\u72ee\u5b50",
                    138
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        },
        {
            "type": "line",
            "name": "\u76f4\u7ebf",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u6cb3\u9a6c",
                    89
                ],
                [
                    "\u87d2\u86c7",
                    127
                ],
                [
                    "\u8001\u864e",
                    69
                ],
                [
                    "\u5927\u8c61",
                    31
                ],
                [
                    "\u5154\u5b50",
                    147
                ],
                [
                    "\u718a\u732b",
                    84
                ],
                [
                    "\u72ee\u5b50",
                    42
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        }
    ],
    "legend": [
        {
            "data": [
                "\u5e73\u6ed1\u66f2\u7ebf",
                "\u76f4\u7ebf"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u6cb3\u9a6c",
                "\u87d2\u86c7",
                "\u8001\u864e",
                "\u5927\u8c61",
                "\u5154\u5b50",
                "\u718a\u732b",
                "\u72ee\u5b50"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_d87925855806453cb2cdf3bcd45fa463.setOption(option_d87925855806453cb2cdf3bcd45fa463);
    </script>
</body>
</html>




#### 26. 直方图带标记线(最大值，平均值等)


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def bar_with_guide_line():
    bar = Bar(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis('A', Faker.values())
    bar.add_yaxis('B', Faker.values())
    # 设置标记线
    bar.set_series_opts(
        markline_opts=opts.MarkLineOpts(
            data=[
                opts.MarkLineItem(type_="min", name="最小值"),
                opts.MarkLineItem(type_="max", name="最大值"),
                opts.MarkLineItem(type_="average", name="平均值"),
            ]
        )
    )

    return bar


chart = bar_with_guide_line()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="6bf3f39554574835aa63295c41a3d8f9" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_6bf3f39554574835aa63295c41a3d8f9 = echarts.init(
            document.getElementById('6bf3f39554574835aa63295c41a3d8f9'), 'light', {renderer: 'canvas'});
        var option_6bf3f39554574835aa63295c41a3d8f9 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "bar",
            "name": "A",
            "legendHoverLink": true,
            "data": [
                67,
                82,
                135,
                136,
                90,
                65,
                107
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "markLine": {
                "silent": false,
                "precision": 2,
                "label": {
                    "show": true,
                    "margin": 8,
                    "valueAnimation": false
                },
                "data": [
                    {
                        "name": "\u6700\u5c0f\u503c",
                        "type": "min"
                    },
                    {
                        "name": "\u6700\u5927\u503c",
                        "type": "max"
                    },
                    {
                        "name": "\u5e73\u5747\u503c",
                        "type": "average"
                    }
                ]
            },
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        },
        {
            "type": "bar",
            "name": "B",
            "legendHoverLink": true,
            "data": [
                130,
                52,
                46,
                140,
                34,
                108,
                134
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "markLine": {
                "silent": false,
                "precision": 2,
                "label": {
                    "show": true,
                    "margin": 8,
                    "valueAnimation": false
                },
                "data": [
                    {
                        "name": "\u6700\u5c0f\u503c",
                        "type": "min"
                    },
                    {
                        "name": "\u6700\u5927\u503c",
                        "type": "max"
                    },
                    {
                        "name": "\u5e73\u5747\u503c",
                        "type": "average"
                    }
                ]
            },
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A",
                "B"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5468\u4e00",
                "\u5468\u4e8c",
                "\u5468\u4e09",
                "\u5468\u56db",
                "\u5468\u4e94",
                "\u5468\u516d",
                "\u5468\u65e5"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_6bf3f39554574835aa63295c41a3d8f9.setOption(option_6bf3f39554574835aa63295c41a3d8f9);
    </script>
</body>
</html>




#### 27.折线图带自定义标记点


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data = [i + random.randint(10, 20) for i in range(len(x_data))]


def line_with_custom_mark_point():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data)
    line.add_yaxis('', y_data)
    # 自定义标记点
    line.set_series_opts(
        markpoint_opts=opts.MarkPointOpts(
            data=[opts.MarkPointItem(name="自定义标记点", coord=[x_data[2], y_data[2]], value=y_data[2])]
        )
    )

    return line


chart = line_with_custom_mark_point()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="b882d32e72d9439691e5559d438b9c40" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_b882d32e72d9439691e5559d438b9c40 = echarts.init(
            document.getElementById('b882d32e72d9439691e5559d438b9c40'), 'light', {renderer: 'canvas'});
        var option_b882d32e72d9439691e5559d438b9c40 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    20
                ],
                [
                    "2020/10/2",
                    19
                ],
                [
                    "2020/10/3",
                    20
                ],
                [
                    "2020/10/4",
                    17
                ],
                [
                    "2020/10/5",
                    21
                ],
                [
                    "2020/10/6",
                    19
                ],
                [
                    "2020/10/7",
                    21
                ],
                [
                    "2020/10/8",
                    17
                ],
                [
                    "2020/10/9",
                    20
                ],
                [
                    "2020/10/10",
                    22
                ],
                [
                    "2020/10/11",
                    26
                ],
                [
                    "2020/10/12",
                    28
                ],
                [
                    "2020/10/13",
                    29
                ],
                [
                    "2020/10/14",
                    25
                ],
                [
                    "2020/10/15",
                    32
                ],
                [
                    "2020/10/16",
                    26
                ],
                [
                    "2020/10/17",
                    29
                ],
                [
                    "2020/10/18",
                    27
                ],
                [
                    "2020/10/19",
                    34
                ],
                [
                    "2020/10/20",
                    37
                ],
                [
                    "2020/10/21",
                    33
                ],
                [
                    "2020/10/22",
                    33
                ],
                [
                    "2020/10/23",
                    40
                ],
                [
                    "2020/10/24",
                    35
                ],
                [
                    "2020/10/25",
                    44
                ],
                [
                    "2020/10/26",
                    36
                ],
                [
                    "2020/10/27",
                    41
                ],
                [
                    "2020/10/28",
                    42
                ],
                [
                    "2020/10/29",
                    38
                ],
                [
                    "2020/10/30",
                    39
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "markPoint": {
                "label": {
                    "show": true,
                    "position": "inside",
                    "color": "#fff",
                    "margin": 8,
                    "valueAnimation": false
                },
                "data": [
                    {
                        "name": "\u81ea\u5b9a\u4e49\u6807\u8bb0\u70b9",
                        "coord": [
                            "2020/10/3",
                            20
                        ],
                        "value": 20
                    }
                ]
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_b882d32e72d9439691e5559d438b9c40.setOption(option_b882d32e72d9439691e5559d438b9c40);
    </script>
</body>
</html>




#### 28.折线图带标记区域


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = ["2020/10/{}".format(i + 1) for i in range(30)]

# 随机生成点数据
y_data = [i + random.randint(10, 20) for i in range(len(x_data))]


def line_with_mark_area():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data)
    line.add_yaxis('', y_data)
    # 设置标记区域
    line.set_series_opts(
        markarea_opts=opts.MarkAreaOpts(
            data=[
                opts.MarkAreaItem(name="黄金周", x=("2020/10/1", "2020/10/8"))
            ]
        )
    )

    return line


chart = line_with_mark_area()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="7bc50ee946254efcb236793a09b5ea03" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_7bc50ee946254efcb236793a09b5ea03 = echarts.init(
            document.getElementById('7bc50ee946254efcb236793a09b5ea03'), 'light', {renderer: 'canvas'});
        var option_7bc50ee946254efcb236793a09b5ea03 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "2020/10/1",
                    20
                ],
                [
                    "2020/10/2",
                    19
                ],
                [
                    "2020/10/3",
                    22
                ],
                [
                    "2020/10/4",
                    13
                ],
                [
                    "2020/10/5",
                    18
                ],
                [
                    "2020/10/6",
                    25
                ],
                [
                    "2020/10/7",
                    26
                ],
                [
                    "2020/10/8",
                    20
                ],
                [
                    "2020/10/9",
                    26
                ],
                [
                    "2020/10/10",
                    19
                ],
                [
                    "2020/10/11",
                    30
                ],
                [
                    "2020/10/12",
                    31
                ],
                [
                    "2020/10/13",
                    31
                ],
                [
                    "2020/10/14",
                    23
                ],
                [
                    "2020/10/15",
                    34
                ],
                [
                    "2020/10/16",
                    28
                ],
                [
                    "2020/10/17",
                    29
                ],
                [
                    "2020/10/18",
                    37
                ],
                [
                    "2020/10/19",
                    29
                ],
                [
                    "2020/10/20",
                    38
                ],
                [
                    "2020/10/21",
                    34
                ],
                [
                    "2020/10/22",
                    34
                ],
                [
                    "2020/10/23",
                    41
                ],
                [
                    "2020/10/24",
                    36
                ],
                [
                    "2020/10/25",
                    40
                ],
                [
                    "2020/10/26",
                    36
                ],
                [
                    "2020/10/27",
                    36
                ],
                [
                    "2020/10/28",
                    39
                ],
                [
                    "2020/10/29",
                    40
                ],
                [
                    "2020/10/30",
                    43
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "markArea": {
                "silent": false,
                "label": {
                    "show": true,
                    "margin": 8,
                    "valueAnimation": false
                },
                "data": [
                    [
                        {
                            "name": "\u9ec4\u91d1\u5468",
                            "xAxis": "2020/10/1"
                        },
                        {
                            "xAxis": "2020/10/8"
                        }
                    ]
                ]
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "2020/10/1",
                "2020/10/2",
                "2020/10/3",
                "2020/10/4",
                "2020/10/5",
                "2020/10/6",
                "2020/10/7",
                "2020/10/8",
                "2020/10/9",
                "2020/10/10",
                "2020/10/11",
                "2020/10/12",
                "2020/10/13",
                "2020/10/14",
                "2020/10/15",
                "2020/10/16",
                "2020/10/17",
                "2020/10/18",
                "2020/10/19",
                "2020/10/20",
                "2020/10/21",
                "2020/10/22",
                "2020/10/23",
                "2020/10/24",
                "2020/10/25",
                "2020/10/26",
                "2020/10/27",
                "2020/10/28",
                "2020/10/29",
                "2020/10/30"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_7bc50ee946254efcb236793a09b5ea03.setOption(option_7bc50ee946254efcb236793a09b5ea03);
    </script>
</body>
</html>




#### 29.折线图带百分号显示


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.commons.utils import JsCode


x_data = ['Apple', 'Huawei', 'Xiaomi', 'Oppo', 'Vivo', 'Meizu']
y_data = [0.98, 0.89, 0.92, 1.07, 0.81, 1.23]

js = """function (param) {return param.name +':'+ Math.floor(param.value[1])+'%';}"""


def line_with_per_show():
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='1000px',
                                        height='600px'))
    line.add_xaxis(x_data)
    # 传入数据时先乘以100
    line.add_yaxis('', [round(v * 100, 0) for v in y_data])
    # 执行js代码让%显示
    line.set_series_opts(label_opts=opts.LabelOpts(is_show=True,
                                                   formatter=JsCode(js)))

    return line


chart = line_with_per_show()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="d100f6bdb98e406ca8b4b62687325c76" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_d100f6bdb98e406ca8b4b62687325c76 = echarts.init(
            document.getElementById('d100f6bdb98e406ca8b4b62687325c76'), 'light', {renderer: 'canvas'});
        var option_d100f6bdb98e406ca8b4b62687325c76 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "line",
            "connectNulls": false,
            "xAxisIndex": 0,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "Apple",
                    98.0
                ],
                [
                    "Huawei",
                    89.0
                ],
                [
                    "Xiaomi",
                    92.0
                ],
                [
                    "Oppo",
                    107.0
                ],
                [
                    "Vivo",
                    81.0
                ],
                [
                    "Meizu",
                    123.0
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "formatter": function (param) {return param.name +':'+ Math.floor(param.value[1])+'%';},
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0,
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "Apple",
                "Huawei",
                "Xiaomi",
                "Oppo",
                "Vivo",
                "Meizu"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_d100f6bdb98e406ca8b4b62687325c76.setOption(option_d100f6bdb98e406ca8b4b62687325c76);
    </script>
</body>
</html>




#### 30.象形图自定义图形


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def pictorialbar_with_custom_symbol():
    pictorialbar = PictorialBar(init_opts=opts.InitOpts(theme='light',
                                                        width='1000px',
                                                        height='600px'))
    pictorialbar.add_xaxis(Faker.choose())
    pictorialbar.add_yaxis('A',
                           Faker.values(),
                           symbol_size=20,
                           # 自定义图形
                           symbol='path://M100,0 L41.22,180.90 L195.10,69.09 L4.89,69.09 L158.77,180.90 z',
                           symbol_repeat="fixed",
                           is_symbol_clip=True
                           )

    return pictorialbar


chart = pictorialbar_with_custom_symbol()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="eee2640e053142f0a7e9e6ccfa8c74f3" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_eee2640e053142f0a7e9e6ccfa8c74f3 = echarts.init(
            document.getElementById('eee2640e053142f0a7e9e6ccfa8c74f3'), 'light', {renderer: 'canvas'});
        var option_eee2640e053142f0a7e9e6ccfa8c74f3 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "pictorialBar",
            "symbol": "path://M100,0 L41.22,180.90 L195.10,69.09 L4.89,69.09 L158.77,180.90 z",
            "symbolSize": 20,
            "symbolRepeat": "fixed",
            "symbolClip": true,
            "name": "A",
            "data": [
                83,
                76,
                37,
                134,
                143,
                109,
                30
            ],
            "barCategoryGap": "20%",
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "A"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u53ef\u4e50",
                "\u96ea\u78a7",
                "\u6a59\u6c41",
                "\u7eff\u8336",
                "\u5976\u8336",
                "\u767e\u5a01",
                "\u9752\u5c9b"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ]
};
        chart_eee2640e053142f0a7e9e6ccfa8c74f3.setOption(option_eee2640e053142f0a7e9e6ccfa8c74f3);
    </script>
</body>
</html>




#### 31.水球图自定义图形


```python
from pyecharts.charts import *
from pyecharts import options as opts

ios_icon = 'path://M24.734 17.003c-0.040-4.053 3.305-5.996 3.454-6.093-1.88-2.751-4.808-3.127-5.851-3.171-2.492-0.252-4.862 1.467-6.127 1.467-1.261 0-3.213-1.43-5.28-1.392-2.716 0.040-5.221 1.579-6.619 4.012-2.822 4.897-0.723 12.151 2.028 16.123 1.344 1.944 2.947 4.127 5.051 4.049 2.026-0.081 2.793-1.311 5.242-1.311s3.138 1.311 5.283 1.271c2.18-0.041 3.562-1.981 4.897-3.931 1.543-2.255 2.179-4.439 2.216-4.551-0.048-0.022-4.252-1.632-4.294-6.473zM20.705 5.11c1.117-1.355 1.871-3.235 1.665-5.11-1.609 0.066-3.559 1.072-4.713 2.423-1.036 1.199-1.942 3.113-1.699 4.951 1.796 0.14 3.629-0.913 4.747-2.264z'


def liquid_with_custom_shape():
    liquid = Liquid(init_opts=opts.InitOpts(theme='light',
                                            width='1000px',
                                            height='600px'))
    liquid.add('', [0.4, 0.5], shape=ios_icon)

    return liquid


chart = liquid_with_custom_shape()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts-liquidfill.min.js"></script>


</head>
<body >
    <div id="5a93664f7fda46628326fc5015142687" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_5a93664f7fda46628326fc5015142687 = echarts.init(
            document.getElementById('5a93664f7fda46628326fc5015142687'), 'light', {renderer: 'canvas'});
        var option_5a93664f7fda46628326fc5015142687 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "liquidFill",
            "data": [
                0.4,
                0.5
            ],
            "waveAnimation": true,
            "animationDuration": 2000,
            "animationDurationUpdate": 1000,
            "color": [
                "#294D99",
                "#156ACF",
                "#1598ED",
                "#45BDFF"
            ],
            "shape": "path://M24.734 17.003c-0.040-4.053 3.305-5.996 3.454-6.093-1.88-2.751-4.808-3.127-5.851-3.171-2.492-0.252-4.862 1.467-6.127 1.467-1.261 0-3.213-1.43-5.28-1.392-2.716 0.040-5.221 1.579-6.619 4.012-2.822 4.897-0.723 12.151 2.028 16.123 1.344 1.944 2.947 4.127 5.051 4.049 2.026-0.081 2.793-1.311 5.242-1.311s3.138 1.311 5.283 1.271c2.18-0.041 3.562-1.981 4.897-3.931 1.543-2.255 2.179-4.439 2.216-4.551-0.048-0.022-4.252-1.632-4.294-6.473zM20.705 5.11c1.117-1.355 1.871-3.235 1.665-5.11-1.609 0.066-3.559 1.072-4.713 2.423-1.036 1.199-1.942 3.113-1.699 4.951 1.796 0.14 3.629-0.913 4.747-2.264z",
            "backgroundStyle": {},
            "outline": {
                "show": true,
                "borderDistance": 8
            },
            "label": {
                "show": true,
                "position": "inside",
                "margin": 8,
                "fontSize": 50,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    }
};
        chart_5a93664f7fda46628326fc5015142687.setOption(option_5a93664f7fda46628326fc5015142687);
    </script>
</body>
</html>




#### 32.日历图自定义cell


```python
from pyecharts.charts import *
from pyecharts import options as opts
import datetime

# 美国covid确诊数据
data = [(datetime.datetime(2020, 1, 21, 0, 0), 1), (datetime.datetime(2020, 1, 22, 0, 0), 1),
        (datetime.datetime(2020, 1, 23, 0, 0), 1), (datetime.datetime(2020, 1, 24, 0, 0), 2),
        (datetime.datetime(2020, 1, 25, 0, 0), 2), (datetime.datetime(2020, 1, 26, 0, 0), 5),
        (datetime.datetime(2020, 1, 27, 0, 0), 5), (datetime.datetime(2020, 1, 28, 0, 0), 5),
        (datetime.datetime(2020, 1, 29, 0, 0), 5), (datetime.datetime(2020, 1, 30, 0, 0), 5),
        (datetime.datetime(2020, 1, 31, 0, 0), 7), (datetime.datetime(2020, 2, 1, 0, 0), 8),
        (datetime.datetime(2020, 2, 2, 0, 0), 8), (datetime.datetime(2020, 2, 3, 0, 0), 11),
        (datetime.datetime(2020, 2, 4, 0, 0), 11), (datetime.datetime(2020, 2, 5, 0, 0), 11),
        (datetime.datetime(2020, 2, 6, 0, 0), 11), (datetime.datetime(2020, 2, 7, 0, 0), 11),
        (datetime.datetime(2020, 2, 8, 0, 0), 11), (datetime.datetime(2020, 2, 9, 0, 0), 11),
        (datetime.datetime(2020, 2, 10, 0, 0), 11), (datetime.datetime(2020, 2, 11, 0, 0), 12),
        (datetime.datetime(2020, 2, 12, 0, 0), 12), (datetime.datetime(2020, 2, 13, 0, 0), 13),
        (datetime.datetime(2020, 2, 14, 0, 0), 13), (datetime.datetime(2020, 2, 15, 0, 0), 13),
        (datetime.datetime(2020, 2, 16, 0, 0), 13), (datetime.datetime(2020, 2, 17, 0, 0), 13),
        (datetime.datetime(2020, 2, 18, 0, 0), 13), (datetime.datetime(2020, 2, 19, 0, 0), 13),
        (datetime.datetime(2020, 2, 20, 0, 0), 13), (datetime.datetime(2020, 2, 21, 0, 0), 15),
        (datetime.datetime(2020, 2, 22, 0, 0), 15), (datetime.datetime(2020, 2, 23, 0, 0), 15),
        (datetime.datetime(2020, 2, 24, 0, 0), 15), (datetime.datetime(2020, 2, 25, 0, 0), 15),
        (datetime.datetime(2020, 2, 26, 0, 0), 15), (datetime.datetime(2020, 2, 27, 0, 0), 16),
        (datetime.datetime(2020, 2, 28, 0, 0), 16), (datetime.datetime(2020, 2, 29, 0, 0), 24),
        (datetime.datetime(2020, 3, 1, 0, 0), 30), (datetime.datetime(2020, 3, 2, 0, 0), 53),
        (datetime.datetime(2020, 3, 3, 0, 0), 73), (datetime.datetime(2020, 3, 4, 0, 0), 104),
        (datetime.datetime(2020, 3, 5, 0, 0), 174), (datetime.datetime(2020, 3, 6, 0, 0), 222),
        (datetime.datetime(2020, 3, 7, 0, 0), 337), (datetime.datetime(2020, 3, 8, 0, 0), 451),
        (datetime.datetime(2020, 3, 9, 0, 0), 519), (datetime.datetime(2020, 3, 10, 0, 0), 711),
        (datetime.datetime(2020, 3, 11, 0, 0), 1109), (datetime.datetime(2020, 3, 12, 0, 0), 1561),
        (datetime.datetime(2020, 3, 13, 0, 0), 2157), (datetime.datetime(2020, 3, 14, 0, 0), 2870),
        (datetime.datetime(2020, 3, 15, 0, 0), 2968), (datetime.datetime(2020, 3, 16, 0, 0), 4360),
        (datetime.datetime(2020, 3, 17, 0, 0), 6141), (datetime.datetime(2020, 3, 18, 0, 0), 8914),
        (datetime.datetime(2020, 3, 19, 0, 0), 14153), (datetime.datetime(2020, 3, 20, 0, 0), 19479),
        (datetime.datetime(2020, 3, 21, 0, 0), 25818), (datetime.datetime(2020, 3, 22, 0, 0), 33756),
        (datetime.datetime(2020, 3, 23, 0, 0), 43845), (datetime.datetime(2020, 3, 24, 0, 0), 54108),
        (datetime.datetime(2020, 3, 25, 0, 0), 66044), (datetime.datetime(2020, 3, 26, 0, 0), 84080),
        (datetime.datetime(2020, 3, 27, 0, 0), 102254), (datetime.datetime(2020, 3, 28, 0, 0), 122054),
        (datetime.datetime(2020, 3, 29, 0, 0), 141194), (datetime.datetime(2020, 3, 30, 0, 0), 162690),
        (datetime.datetime(2020, 3, 31, 0, 0), 188701), (datetime.datetime(2020, 4, 1, 0, 0), 214194),
        (datetime.datetime(2020, 4, 2, 0, 0), 244593), (datetime.datetime(2020, 4, 3, 0, 0), 276535),
        (datetime.datetime(2020, 4, 4, 0, 0), 309699), (datetime.datetime(2020, 4, 5, 0, 0), 337573),
        (datetime.datetime(2020, 4, 6, 0, 0), 367210), (datetime.datetime(2020, 4, 7, 0, 0), 397992),
        (datetime.datetime(2020, 4, 8, 0, 0), 429686), (datetime.datetime(2020, 4, 9, 0, 0), 464442),
        (datetime.datetime(2020, 4, 10, 0, 0), 497943), (datetime.datetime(2020, 4, 11, 0, 0), 527958),
        (datetime.datetime(2020, 4, 12, 0, 0), 556517), (datetime.datetime(2020, 4, 13, 0, 0), 581810),
        (datetime.datetime(2020, 4, 14, 0, 0), 608845), (datetime.datetime(2020, 4, 15, 0, 0), 637974),
        (datetime.datetime(2020, 4, 16, 0, 0), 669272), (datetime.datetime(2020, 4, 17, 0, 0), 701996),
        (datetime.datetime(2020, 4, 18, 0, 0), 730317), (datetime.datetime(2020, 4, 19, 0, 0), 756375),
        (datetime.datetime(2020, 4, 20, 0, 0), 783716), (datetime.datetime(2020, 4, 21, 0, 0), 809213),
        (datetime.datetime(2020, 4, 22, 0, 0), 837414), (datetime.datetime(2020, 4, 23, 0, 0), 871617),
        (datetime.datetime(2020, 4, 24, 0, 0), 907908), (datetime.datetime(2020, 4, 25, 0, 0), 940829),
        (datetime.datetime(2020, 4, 26, 0, 0), 968517), (datetime.datetime(2020, 4, 27, 0, 0), 990993),
        (datetime.datetime(2020, 4, 28, 0, 0), 1015518), (datetime.datetime(2020, 4, 29, 0, 0), 1042926),
        (datetime.datetime(2020, 4, 30, 0, 0), 1072667)]


def calendar_custom_cell():
    calendar = Calendar(init_opts=opts.InitOpts(theme='light',
                                                width='1000px',
                                                height='600px'))
    calendar.add('确证人数',
                 yaxis_data=data,
                 label_opts=opts.LabelOpts(is_show=True),
                 calendar_opts=opts.CalendarOpts(
                     # 日历位置
                     pos_top='10%',
                     pos_left='10%',
                     # 日期范围
                     range_=['2020-01-21', '2020-04-30'],
                     # 日历单元格尺寸
                     cell_size=50,
                     # 年月日标签样式设置
                     yearlabel_opts=opts.CalendarYearLabelOpts(margin=40,
                                                               label_font_size=20,
                                                               label_color='rgba(130,134,112,0.8)'),
                     daylabel_opts=opts.CalendarDayLabelOpts(label_color='#778633', label_font_weight='bold'),
                     monthlabel_opts=opts.CalendarMonthLabelOpts(label_color='#778633', label_font_weight='bold')
                 )
                 )
    # 设置视觉组件
    calendar.set_global_opts(visualmap_opts=opts.VisualMapOpts(
        max_=1000000,
        is_piecewise=True,
        pieces=[{"min": 1000000},
                {"min": 10000, "max": 1000000},
                {"min": 100, "max": 10000},
                {"max": 100}],
        range_color=["#CCD3D9", "#E6B6C2", "#D4587A", "#DC364C"]
    ))
    return calendar


chart = calendar_custom_cell()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="fe3679032c204b0ba007e6bdf1fa731f" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_fe3679032c204b0ba007e6bdf1fa731f = echarts.init(
            document.getElementById('fe3679032c204b0ba007e6bdf1fa731f'), 'light', {renderer: 'canvas'});
        var option_fe3679032c204b0ba007e6bdf1fa731f = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "heatmap",
            "coordinateSystem": "calendar",
            "name": "\u786e\u8bc1\u4eba\u6570",
            "data": [
                [
                    "2020-01-21T00:00:00",
                    1
                ],
                [
                    "2020-01-22T00:00:00",
                    1
                ],
                [
                    "2020-01-23T00:00:00",
                    1
                ],
                [
                    "2020-01-24T00:00:00",
                    2
                ],
                [
                    "2020-01-25T00:00:00",
                    2
                ],
                [
                    "2020-01-26T00:00:00",
                    5
                ],
                [
                    "2020-01-27T00:00:00",
                    5
                ],
                [
                    "2020-01-28T00:00:00",
                    5
                ],
                [
                    "2020-01-29T00:00:00",
                    5
                ],
                [
                    "2020-01-30T00:00:00",
                    5
                ],
                [
                    "2020-01-31T00:00:00",
                    7
                ],
                [
                    "2020-02-01T00:00:00",
                    8
                ],
                [
                    "2020-02-02T00:00:00",
                    8
                ],
                [
                    "2020-02-03T00:00:00",
                    11
                ],
                [
                    "2020-02-04T00:00:00",
                    11
                ],
                [
                    "2020-02-05T00:00:00",
                    11
                ],
                [
                    "2020-02-06T00:00:00",
                    11
                ],
                [
                    "2020-02-07T00:00:00",
                    11
                ],
                [
                    "2020-02-08T00:00:00",
                    11
                ],
                [
                    "2020-02-09T00:00:00",
                    11
                ],
                [
                    "2020-02-10T00:00:00",
                    11
                ],
                [
                    "2020-02-11T00:00:00",
                    12
                ],
                [
                    "2020-02-12T00:00:00",
                    12
                ],
                [
                    "2020-02-13T00:00:00",
                    13
                ],
                [
                    "2020-02-14T00:00:00",
                    13
                ],
                [
                    "2020-02-15T00:00:00",
                    13
                ],
                [
                    "2020-02-16T00:00:00",
                    13
                ],
                [
                    "2020-02-17T00:00:00",
                    13
                ],
                [
                    "2020-02-18T00:00:00",
                    13
                ],
                [
                    "2020-02-19T00:00:00",
                    13
                ],
                [
                    "2020-02-20T00:00:00",
                    13
                ],
                [
                    "2020-02-21T00:00:00",
                    15
                ],
                [
                    "2020-02-22T00:00:00",
                    15
                ],
                [
                    "2020-02-23T00:00:00",
                    15
                ],
                [
                    "2020-02-24T00:00:00",
                    15
                ],
                [
                    "2020-02-25T00:00:00",
                    15
                ],
                [
                    "2020-02-26T00:00:00",
                    15
                ],
                [
                    "2020-02-27T00:00:00",
                    16
                ],
                [
                    "2020-02-28T00:00:00",
                    16
                ],
                [
                    "2020-02-29T00:00:00",
                    24
                ],
                [
                    "2020-03-01T00:00:00",
                    30
                ],
                [
                    "2020-03-02T00:00:00",
                    53
                ],
                [
                    "2020-03-03T00:00:00",
                    73
                ],
                [
                    "2020-03-04T00:00:00",
                    104
                ],
                [
                    "2020-03-05T00:00:00",
                    174
                ],
                [
                    "2020-03-06T00:00:00",
                    222
                ],
                [
                    "2020-03-07T00:00:00",
                    337
                ],
                [
                    "2020-03-08T00:00:00",
                    451
                ],
                [
                    "2020-03-09T00:00:00",
                    519
                ],
                [
                    "2020-03-10T00:00:00",
                    711
                ],
                [
                    "2020-03-11T00:00:00",
                    1109
                ],
                [
                    "2020-03-12T00:00:00",
                    1561
                ],
                [
                    "2020-03-13T00:00:00",
                    2157
                ],
                [
                    "2020-03-14T00:00:00",
                    2870
                ],
                [
                    "2020-03-15T00:00:00",
                    2968
                ],
                [
                    "2020-03-16T00:00:00",
                    4360
                ],
                [
                    "2020-03-17T00:00:00",
                    6141
                ],
                [
                    "2020-03-18T00:00:00",
                    8914
                ],
                [
                    "2020-03-19T00:00:00",
                    14153
                ],
                [
                    "2020-03-20T00:00:00",
                    19479
                ],
                [
                    "2020-03-21T00:00:00",
                    25818
                ],
                [
                    "2020-03-22T00:00:00",
                    33756
                ],
                [
                    "2020-03-23T00:00:00",
                    43845
                ],
                [
                    "2020-03-24T00:00:00",
                    54108
                ],
                [
                    "2020-03-25T00:00:00",
                    66044
                ],
                [
                    "2020-03-26T00:00:00",
                    84080
                ],
                [
                    "2020-03-27T00:00:00",
                    102254
                ],
                [
                    "2020-03-28T00:00:00",
                    122054
                ],
                [
                    "2020-03-29T00:00:00",
                    141194
                ],
                [
                    "2020-03-30T00:00:00",
                    162690
                ],
                [
                    "2020-03-31T00:00:00",
                    188701
                ],
                [
                    "2020-04-01T00:00:00",
                    214194
                ],
                [
                    "2020-04-02T00:00:00",
                    244593
                ],
                [
                    "2020-04-03T00:00:00",
                    276535
                ],
                [
                    "2020-04-04T00:00:00",
                    309699
                ],
                [
                    "2020-04-05T00:00:00",
                    337573
                ],
                [
                    "2020-04-06T00:00:00",
                    367210
                ],
                [
                    "2020-04-07T00:00:00",
                    397992
                ],
                [
                    "2020-04-08T00:00:00",
                    429686
                ],
                [
                    "2020-04-09T00:00:00",
                    464442
                ],
                [
                    "2020-04-10T00:00:00",
                    497943
                ],
                [
                    "2020-04-11T00:00:00",
                    527958
                ],
                [
                    "2020-04-12T00:00:00",
                    556517
                ],
                [
                    "2020-04-13T00:00:00",
                    581810
                ],
                [
                    "2020-04-14T00:00:00",
                    608845
                ],
                [
                    "2020-04-15T00:00:00",
                    637974
                ],
                [
                    "2020-04-16T00:00:00",
                    669272
                ],
                [
                    "2020-04-17T00:00:00",
                    701996
                ],
                [
                    "2020-04-18T00:00:00",
                    730317
                ],
                [
                    "2020-04-19T00:00:00",
                    756375
                ],
                [
                    "2020-04-20T00:00:00",
                    783716
                ],
                [
                    "2020-04-21T00:00:00",
                    809213
                ],
                [
                    "2020-04-22T00:00:00",
                    837414
                ],
                [
                    "2020-04-23T00:00:00",
                    871617
                ],
                [
                    "2020-04-24T00:00:00",
                    907908
                ],
                [
                    "2020-04-25T00:00:00",
                    940829
                ],
                [
                    "2020-04-26T00:00:00",
                    968517
                ],
                [
                    "2020-04-27T00:00:00",
                    990993
                ],
                [
                    "2020-04-28T00:00:00",
                    1015518
                ],
                [
                    "2020-04-29T00:00:00",
                    1042926
                ],
                [
                    "2020-04-30T00:00:00",
                    1072667
                ]
            ],
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u786e\u8bc1\u4eba\u6570"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "calendar": [
        {
            "zlevel": 0,
            "z": 2,
            "left": "10%",
            "top": "10%",
            "width": "auto",
            "orient": "horizontal",
            "range": [
                "2020-01-21",
                "2020-04-30"
            ],
            "cellSize": 50,
            "dayLabel": {
                "show": true,
                "firstDay": 0,
                "position": "start",
                "nameMap": "en",
                "color": "#778633",
                "fontStyle": "normal",
                "fontWeight": "bold",
                "fontFamily": "sans-serif",
                "fontSize": 12
            },
            "monthLabel": {
                "show": true,
                "position": "start",
                "nameMap": "en",
                "color": "#778633",
                "fontStyle": "normal",
                "fontWeight": "bold",
                "fontFamily": "sans-serif",
                "fontSize": 12
            },
            "yearLabel": {
                "show": true,
                "margin": 40,
                "color": "rgba(130,134,112,0.8)",
                "fontStyle": "normal",
                "fontWeight": "normal",
                "fontFamily": "sans-serif",
                "fontSize": 20
            },
            "silent": false
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": {
        "show": true,
        "type": "piecewise",
        "min": 0,
        "max": 1000000,
        "inRange": {
            "color": [
                "#CCD3D9",
                "#E6B6C2",
                "#D4587A",
                "#DC364C"
            ]
        },
        "calculable": true,
        "inverse": false,
        "splitNumber": 5,
        "hoverLink": true,
        "orient": "vertical",
        "padding": 5,
        "showLabel": true,
        "itemWidth": 20,
        "itemHeight": 14,
        "borderWidth": 0,
        "pieces": [
            {
                "min": 1000000
            },
            {
                "min": 10000,
                "max": 1000000
            },
            {
                "min": 100,
                "max": 10000
            },
            {
                "max": 100
            }
        ]
    }
};
        chart_fe3679032c204b0ba007e6bdf1fa731f.setOption(option_fe3679032c204b0ba007e6bdf1fa731f);
    </script>
</body>
</html>




#### 33.日历图显示中文标签


```python
from pyecharts.charts import *
from pyecharts import options as opts
import datetime

# 美国covid确诊数据
data = [(datetime.datetime(2020, 1, 21, 0, 0), 1), (datetime.datetime(2020, 1, 22, 0, 0), 1),
        (datetime.datetime(2020, 1, 23, 0, 0), 1), (datetime.datetime(2020, 1, 24, 0, 0), 2),
        (datetime.datetime(2020, 1, 25, 0, 0), 2), (datetime.datetime(2020, 1, 26, 0, 0), 5),
        (datetime.datetime(2020, 1, 27, 0, 0), 5), (datetime.datetime(2020, 1, 28, 0, 0), 5),
        (datetime.datetime(2020, 1, 29, 0, 0), 5), (datetime.datetime(2020, 1, 30, 0, 0), 5),
        (datetime.datetime(2020, 1, 31, 0, 0), 7), (datetime.datetime(2020, 2, 1, 0, 0), 8),
        (datetime.datetime(2020, 2, 2, 0, 0), 8), (datetime.datetime(2020, 2, 3, 0, 0), 11),
        (datetime.datetime(2020, 2, 4, 0, 0), 11), (datetime.datetime(2020, 2, 5, 0, 0), 11),
        (datetime.datetime(2020, 2, 6, 0, 0), 11), (datetime.datetime(2020, 2, 7, 0, 0), 11),
        (datetime.datetime(2020, 2, 8, 0, 0), 11), (datetime.datetime(2020, 2, 9, 0, 0), 11),
        (datetime.datetime(2020, 2, 10, 0, 0), 11), (datetime.datetime(2020, 2, 11, 0, 0), 12),
        (datetime.datetime(2020, 2, 12, 0, 0), 12), (datetime.datetime(2020, 2, 13, 0, 0), 13),
        (datetime.datetime(2020, 2, 14, 0, 0), 13), (datetime.datetime(2020, 2, 15, 0, 0), 13),
        (datetime.datetime(2020, 2, 16, 0, 0), 13), (datetime.datetime(2020, 2, 17, 0, 0), 13),
        (datetime.datetime(2020, 2, 18, 0, 0), 13), (datetime.datetime(2020, 2, 19, 0, 0), 13),
        (datetime.datetime(2020, 2, 20, 0, 0), 13), (datetime.datetime(2020, 2, 21, 0, 0), 15),
        (datetime.datetime(2020, 2, 22, 0, 0), 15), (datetime.datetime(2020, 2, 23, 0, 0), 15),
        (datetime.datetime(2020, 2, 24, 0, 0), 15), (datetime.datetime(2020, 2, 25, 0, 0), 15),
        (datetime.datetime(2020, 2, 26, 0, 0), 15), (datetime.datetime(2020, 2, 27, 0, 0), 16),
        (datetime.datetime(2020, 2, 28, 0, 0), 16), (datetime.datetime(2020, 2, 29, 0, 0), 24),
        (datetime.datetime(2020, 3, 1, 0, 0), 30), (datetime.datetime(2020, 3, 2, 0, 0), 53),
        (datetime.datetime(2020, 3, 3, 0, 0), 73), (datetime.datetime(2020, 3, 4, 0, 0), 104),
        (datetime.datetime(2020, 3, 5, 0, 0), 174), (datetime.datetime(2020, 3, 6, 0, 0), 222),
        (datetime.datetime(2020, 3, 7, 0, 0), 337), (datetime.datetime(2020, 3, 8, 0, 0), 451),
        (datetime.datetime(2020, 3, 9, 0, 0), 519), (datetime.datetime(2020, 3, 10, 0, 0), 711),
        (datetime.datetime(2020, 3, 11, 0, 0), 1109), (datetime.datetime(2020, 3, 12, 0, 0), 1561),
        (datetime.datetime(2020, 3, 13, 0, 0), 2157), (datetime.datetime(2020, 3, 14, 0, 0), 2870),
        (datetime.datetime(2020, 3, 15, 0, 0), 2968), (datetime.datetime(2020, 3, 16, 0, 0), 4360),
        (datetime.datetime(2020, 3, 17, 0, 0), 6141), (datetime.datetime(2020, 3, 18, 0, 0), 8914),
        (datetime.datetime(2020, 3, 19, 0, 0), 14153), (datetime.datetime(2020, 3, 20, 0, 0), 19479),
        (datetime.datetime(2020, 3, 21, 0, 0), 25818), (datetime.datetime(2020, 3, 22, 0, 0), 33756),
        (datetime.datetime(2020, 3, 23, 0, 0), 43845), (datetime.datetime(2020, 3, 24, 0, 0), 54108),
        (datetime.datetime(2020, 3, 25, 0, 0), 66044), (datetime.datetime(2020, 3, 26, 0, 0), 84080),
        (datetime.datetime(2020, 3, 27, 0, 0), 102254), (datetime.datetime(2020, 3, 28, 0, 0), 122054),
        (datetime.datetime(2020, 3, 29, 0, 0), 141194), (datetime.datetime(2020, 3, 30, 0, 0), 162690),
        (datetime.datetime(2020, 3, 31, 0, 0), 188701), (datetime.datetime(2020, 4, 1, 0, 0), 214194),
        (datetime.datetime(2020, 4, 2, 0, 0), 244593), (datetime.datetime(2020, 4, 3, 0, 0), 276535),
        (datetime.datetime(2020, 4, 4, 0, 0), 309699), (datetime.datetime(2020, 4, 5, 0, 0), 337573),
        (datetime.datetime(2020, 4, 6, 0, 0), 367210), (datetime.datetime(2020, 4, 7, 0, 0), 397992),
        (datetime.datetime(2020, 4, 8, 0, 0), 429686), (datetime.datetime(2020, 4, 9, 0, 0), 464442),
        (datetime.datetime(2020, 4, 10, 0, 0), 497943), (datetime.datetime(2020, 4, 11, 0, 0), 527958),
        (datetime.datetime(2020, 4, 12, 0, 0), 556517), (datetime.datetime(2020, 4, 13, 0, 0), 581810),
        (datetime.datetime(2020, 4, 14, 0, 0), 608845), (datetime.datetime(2020, 4, 15, 0, 0), 637974),
        (datetime.datetime(2020, 4, 16, 0, 0), 669272), (datetime.datetime(2020, 4, 17, 0, 0), 701996),
        (datetime.datetime(2020, 4, 18, 0, 0), 730317), (datetime.datetime(2020, 4, 19, 0, 0), 756375),
        (datetime.datetime(2020, 4, 20, 0, 0), 783716), (datetime.datetime(2020, 4, 21, 0, 0), 809213),
        (datetime.datetime(2020, 4, 22, 0, 0), 837414), (datetime.datetime(2020, 4, 23, 0, 0), 871617),
        (datetime.datetime(2020, 4, 24, 0, 0), 907908), (datetime.datetime(2020, 4, 25, 0, 0), 940829),
        (datetime.datetime(2020, 4, 26, 0, 0), 968517), (datetime.datetime(2020, 4, 27, 0, 0), 990993),
        (datetime.datetime(2020, 4, 28, 0, 0), 1015518), (datetime.datetime(2020, 4, 29, 0, 0), 1042926),
        (datetime.datetime(2020, 4, 30, 0, 0), 1072667)]


def calendar_in_Chinese():
    calendar = Calendar(init_opts=opts.InitOpts(theme='light',
                                                width='1000px',
                                                height='600px'))
    calendar.add('确诊人数',
                 yaxis_data=data,
                 label_opts=opts.LabelOpts(is_show=True),
                 calendar_opts=opts.CalendarOpts(
                     # 日期范围
                     range_=['2020-01-21', '2020-04-30'],
                     # 日历单元格尺寸
                     cell_size=50,
                     # 年月日标签样式设置
                     # 星期和月份设置为中文显示，默认是英文
                     yearlabel_opts=opts.CalendarYearLabelOpts(margin=50),
                     daylabel_opts=opts.CalendarDayLabelOpts(name_map='cn'),
                     monthlabel_opts=opts.CalendarMonthLabelOpts(name_map='cn')
                 )
                 )
    # 设置视觉组件
    calendar.set_global_opts(visualmap_opts=opts.VisualMapOpts(
        max_=1000000,
        is_piecewise=True,
        pieces=[{"min": 1000000},
                {"min": 10000, "max": 1000000},
                {"min": 100, "max": 10000},
                {"max": 100}],
        range_color=["#CCD3D9", "#E6B6C2", "#D4587A", "#DC364C"]
    ))
    return calendar


chart = calendar_in_Chinese()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="6b9b902a8235459eb4bbb5d7509d1801" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_6b9b902a8235459eb4bbb5d7509d1801 = echarts.init(
            document.getElementById('6b9b902a8235459eb4bbb5d7509d1801'), 'light', {renderer: 'canvas'});
        var option_6b9b902a8235459eb4bbb5d7509d1801 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "heatmap",
            "coordinateSystem": "calendar",
            "name": "\u786e\u8bca\u4eba\u6570",
            "data": [
                [
                    "2020-01-21T00:00:00",
                    1
                ],
                [
                    "2020-01-22T00:00:00",
                    1
                ],
                [
                    "2020-01-23T00:00:00",
                    1
                ],
                [
                    "2020-01-24T00:00:00",
                    2
                ],
                [
                    "2020-01-25T00:00:00",
                    2
                ],
                [
                    "2020-01-26T00:00:00",
                    5
                ],
                [
                    "2020-01-27T00:00:00",
                    5
                ],
                [
                    "2020-01-28T00:00:00",
                    5
                ],
                [
                    "2020-01-29T00:00:00",
                    5
                ],
                [
                    "2020-01-30T00:00:00",
                    5
                ],
                [
                    "2020-01-31T00:00:00",
                    7
                ],
                [
                    "2020-02-01T00:00:00",
                    8
                ],
                [
                    "2020-02-02T00:00:00",
                    8
                ],
                [
                    "2020-02-03T00:00:00",
                    11
                ],
                [
                    "2020-02-04T00:00:00",
                    11
                ],
                [
                    "2020-02-05T00:00:00",
                    11
                ],
                [
                    "2020-02-06T00:00:00",
                    11
                ],
                [
                    "2020-02-07T00:00:00",
                    11
                ],
                [
                    "2020-02-08T00:00:00",
                    11
                ],
                [
                    "2020-02-09T00:00:00",
                    11
                ],
                [
                    "2020-02-10T00:00:00",
                    11
                ],
                [
                    "2020-02-11T00:00:00",
                    12
                ],
                [
                    "2020-02-12T00:00:00",
                    12
                ],
                [
                    "2020-02-13T00:00:00",
                    13
                ],
                [
                    "2020-02-14T00:00:00",
                    13
                ],
                [
                    "2020-02-15T00:00:00",
                    13
                ],
                [
                    "2020-02-16T00:00:00",
                    13
                ],
                [
                    "2020-02-17T00:00:00",
                    13
                ],
                [
                    "2020-02-18T00:00:00",
                    13
                ],
                [
                    "2020-02-19T00:00:00",
                    13
                ],
                [
                    "2020-02-20T00:00:00",
                    13
                ],
                [
                    "2020-02-21T00:00:00",
                    15
                ],
                [
                    "2020-02-22T00:00:00",
                    15
                ],
                [
                    "2020-02-23T00:00:00",
                    15
                ],
                [
                    "2020-02-24T00:00:00",
                    15
                ],
                [
                    "2020-02-25T00:00:00",
                    15
                ],
                [
                    "2020-02-26T00:00:00",
                    15
                ],
                [
                    "2020-02-27T00:00:00",
                    16
                ],
                [
                    "2020-02-28T00:00:00",
                    16
                ],
                [
                    "2020-02-29T00:00:00",
                    24
                ],
                [
                    "2020-03-01T00:00:00",
                    30
                ],
                [
                    "2020-03-02T00:00:00",
                    53
                ],
                [
                    "2020-03-03T00:00:00",
                    73
                ],
                [
                    "2020-03-04T00:00:00",
                    104
                ],
                [
                    "2020-03-05T00:00:00",
                    174
                ],
                [
                    "2020-03-06T00:00:00",
                    222
                ],
                [
                    "2020-03-07T00:00:00",
                    337
                ],
                [
                    "2020-03-08T00:00:00",
                    451
                ],
                [
                    "2020-03-09T00:00:00",
                    519
                ],
                [
                    "2020-03-10T00:00:00",
                    711
                ],
                [
                    "2020-03-11T00:00:00",
                    1109
                ],
                [
                    "2020-03-12T00:00:00",
                    1561
                ],
                [
                    "2020-03-13T00:00:00",
                    2157
                ],
                [
                    "2020-03-14T00:00:00",
                    2870
                ],
                [
                    "2020-03-15T00:00:00",
                    2968
                ],
                [
                    "2020-03-16T00:00:00",
                    4360
                ],
                [
                    "2020-03-17T00:00:00",
                    6141
                ],
                [
                    "2020-03-18T00:00:00",
                    8914
                ],
                [
                    "2020-03-19T00:00:00",
                    14153
                ],
                [
                    "2020-03-20T00:00:00",
                    19479
                ],
                [
                    "2020-03-21T00:00:00",
                    25818
                ],
                [
                    "2020-03-22T00:00:00",
                    33756
                ],
                [
                    "2020-03-23T00:00:00",
                    43845
                ],
                [
                    "2020-03-24T00:00:00",
                    54108
                ],
                [
                    "2020-03-25T00:00:00",
                    66044
                ],
                [
                    "2020-03-26T00:00:00",
                    84080
                ],
                [
                    "2020-03-27T00:00:00",
                    102254
                ],
                [
                    "2020-03-28T00:00:00",
                    122054
                ],
                [
                    "2020-03-29T00:00:00",
                    141194
                ],
                [
                    "2020-03-30T00:00:00",
                    162690
                ],
                [
                    "2020-03-31T00:00:00",
                    188701
                ],
                [
                    "2020-04-01T00:00:00",
                    214194
                ],
                [
                    "2020-04-02T00:00:00",
                    244593
                ],
                [
                    "2020-04-03T00:00:00",
                    276535
                ],
                [
                    "2020-04-04T00:00:00",
                    309699
                ],
                [
                    "2020-04-05T00:00:00",
                    337573
                ],
                [
                    "2020-04-06T00:00:00",
                    367210
                ],
                [
                    "2020-04-07T00:00:00",
                    397992
                ],
                [
                    "2020-04-08T00:00:00",
                    429686
                ],
                [
                    "2020-04-09T00:00:00",
                    464442
                ],
                [
                    "2020-04-10T00:00:00",
                    497943
                ],
                [
                    "2020-04-11T00:00:00",
                    527958
                ],
                [
                    "2020-04-12T00:00:00",
                    556517
                ],
                [
                    "2020-04-13T00:00:00",
                    581810
                ],
                [
                    "2020-04-14T00:00:00",
                    608845
                ],
                [
                    "2020-04-15T00:00:00",
                    637974
                ],
                [
                    "2020-04-16T00:00:00",
                    669272
                ],
                [
                    "2020-04-17T00:00:00",
                    701996
                ],
                [
                    "2020-04-18T00:00:00",
                    730317
                ],
                [
                    "2020-04-19T00:00:00",
                    756375
                ],
                [
                    "2020-04-20T00:00:00",
                    783716
                ],
                [
                    "2020-04-21T00:00:00",
                    809213
                ],
                [
                    "2020-04-22T00:00:00",
                    837414
                ],
                [
                    "2020-04-23T00:00:00",
                    871617
                ],
                [
                    "2020-04-24T00:00:00",
                    907908
                ],
                [
                    "2020-04-25T00:00:00",
                    940829
                ],
                [
                    "2020-04-26T00:00:00",
                    968517
                ],
                [
                    "2020-04-27T00:00:00",
                    990993
                ],
                [
                    "2020-04-28T00:00:00",
                    1015518
                ],
                [
                    "2020-04-29T00:00:00",
                    1042926
                ],
                [
                    "2020-04-30T00:00:00",
                    1072667
                ]
            ],
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u786e\u8bca\u4eba\u6570"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "calendar": [
        {
            "zlevel": 0,
            "z": 2,
            "width": "auto",
            "orient": "horizontal",
            "range": [
                "2020-01-21",
                "2020-04-30"
            ],
            "cellSize": 50,
            "dayLabel": {
                "show": true,
                "firstDay": 0,
                "position": "start",
                "nameMap": "cn",
                "color": "#000",
                "fontStyle": "normal",
                "fontWeight": "normal",
                "fontFamily": "sans-serif",
                "fontSize": 12
            },
            "monthLabel": {
                "show": true,
                "position": "start",
                "nameMap": "cn",
                "color": "#000",
                "fontStyle": "normal",
                "fontWeight": "normal",
                "fontFamily": "sans-serif",
                "fontSize": 12
            },
            "yearLabel": {
                "show": true,
                "margin": 50,
                "color": "#000",
                "fontStyle": "normal",
                "fontWeight": "normal",
                "fontFamily": "sans-serif",
                "fontSize": 12
            },
            "silent": false
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": {
        "show": true,
        "type": "piecewise",
        "min": 0,
        "max": 1000000,
        "inRange": {
            "color": [
                "#CCD3D9",
                "#E6B6C2",
                "#D4587A",
                "#DC364C"
            ]
        },
        "calculable": true,
        "inverse": false,
        "splitNumber": 5,
        "hoverLink": true,
        "orient": "vertical",
        "padding": 5,
        "showLabel": true,
        "itemWidth": 20,
        "itemHeight": 14,
        "borderWidth": 0,
        "pieces": [
            {
                "min": 1000000
            },
            {
                "min": 10000,
                "max": 1000000
            },
            {
                "min": 100,
                "max": 10000
            },
            {
                "max": 100
            }
        ]
    }
};
        chart_6b9b902a8235459eb4bbb5d7509d1801.setOption(option_6b9b902a8235459eb4bbb5d7509d1801);
    </script>
</body>
</html>




#### 34.GEO添加自定义坐标


```python
from pyecharts.charts import *
from pyecharts import options as opts


def geo_add_custom_coordinate():
    geo = Geo(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    # 添加自定义坐标点
    geo.add_coordinate('x', 116.397428, 39.90923)
    geo.add_coordinate('y', 112.398615, 29.91659)

    geo.add_schema(maptype="china")
    geo.add("", [('x', 1), ('y', 2)])

    return geo


chart = geo_add_custom_coordinate()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/maps/china.js"></script>


</head>
<body >
    <div id="fb052462ce8f4f76953f91e062d94cf2" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_fb052462ce8f4f76953f91e062d94cf2 = echarts.init(
            document.getElementById('fb052462ce8f4f76953f91e062d94cf2'), 'light', {renderer: 'canvas'});
        var option_fb052462ce8f4f76953f91e062d94cf2 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "coordinateSystem": "geo",
            "symbolSize": 12,
            "data": [
                {
                    "name": "x",
                    "value": [
                        116.397428,
                        39.90923,
                        1
                    ]
                },
                {
                    "name": "y",
                    "value": [
                        112.398615,
                        29.91659,
                        2
                    ]
                }
            ]
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "geo": {
        "map": "china",
        "roam": true,
        "aspectScale": 0.75,
        "nameProperty": "name",
        "selectedMode": false,
        "emphasis": {}
    }
};
        chart_fb052462ce8f4f76953f91e062d94cf2.setOption(option_fb052462ce8f4f76953f91e062d94cf2);
    </script>
</body>
</html>




#### 35.GEO使用国外地图


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.datasets import register_url
import ssl


def geo_foreign_country():
    # 添加其他国家的地图
    # noinspection PyBroadException
    try:
        register_url("https://echarts-maps.github.io/echarts-countries-js/")
    except Exception:
        ssl._create_default_https_context = ssl._create_unverified_context
        register_url("https://echarts-maps.github.io/echarts-countries-js/")

    geo = Geo(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))

    geo.add_schema(maptype="美国")

    return geo


chart = geo_foreign_country()
from IPython.display import HTML
HTML(chart.render_embed())

```


    ---------------------------------------------------------------------------

    ConnectionRefusedError                    Traceback (most recent call last)

    File ~\anaconda3\Lib\urllib\request.py:1344, in AbstractHTTPHandler.do_open(self, http_class, req, **http_conn_args)
       1343 try:
    -> 1344     h.request(req.get_method(), req.selector, req.data, headers,
       1345               encode_chunked=req.has_header('Transfer-encoding'))
       1346 except OSError as err: # timeout error
    

    File ~\anaconda3\Lib\http\client.py:1336, in HTTPConnection.request(self, method, url, body, headers, encode_chunked)
       1335 """Send a complete request to the server."""
    -> 1336 self._send_request(method, url, body, headers, encode_chunked)
    

    File ~\anaconda3\Lib\http\client.py:1382, in HTTPConnection._send_request(self, method, url, body, headers, encode_chunked)
       1381     body = _encode(body, 'body')
    -> 1382 self.endheaders(body, encode_chunked=encode_chunked)
    

    File ~\anaconda3\Lib\http\client.py:1331, in HTTPConnection.endheaders(self, message_body, encode_chunked)
       1330     raise CannotSendHeader()
    -> 1331 self._send_output(message_body, encode_chunked=encode_chunked)
    

    File ~\anaconda3\Lib\http\client.py:1091, in HTTPConnection._send_output(self, message_body, encode_chunked)
       1090 del self._buffer[:]
    -> 1091 self.send(msg)
       1093 if message_body is not None:
       1094 
       1095     # create a consistent interface to message_body
    

    File ~\anaconda3\Lib\http\client.py:1035, in HTTPConnection.send(self, data)
       1034 if self.auto_open:
    -> 1035     self.connect()
       1036 else:
    

    File ~\anaconda3\Lib\http\client.py:1470, in HTTPSConnection.connect(self)
       1468 "Connect to a host on a given (SSL) port."
    -> 1470 super().connect()
       1472 if self._tunnel_host:
    

    File ~\anaconda3\Lib\http\client.py:1001, in HTTPConnection.connect(self)
       1000 sys.audit("http.client.connect", self, self.host, self.port)
    -> 1001 self.sock = self._create_connection(
       1002     (self.host,self.port), self.timeout, self.source_address)
       1003 # Might fail in OSs that don't implement TCP_NODELAY
    

    File ~\anaconda3\Lib\socket.py:865, in create_connection(address, timeout, source_address, all_errors)
        864 if not all_errors:
    --> 865     raise exceptions[0]
        866 raise ExceptionGroup("create_connection failed", exceptions)
    

    File ~\anaconda3\Lib\socket.py:850, in create_connection(address, timeout, source_address, all_errors)
        849     sock.bind(source_address)
    --> 850 sock.connect(sa)
        851 # Break explicitly a reference cycle
    

    ConnectionRefusedError: [WinError 10061] 由于目标计算机积极拒绝，无法连接。

    
    During handling of the above exception, another exception occurred:
    

    URLError                                  Traceback (most recent call last)

    Cell In[83], line 11, in geo_foreign_country()
         10 try:
    ---> 11     register_url("https://echarts-maps.github.io/echarts-countries-js/")
         12 except Exception:
    

    File ~\anaconda3\Lib\site-packages\pyecharts\datasets\__init__.py:110, in register_url(asset_url)
        109 except Exception as e:
    --> 110     raise e
        111 files = {}
    

    File ~\anaconda3\Lib\site-packages\pyecharts\datasets\__init__.py:107, in register_url(asset_url)
        106 try:
    --> 107     contents = urllib.request.urlopen(registry).read()
        108     contents = json.loads(contents)
    

    File ~\anaconda3\Lib\urllib\request.py:215, in urlopen(url, data, timeout, cafile, capath, cadefault, context)
        214     opener = _opener
    --> 215 return opener.open(url, data, timeout)
    

    File ~\anaconda3\Lib\urllib\request.py:515, in OpenerDirector.open(self, fullurl, data, timeout)
        514 sys.audit('urllib.Request', req.full_url, req.data, req.headers, req.get_method())
    --> 515 response = self._open(req, data)
        517 # post-process response
    

    File ~\anaconda3\Lib\urllib\request.py:532, in OpenerDirector._open(self, req, data)
        531 protocol = req.type
    --> 532 result = self._call_chain(self.handle_open, protocol, protocol +
        533                           '_open', req)
        534 if result:
    

    File ~\anaconda3\Lib\urllib\request.py:492, in OpenerDirector._call_chain(self, chain, kind, meth_name, *args)
        491 func = getattr(handler, meth_name)
    --> 492 result = func(*args)
        493 if result is not None:
    

    File ~\anaconda3\Lib\urllib\request.py:1392, in HTTPSHandler.https_open(self, req)
       1391 def https_open(self, req):
    -> 1392     return self.do_open(http.client.HTTPSConnection, req,
       1393                         context=self._context)
    

    File ~\anaconda3\Lib\urllib\request.py:1347, in AbstractHTTPHandler.do_open(self, http_class, req, **http_conn_args)
       1346 except OSError as err: # timeout error
    -> 1347     raise URLError(err)
       1348 r = h.getresponse()
    

    URLError: <urlopen error [WinError 10061] 由于目标计算机积极拒绝，无法连接。>

    
    During handling of the above exception, another exception occurred:
    

    ConnectionRefusedError                    Traceback (most recent call last)

    File ~\anaconda3\Lib\urllib\request.py:1344, in AbstractHTTPHandler.do_open(self, http_class, req, **http_conn_args)
       1343 try:
    -> 1344     h.request(req.get_method(), req.selector, req.data, headers,
       1345               encode_chunked=req.has_header('Transfer-encoding'))
       1346 except OSError as err: # timeout error
    

    File ~\anaconda3\Lib\http\client.py:1336, in HTTPConnection.request(self, method, url, body, headers, encode_chunked)
       1335 """Send a complete request to the server."""
    -> 1336 self._send_request(method, url, body, headers, encode_chunked)
    

    File ~\anaconda3\Lib\http\client.py:1382, in HTTPConnection._send_request(self, method, url, body, headers, encode_chunked)
       1381     body = _encode(body, 'body')
    -> 1382 self.endheaders(body, encode_chunked=encode_chunked)
    

    File ~\anaconda3\Lib\http\client.py:1331, in HTTPConnection.endheaders(self, message_body, encode_chunked)
       1330     raise CannotSendHeader()
    -> 1331 self._send_output(message_body, encode_chunked=encode_chunked)
    

    File ~\anaconda3\Lib\http\client.py:1091, in HTTPConnection._send_output(self, message_body, encode_chunked)
       1090 del self._buffer[:]
    -> 1091 self.send(msg)
       1093 if message_body is not None:
       1094 
       1095     # create a consistent interface to message_body
    

    File ~\anaconda3\Lib\http\client.py:1035, in HTTPConnection.send(self, data)
       1034 if self.auto_open:
    -> 1035     self.connect()
       1036 else:
    

    File ~\anaconda3\Lib\http\client.py:1470, in HTTPSConnection.connect(self)
       1468 "Connect to a host on a given (SSL) port."
    -> 1470 super().connect()
       1472 if self._tunnel_host:
    

    File ~\anaconda3\Lib\http\client.py:1001, in HTTPConnection.connect(self)
       1000 sys.audit("http.client.connect", self, self.host, self.port)
    -> 1001 self.sock = self._create_connection(
       1002     (self.host,self.port), self.timeout, self.source_address)
       1003 # Might fail in OSs that don't implement TCP_NODELAY
    

    File ~\anaconda3\Lib\socket.py:865, in create_connection(address, timeout, source_address, all_errors)
        864 if not all_errors:
    --> 865     raise exceptions[0]
        866 raise ExceptionGroup("create_connection failed", exceptions)
    

    File ~\anaconda3\Lib\socket.py:850, in create_connection(address, timeout, source_address, all_errors)
        849     sock.bind(source_address)
    --> 850 sock.connect(sa)
        851 # Break explicitly a reference cycle
    

    ConnectionRefusedError: [WinError 10061] 由于目标计算机积极拒绝，无法连接。

    
    During handling of the above exception, another exception occurred:
    

    URLError                                  Traceback (most recent call last)

    Cell In[83], line 25
         20     geo.add_schema(maptype="美国")
         22     return geo
    ---> 25 chart = geo_foreign_country()
         26 from IPython.display import HTML
         27 HTML(chart.render_embed())
    

    Cell In[83], line 14, in geo_foreign_country()
         12 except Exception:
         13     ssl._create_default_https_context = ssl._create_unverified_context
    ---> 14     register_url("https://echarts-maps.github.io/echarts-countries-js/")
         16 geo = Geo(init_opts=opts.InitOpts(theme='light',
         17                                   width='1000px',
         18                                   height='600px'))
         20 geo.add_schema(maptype="美国")
    

    File ~\anaconda3\Lib\site-packages\pyecharts\datasets\__init__.py:110, in register_url(asset_url)
        108     contents = json.loads(contents)
        109 except Exception as e:
    --> 110     raise e
        111 files = {}
        112 pinyin_names = set()
    

    File ~\anaconda3\Lib\site-packages\pyecharts\datasets\__init__.py:107, in register_url(asset_url)
        105 registry = asset_url + "/registry.json"
        106 try:
    --> 107     contents = urllib.request.urlopen(registry).read()
        108     contents = json.loads(contents)
        109 except Exception as e:
    

    File ~\anaconda3\Lib\urllib\request.py:215, in urlopen(url, data, timeout, cafile, capath, cadefault, context)
        213 else:
        214     opener = _opener
    --> 215 return opener.open(url, data, timeout)
    

    File ~\anaconda3\Lib\urllib\request.py:515, in OpenerDirector.open(self, fullurl, data, timeout)
        512     req = meth(req)
        514 sys.audit('urllib.Request', req.full_url, req.data, req.headers, req.get_method())
    --> 515 response = self._open(req, data)
        517 # post-process response
        518 meth_name = protocol+"_response"
    

    File ~\anaconda3\Lib\urllib\request.py:532, in OpenerDirector._open(self, req, data)
        529     return result
        531 protocol = req.type
    --> 532 result = self._call_chain(self.handle_open, protocol, protocol +
        533                           '_open', req)
        534 if result:
        535     return result
    

    File ~\anaconda3\Lib\urllib\request.py:492, in OpenerDirector._call_chain(self, chain, kind, meth_name, *args)
        490 for handler in handlers:
        491     func = getattr(handler, meth_name)
    --> 492     result = func(*args)
        493     if result is not None:
        494         return result
    

    File ~\anaconda3\Lib\urllib\request.py:1392, in HTTPSHandler.https_open(self, req)
       1391 def https_open(self, req):
    -> 1392     return self.do_open(http.client.HTTPSConnection, req,
       1393                         context=self._context)
    

    File ~\anaconda3\Lib\urllib\request.py:1347, in AbstractHTTPHandler.do_open(self, http_class, req, **http_conn_args)
       1344         h.request(req.get_method(), req.selector, req.data, headers,
       1345                   encode_chunked=req.has_header('Transfer-encoding'))
       1346     except OSError as err: # timeout error
    -> 1347         raise URLError(err)
       1348     r = h.getresponse()
       1349 except:
    

    URLError: <urlopen error [WinError 10061] 由于目标计算机积极拒绝，无法连接。>


#### 36.GEO 带涟漪效果散点图


```python
from pyecharts.charts import *
from pyecharts import options as opts


def geo_effect_scatter():
    geo = Geo(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))

    geo.add_schema(maptype="china")

    geo.add("",
            [("广州", 150), ("北京", 70), ("长沙", 64), ("上海", 74),  ("厦门", 63)],
            # 涟漪效果散点图
            type_='effectScatter')

    return geo


chart = geo_effect_scatter()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/maps/china.js"></script>


</head>
<body >
    <div id="f5e14eba78294168b074a17675081115" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_f5e14eba78294168b074a17675081115 = echarts.init(
            document.getElementById('f5e14eba78294168b074a17675081115'), 'light', {renderer: 'canvas'});
        var option_f5e14eba78294168b074a17675081115 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "effectScatter",
            "coordinateSystem": "geo",
            "showEffectOn": "render",
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            },
            "symbolSize": 12,
            "data": [
                {
                    "name": "\u5e7f\u5dde",
                    "value": [
                        113.23,
                        23.16,
                        150
                    ]
                },
                {
                    "name": "\u5317\u4eac",
                    "value": [
                        116.407526,
                        39.90403,
                        70
                    ]
                },
                {
                    "name": "\u957f\u6c99",
                    "value": [
                        113,
                        28.21,
                        64
                    ]
                },
                {
                    "name": "\u4e0a\u6d77",
                    "value": [
                        121.473701,
                        31.230416,
                        74
                    ]
                },
                {
                    "name": "\u53a6\u95e8",
                    "value": [
                        118.1,
                        24.46,
                        63
                    ]
                }
            ]
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "geo": {
        "map": "china",
        "roam": true,
        "aspectScale": 0.75,
        "nameProperty": "name",
        "selectedMode": false,
        "emphasis": {}
    }
};
        chart_f5e14eba78294168b074a17675081115.setOption(option_f5e14eba78294168b074a17675081115);
    </script>
</body>
</html>




#### 37.GEO热力图


```python
from pyecharts.charts import *
from pyecharts import options as opts


def geo_heatmap():
    geo = Geo(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))

    geo.add_schema(maptype="china")

    geo.add("",
            [("广州", 150), ("北京", 70), ("深圳", 64), ("上海", 74),  ("杭州", 63)],
            type_='heatmap')
    # 热点图必须配置visualmap_opts
    geo.set_global_opts(visualmap_opts=opts.VisualMapOpts())
    return geo


chart = geo_heatmap()
from IPython.display import HTML
HTML(chart.render_embed())

```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/maps/china.js"></script>


</head>
<body >
    <div id="fbf2af3a618d4f848990e79f5108b6bc" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_fbf2af3a618d4f848990e79f5108b6bc = echarts.init(
            document.getElementById('fbf2af3a618d4f848990e79f5108b6bc'), 'light', {renderer: 'canvas'});
        var option_fbf2af3a618d4f848990e79f5108b6bc = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "heatmap",
            "coordinateSystem": "geo",
            "data": [
                {
                    "name": "\u5e7f\u5dde",
                    "value": [
                        113.23,
                        23.16,
                        150
                    ]
                },
                {
                    "name": "\u5317\u4eac",
                    "value": [
                        116.407526,
                        39.90403,
                        70
                    ]
                },
                {
                    "name": "\u6df1\u5733",
                    "value": [
                        114.07,
                        22.62,
                        64
                    ]
                },
                {
                    "name": "\u4e0a\u6d77",
                    "value": [
                        121.473701,
                        31.230416,
                        74
                    ]
                },
                {
                    "name": "\u676d\u5dde",
                    "value": [
                        120.19,
                        30.26,
                        63
                    ]
                }
            ],
            "pointSize": 20,
            "blurSize": 20
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "formatter": function (params) {        return params.name + ' : ' + params.value[2];    },
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": {
        "show": true,
        "type": "continuous",
        "min": 0,
        "max": 100,
        "inRange": {
            "color": [
                "#50a3ba",
                "#eac763",
                "#d94e5d"
            ]
        },
        "calculable": true,
        "inverse": false,
        "splitNumber": 5,
        "hoverLink": true,
        "orient": "vertical",
        "padding": 5,
        "showLabel": true,
        "itemWidth": 20,
        "itemHeight": 140,
        "borderWidth": 0
    },
    "geo": {
        "map": "china",
        "roam": true,
        "aspectScale": 0.75,
        "nameProperty": "name",
        "selectedMode": false,
        "emphasis": {}
    }
};
        chart_fbf2af3a618d4f848990e79f5108b6bc.setOption(option_fbf2af3a618d4f848990e79f5108b6bc);
    </script>
</body>
</html>




#### 38.GEO 线图


```python
from pyecharts.charts import *
from pyecharts import options as opts


def geo_lines():
    geo = Geo(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))

    geo.add_schema(maptype="china")

    geo.add("广州出发",
            # 数据格式（from， to）
            [("广州", "上海"), ("广州", "北京"), ("广州", "西宁"), ("广州", "重庆")],
            type_='lines')
    geo.add("成都出发",
            # 数据格式（from， to）
            [("成都", '长沙'), ("成都", "武汉"), ("成都", "长春"), ("成都", "南京")],
            type_='lines')

    return geo


chart = geo_lines()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/maps/china.js"></script>


</head>
<body >
    <div id="fff6179ec3c74bb08b7f88fa38e82ce6" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_fff6179ec3c74bb08b7f88fa38e82ce6 = echarts.init(
            document.getElementById('fff6179ec3c74bb08b7f88fa38e82ce6'), 'light', {renderer: 'canvas'});
        var option_fff6179ec3c74bb08b7f88fa38e82ce6 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "lines",
            "name": "\u5e7f\u5dde\u51fa\u53d1",
            "coordinateSystem": "geo",
            "zlevel": 2,
            "progressive": 400,
            "progressiveThreshold": 3000,
            "effect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            },
            "symbol": [
                "none",
                "arrow"
            ],
            "polyline": false,
            "large": false,
            "largeThreshold": 2000,
            "symbolSize": 12,
            "data": [
                {
                    "name": "\u5e7f\u5dde->\u4e0a\u6d77",
                    "coords": [
                        [
                            113.23,
                            23.16
                        ],
                        [
                            121.473701,
                            31.230416
                        ]
                    ]
                },
                {
                    "name": "\u5e7f\u5dde->\u5317\u4eac",
                    "coords": [
                        [
                            113.23,
                            23.16
                        ],
                        [
                            116.407526,
                            39.90403
                        ]
                    ]
                },
                {
                    "name": "\u5e7f\u5dde->\u897f\u5b81",
                    "coords": [
                        [
                            113.23,
                            23.16
                        ],
                        [
                            101.74,
                            36.56
                        ]
                    ]
                },
                {
                    "name": "\u5e7f\u5dde->\u91cd\u5e86",
                    "coords": [
                        [
                            113.23,
                            23.16
                        ],
                        [
                            106.551556,
                            29.563009
                        ]
                    ]
                }
            ],
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            }
        },
        {
            "type": "lines",
            "name": "\u6210\u90fd\u51fa\u53d1",
            "coordinateSystem": "geo",
            "zlevel": 3,
            "progressive": 400,
            "progressiveThreshold": 3000,
            "effect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            },
            "symbol": [
                "none",
                "arrow"
            ],
            "polyline": false,
            "large": false,
            "largeThreshold": 2000,
            "symbolSize": 12,
            "data": [
                {
                    "name": "\u6210\u90fd->\u957f\u6c99",
                    "coords": [
                        [
                            104.06,
                            30.67
                        ],
                        [
                            113,
                            28.21
                        ]
                    ]
                },
                {
                    "name": "\u6210\u90fd->\u6b66\u6c49",
                    "coords": [
                        [
                            104.06,
                            30.67
                        ],
                        [
                            114.31,
                            30.52
                        ]
                    ]
                },
                {
                    "name": "\u6210\u90fd->\u957f\u6625",
                    "coords": [
                        [
                            104.06,
                            30.67
                        ],
                        [
                            125.35,
                            43.88
                        ]
                    ]
                },
                {
                    "name": "\u6210\u90fd->\u5357\u4eac",
                    "coords": [
                        [
                            104.06,
                            30.67
                        ],
                        [
                            118.78,
                            32.04
                        ]
                    ]
                }
            ],
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u5e7f\u5dde\u51fa\u53d1",
                "\u6210\u90fd\u51fa\u53d1"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "geo": {
        "map": "china",
        "roam": true,
        "aspectScale": 0.75,
        "nameProperty": "name",
        "selectedMode": false,
        "emphasis": {}
    }
};
        chart_fff6179ec3c74bb08b7f88fa38e82ce6.setOption(option_fff6179ec3c74bb08b7f88fa38e82ce6);
    </script>
</body>
</html>




#### 39.饼图自定义图形半径范围


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def pie_custom_radius():
    pie = Pie(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    pie.add("",
            [list(z) for z in zip(Faker.choose(), Faker.values())],
            # 设置半径范围，0%-100%
            radius=["40%", "75%"])

    return pie


chart = pie_custom_radius()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="07f9fa1f41c645048aa11729aff02542" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_07f9fa1f41c645048aa11729aff02542 = echarts.init(
            document.getElementById('07f9fa1f41c645048aa11729aff02542'), 'light', {renderer: 'canvas'});
        var option_07f9fa1f41c645048aa11729aff02542 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "pie",
            "colorBy": "data",
            "legendHoverLink": true,
            "selectedMode": false,
            "selectedOffset": 10,
            "clockwise": true,
            "startAngle": 90,
            "minAngle": 0,
            "minShowLabelAngle": 0,
            "avoidLabelOverlap": true,
            "stillShowZeroSum": true,
            "percentPrecision": 2,
            "showEmptyCircle": true,
            "emptyCircleStyle": {
                "color": "lightgray",
                "borderColor": "#000",
                "borderWidth": 0,
                "borderType": "solid",
                "borderDashOffset": 0,
                "borderCap": "butt",
                "borderJoin": "bevel",
                "borderMiterLimit": 10,
                "opacity": 1
            },
            "data": [
                {
                    "name": "\u5468\u4e00",
                    "value": 124
                },
                {
                    "name": "\u5468\u4e8c",
                    "value": 86
                },
                {
                    "name": "\u5468\u4e09",
                    "value": 113
                },
                {
                    "name": "\u5468\u56db",
                    "value": 44
                },
                {
                    "name": "\u5468\u4e94",
                    "value": 128
                },
                {
                    "name": "\u5468\u516d",
                    "value": 21
                },
                {
                    "name": "\u5468\u65e5",
                    "value": 100
                }
            ],
            "radius": [
                "40%",
                "75%"
            ],
            "center": [
                "50%",
                "50%"
            ],
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "labelLine": {
                "show": true,
                "showAbove": false,
                "length": 15,
                "length2": 15,
                "smooth": false,
                "minTurnAngle": 90,
                "maxSurfaceAngle": 90
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u5468\u4e00",
                "\u5468\u4e8c",
                "\u5468\u4e09",
                "\u5468\u56db",
                "\u5468\u4e94",
                "\u5468\u516d",
                "\u5468\u65e5"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    }
};
        chart_07f9fa1f41c645048aa11729aff02542.setOption(option_07f9fa1f41c645048aa11729aff02542);
    </script>
</body>
</html>




#### 40.饼图自定义数据标签


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def pie_with_custom_label():
    pie = Pie(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='600px'))
    pie.add("", [list(z) for z in zip(Faker.choose(), Faker.values())])
    pie.set_series_opts(
        # 自定义数据标签
        label_opts=opts.LabelOpts(position='top',
                                  color='red',
                                  font_family='Arial',
                                  font_size=12,
                                  font_style='italic',
                                  interval=1,
                                  formatter='{b}:{d}%'
                                  )
    )

    return pie


chart = pie_with_custom_label()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="eb537bc0cd6d46a3881e38f71cb7b6a5" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_eb537bc0cd6d46a3881e38f71cb7b6a5 = echarts.init(
            document.getElementById('eb537bc0cd6d46a3881e38f71cb7b6a5'), 'light', {renderer: 'canvas'});
        var option_eb537bc0cd6d46a3881e38f71cb7b6a5 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "pie",
            "colorBy": "data",
            "legendHoverLink": true,
            "selectedMode": false,
            "selectedOffset": 10,
            "clockwise": true,
            "startAngle": 90,
            "minAngle": 0,
            "minShowLabelAngle": 0,
            "avoidLabelOverlap": true,
            "stillShowZeroSum": true,
            "percentPrecision": 2,
            "showEmptyCircle": true,
            "emptyCircleStyle": {
                "color": "lightgray",
                "borderColor": "#000",
                "borderWidth": 0,
                "borderType": "solid",
                "borderDashOffset": 0,
                "borderCap": "butt",
                "borderJoin": "bevel",
                "borderMiterLimit": 10,
                "opacity": 1
            },
            "data": [
                {
                    "name": "\u6cb3\u9a6c",
                    "value": 113
                },
                {
                    "name": "\u87d2\u86c7",
                    "value": 91
                },
                {
                    "name": "\u8001\u864e",
                    "value": 95
                },
                {
                    "name": "\u5927\u8c61",
                    "value": 68
                },
                {
                    "name": "\u5154\u5b50",
                    "value": 42
                },
                {
                    "name": "\u718a\u732b",
                    "value": 31
                },
                {
                    "name": "\u72ee\u5b50",
                    "value": 63
                }
            ],
            "radius": [
                "0%",
                "75%"
            ],
            "center": [
                "50%",
                "50%"
            ],
            "label": {
                "show": true,
                "position": "top",
                "color": "red",
                "margin": 8,
                "interval": 1,
                "fontSize": 12,
                "fontStyle": "italic",
                "fontFamily": "Arial",
                "formatter": "{b}:{d}%",
                "valueAnimation": false
            },
            "labelLine": {
                "show": true,
                "showAbove": false,
                "length": 15,
                "length2": 15,
                "smooth": false,
                "minTurnAngle": 90,
                "maxSurfaceAngle": 90
            },
            "rippleEffect": {
                "show": true,
                "brushType": "stroke",
                "scale": 2.5,
                "period": 4
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u6cb3\u9a6c",
                "\u87d2\u86c7",
                "\u8001\u864e",
                "\u5927\u8c61",
                "\u5154\u5b50",
                "\u718a\u732b",
                "\u72ee\u5b50"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    }
};
        chart_eb537bc0cd6d46a3881e38f71cb7b6a5.setOption(option_eb537bc0cd6d46a3881e38f71cb7b6a5);
    </script>
</body>
</html>




#### 41.多饼图


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def pie_multiple():
    pie = Pie(init_opts=opts.InitOpts(theme='light',
                                      width='1000px',
                                      height='800px'))
    pie.add("",
            [list(z) for z in zip(Faker.choose(), Faker.values())],
            radius=["20%", "50%"],
            center=["25%", "50%"])
    # 添加多个饼图
    pie.add("",
            [list(z) for z in zip(Faker.choose(), Faker.values())],
            radius=["20%", "50%"],
            center=["75%", "50%"])

    return pie


chart = pie_multiple()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="2311f295834f437e8018de594c46c81d" class="chart-container" style="width:1000px; height:800px; "></div>
    <script>
        var chart_2311f295834f437e8018de594c46c81d = echarts.init(
            document.getElementById('2311f295834f437e8018de594c46c81d'), 'light', {renderer: 'canvas'});
        var option_2311f295834f437e8018de594c46c81d = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "pie",
            "colorBy": "data",
            "legendHoverLink": true,
            "selectedMode": false,
            "selectedOffset": 10,
            "clockwise": true,
            "startAngle": 90,
            "minAngle": 0,
            "minShowLabelAngle": 0,
            "avoidLabelOverlap": true,
            "stillShowZeroSum": true,
            "percentPrecision": 2,
            "showEmptyCircle": true,
            "emptyCircleStyle": {
                "color": "lightgray",
                "borderColor": "#000",
                "borderWidth": 0,
                "borderType": "solid",
                "borderDashOffset": 0,
                "borderCap": "butt",
                "borderJoin": "bevel",
                "borderMiterLimit": 10,
                "opacity": 1
            },
            "data": [
                {
                    "name": "\u8349\u8393",
                    "value": 82
                },
                {
                    "name": "\u8292\u679c",
                    "value": 71
                },
                {
                    "name": "\u8461\u8404",
                    "value": 93
                },
                {
                    "name": "\u96ea\u68a8",
                    "value": 63
                },
                {
                    "name": "\u897f\u74dc",
                    "value": 83
                },
                {
                    "name": "\u67e0\u6aac",
                    "value": 135
                },
                {
                    "name": "\u8f66\u5398\u5b50",
                    "value": 38
                }
            ],
            "radius": [
                "20%",
                "50%"
            ],
            "center": [
                "25%",
                "50%"
            ],
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "labelLine": {
                "show": true,
                "showAbove": false,
                "length": 15,
                "length2": 15,
                "smooth": false,
                "minTurnAngle": 90,
                "maxSurfaceAngle": 90
            }
        },
        {
            "type": "pie",
            "colorBy": "data",
            "legendHoverLink": true,
            "selectedMode": false,
            "selectedOffset": 10,
            "clockwise": true,
            "startAngle": 90,
            "minAngle": 0,
            "minShowLabelAngle": 0,
            "avoidLabelOverlap": true,
            "stillShowZeroSum": true,
            "percentPrecision": 2,
            "showEmptyCircle": true,
            "emptyCircleStyle": {
                "color": "lightgray",
                "borderColor": "#000",
                "borderWidth": 0,
                "borderType": "solid",
                "borderDashOffset": 0,
                "borderCap": "butt",
                "borderJoin": "bevel",
                "borderMiterLimit": 10,
                "opacity": 1
            },
            "data": [
                {
                    "name": "\u54c8\u58eb\u5947",
                    "value": 76
                },
                {
                    "name": "\u8428\u6469\u8036",
                    "value": 102
                },
                {
                    "name": "\u6cf0\u8fea",
                    "value": 87
                },
                {
                    "name": "\u91d1\u6bdb",
                    "value": 150
                },
                {
                    "name": "\u7267\u7f8a\u72ac",
                    "value": 133
                },
                {
                    "name": "\u5409\u5a03\u5a03",
                    "value": 127
                },
                {
                    "name": "\u67ef\u57fa",
                    "value": 50
                }
            ],
            "radius": [
                "20%",
                "50%"
            ],
            "center": [
                "75%",
                "50%"
            ],
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "labelLine": {
                "show": true,
                "showAbove": false,
                "length": 15,
                "length2": 15,
                "smooth": false,
                "minTurnAngle": 90,
                "maxSurfaceAngle": 90
            }
        }
    ],
    "legend": [
        {
            "data": [
                "\u8349\u8393",
                "\u8292\u679c",
                "\u8461\u8404",
                "\u96ea\u68a8",
                "\u897f\u74dc",
                "\u67e0\u6aac",
                "\u8f66\u5398\u5b50",
                "\u54c8\u58eb\u5947",
                "\u8428\u6469\u8036",
                "\u6cf0\u8fea",
                "\u91d1\u6bdb",
                "\u7267\u7f8a\u72ac",
                "\u5409\u5a03\u5a03",
                "\u67ef\u57fa"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    }
};
        chart_2311f295834f437e8018de594c46c81d.setOption(option_2311f295834f437e8018de594c46c81d);
    </script>
</body>
</html>




#### 42.散点图添加视觉组件（图形大小）


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def scatter_with_visualmap_size():
    scatter = Scatter(init_opts=opts.InitOpts(theme='light',
                                              width='1000px',
                                              height='600px'))
    scatter.add_xaxis(Faker.choose())
    scatter.add_yaxis('', Faker.values())
    # 设置视觉组件
    scatter.set_global_opts(visualmap_opts=opts.VisualMapOpts(type_='size'))
    return scatter


chart = scatter_with_visualmap_size()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="c50ab9cf16144622b23d8fb01eb1cf69" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_c50ab9cf16144622b23d8fb01eb1cf69 = echarts.init(
            document.getElementById('c50ab9cf16144622b23d8fb01eb1cf69'), 'light', {renderer: 'canvas'});
        var option_c50ab9cf16144622b23d8fb01eb1cf69 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "symbolSize": 10,
            "data": [
                [
                    "\u53ef\u4e50",
                    58
                ],
                [
                    "\u96ea\u78a7",
                    89
                ],
                [
                    "\u6a59\u6c41",
                    87
                ],
                [
                    "\u7eff\u8336",
                    41
                ],
                [
                    "\u5976\u8336",
                    49
                ],
                [
                    "\u767e\u5a01",
                    145
                ],
                [
                    "\u9752\u5c9b",
                    75
                ]
            ],
            "label": {
                "show": true,
                "position": "right",
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u53ef\u4e50",
                "\u96ea\u78a7",
                "\u6a59\u6c41",
                "\u7eff\u8336",
                "\u5976\u8336",
                "\u767e\u5a01",
                "\u9752\u5c9b"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": {
        "show": true,
        "type": "continuous",
        "min": 0,
        "max": 100,
        "inRange": {
            "symbolSize": [
                20,
                50
            ]
        },
        "calculable": true,
        "inverse": false,
        "splitNumber": 5,
        "hoverLink": true,
        "orient": "vertical",
        "padding": 5,
        "showLabel": true,
        "itemWidth": 20,
        "itemHeight": 140,
        "borderWidth": 0
    }
};
        chart_c50ab9cf16144622b23d8fb01eb1cf69.setOption(option_c50ab9cf16144622b23d8fb01eb1cf69);
    </script>
</body>
</html>




#### 43.散点图添加视觉组件（图形大小&颜色）


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = [random.randint(0, 100) for _ in range(30)]
y_data = [(random.randint(0, 100), random.randint(0, 100), random.randint(0, 100)) for _ in range(30)]


def scatter_with_visualmap_color_size():
    scatter = Scatter(init_opts=opts.InitOpts(theme='light',
                                              width='1000px',
                                              height='600px'))
    scatter.add_xaxis(x_data)
    scatter.add_yaxis('', y_data)
    # 多个映射维度通过list形式传入
    # dimension指定数据维度
    scatter.set_global_opts(visualmap_opts=[opts.VisualMapOpts(is_show=True, type_='size', dimension=2, pos_top='20%'),
                                            opts.VisualMapOpts(is_show=True, type_='color', dimension=3,  pos_top='60%')
                                            ],
                            xaxis_opts=opts.AxisOpts(type_="value"))
    return scatter


chart = scatter_with_visualmap_color_size()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="ec52a60e798a4501b74af56081110146" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_ec52a60e798a4501b74af56081110146 = echarts.init(
            document.getElementById('ec52a60e798a4501b74af56081110146'), 'light', {renderer: 'canvas'});
        var option_ec52a60e798a4501b74af56081110146 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "symbolSize": 10,
            "data": [
                [
                    37,
                    36,
                    56,
                    94
                ],
                [
                    99,
                    62,
                    72,
                    100
                ],
                [
                    17,
                    26,
                    20,
                    8
                ],
                [
                    69,
                    51,
                    0,
                    64
                ],
                [
                    25,
                    36,
                    45,
                    14
                ],
                [
                    88,
                    66,
                    70,
                    96
                ],
                [
                    56,
                    3,
                    53,
                    29
                ],
                [
                    40,
                    48,
                    39,
                    75
                ],
                [
                    61,
                    41,
                    43,
                    6
                ],
                [
                    79,
                    94,
                    7,
                    36
                ],
                [
                    69,
                    96,
                    66,
                    48
                ],
                [
                    99,
                    18,
                    46,
                    71
                ],
                [
                    44,
                    0,
                    20,
                    10
                ],
                [
                    37,
                    84,
                    11,
                    15
                ],
                [
                    78,
                    2,
                    21,
                    79
                ],
                [
                    9,
                    80,
                    9,
                    79
                ],
                [
                    34,
                    100,
                    68,
                    3
                ],
                [
                    75,
                    28,
                    98,
                    50
                ],
                [
                    73,
                    20,
                    45,
                    3
                ],
                [
                    10,
                    94,
                    57,
                    12
                ],
                [
                    63,
                    73,
                    96,
                    47
                ],
                [
                    32,
                    48,
                    45,
                    83
                ],
                [
                    32,
                    78,
                    61,
                    41
                ],
                [
                    65,
                    96,
                    16,
                    12
                ],
                [
                    89,
                    21,
                    99,
                    16
                ],
                [
                    4,
                    9,
                    58,
                    44
                ],
                [
                    87,
                    3,
                    56,
                    71
                ],
                [
                    92,
                    18,
                    9,
                    40
                ],
                [
                    28,
                    54,
                    21,
                    95
                ],
                [
                    75,
                    18,
                    1,
                    77
                ]
            ],
            "label": {
                "show": true,
                "position": "right",
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "type": "value",
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                37,
                99,
                17,
                69,
                25,
                88,
                56,
                40,
                61,
                79,
                69,
                99,
                44,
                37,
                78,
                9,
                34,
                75,
                73,
                10,
                63,
                32,
                32,
                65,
                89,
                4,
                87,
                92,
                28,
                75
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": [
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "symbolSize": [
                    20,
                    50
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 2,
            "hoverLink": true,
            "orient": "vertical",
            "top": "20%",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        },
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "color": [
                    "#50a3ba",
                    "#eac763",
                    "#d94e5d"
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 3,
            "hoverLink": true,
            "orient": "vertical",
            "top": "60%",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        }
    ]
};
        chart_ec52a60e798a4501b74af56081110146.setOption(option_ec52a60e798a4501b74af56081110146);
    </script>
</body>
</html>




#### 44.散点图添加视觉组件（图形大小&颜色&透明度）


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

x_data = [random.randint(0, 100) for _ in range(30)]
y_data = [(random.randint(0, 100), random.randint(0, 100), random.randint(0, 100), random.randint(0, 100))
          for _ in range(30)]


def scatter_with_visualmap_color_size_opacity():
    scatter = Scatter(init_opts=opts.InitOpts(theme='light',
                                              width='1000px',
                                              height='600px'))
    scatter.add_xaxis(x_data)
    scatter.add_yaxis('', y_data)
    # 多个映射维度通过list形式传入
    # dimension制定数据维度
    scatter.set_global_opts(visualmap_opts=[opts.VisualMapOpts(is_show=True, type_='size', dimension=2, pos_top='10%'),
                                            opts.VisualMapOpts(is_show=True, type_='color', dimension=3, pos_top='40%'),
                                            opts.VisualMapOpts(is_show=True, type_='opacity', dimension=4,
                                                               # VisualMapOpt中对于range_opacity没给默认值，需要自行设定
                                                               range_opacity=[0.2, 1], pos_top='70%')],
                            xaxis_opts=opts.AxisOpts(type_="value"))
    return scatter


chart = scatter_with_visualmap_color_size_opacity()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="1491e0c8f34342828fc2344de774f116" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_1491e0c8f34342828fc2344de774f116 = echarts.init(
            document.getElementById('1491e0c8f34342828fc2344de774f116'), 'light', {renderer: 'canvas'});
        var option_1491e0c8f34342828fc2344de774f116 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "symbolSize": 10,
            "data": [
                [
                    17,
                    6,
                    80,
                    66,
                    67
                ],
                [
                    85,
                    62,
                    3,
                    43,
                    70
                ],
                [
                    71,
                    84,
                    90,
                    52,
                    93
                ],
                [
                    75,
                    51,
                    6,
                    7,
                    19
                ],
                [
                    52,
                    10,
                    11,
                    73,
                    41
                ],
                [
                    52,
                    39,
                    37,
                    73,
                    88
                ],
                [
                    8,
                    39,
                    74,
                    28,
                    38
                ],
                [
                    74,
                    94,
                    18,
                    61,
                    0
                ],
                [
                    68,
                    81,
                    64,
                    46,
                    63
                ],
                [
                    83,
                    61,
                    10,
                    88,
                    57
                ],
                [
                    51,
                    86,
                    14,
                    21,
                    41
                ],
                [
                    83,
                    21,
                    92,
                    49,
                    73
                ],
                [
                    37,
                    47,
                    85,
                    32,
                    83
                ],
                [
                    22,
                    93,
                    17,
                    52,
                    35
                ],
                [
                    18,
                    99,
                    12,
                    58,
                    88
                ],
                [
                    39,
                    73,
                    59,
                    16,
                    32
                ],
                [
                    12,
                    29,
                    59,
                    43,
                    34
                ],
                [
                    43,
                    8,
                    26,
                    34,
                    54
                ],
                [
                    99,
                    54,
                    28,
                    73,
                    24
                ],
                [
                    49,
                    10,
                    84,
                    81,
                    74
                ],
                [
                    17,
                    13,
                    61,
                    84,
                    91
                ],
                [
                    88,
                    73,
                    77,
                    38,
                    57
                ],
                [
                    7,
                    75,
                    71,
                    74,
                    46
                ],
                [
                    97,
                    9,
                    3,
                    26,
                    88
                ],
                [
                    22,
                    17,
                    59,
                    73,
                    77
                ],
                [
                    29,
                    94,
                    43,
                    64,
                    2
                ],
                [
                    25,
                    12,
                    72,
                    6,
                    91
                ],
                [
                    20,
                    32,
                    42,
                    75,
                    46
                ],
                [
                    21,
                    25,
                    14,
                    90,
                    3
                ],
                [
                    34,
                    85,
                    44,
                    27,
                    42
                ]
            ],
            "label": {
                "show": true,
                "position": "right",
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "type": "value",
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                17,
                85,
                71,
                75,
                52,
                52,
                8,
                74,
                68,
                83,
                51,
                83,
                37,
                22,
                18,
                39,
                12,
                43,
                99,
                49,
                17,
                88,
                7,
                97,
                22,
                29,
                25,
                20,
                21,
                34
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": [
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "symbolSize": [
                    20,
                    50
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 2,
            "hoverLink": true,
            "orient": "vertical",
            "top": "10%",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        },
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "color": [
                    "#50a3ba",
                    "#eac763",
                    "#d94e5d"
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 3,
            "hoverLink": true,
            "orient": "vertical",
            "top": "40%",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        },
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "opacity": [
                    0.2,
                    1
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 4,
            "hoverLink": true,
            "orient": "vertical",
            "top": "70%",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        }
    ]
};
        chart_1491e0c8f34342828fc2344de774f116.setOption(option_1491e0c8f34342828fc2344de774f116);
    </script>
</body>
</html>




#### 45.自定义背景颜色


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random


x_data = [random.randint(0, 100) for _ in range(30)]
y_data = [(random.randint(0, 100), random.randint(0, 100), random.randint(0, 100)) for _ in range(30)]


def scatter_with_custom_bgColor():
    scatter = Scatter(
        init_opts=opts.InitOpts(theme='light',
                                width='1000px',
                                height='600px',
                                # 自定义背景颜色
                                bg_color='#008B8B'))
    scatter.add_xaxis(x_data)
    scatter.add_yaxis('', y_data)
    # 多个映射维度通过list形式传入
    # dimension制定数据维度
    scatter.set_global_opts(visualmap_opts=[opts.VisualMapOpts(is_show=True, type_='size', dimension=2),
                                            opts.VisualMapOpts(is_show=True, type_='color', dimension=3)],
                            xaxis_opts=opts.AxisOpts(type_="value"))
    return scatter


chart = scatter_with_custom_bgColor()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="6b6bce871e714e279e547c7fa2c01887" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_6b6bce871e714e279e547c7fa2c01887 = echarts.init(
            document.getElementById('6b6bce871e714e279e547c7fa2c01887'), 'light', {renderer: 'canvas'});
        var option_6b6bce871e714e279e547c7fa2c01887 = {
    "backgroundColor": "#008B8B",
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "scatter",
            "symbolSize": 10,
            "data": [
                [
                    84,
                    53,
                    9,
                    67
                ],
                [
                    13,
                    58,
                    3,
                    45
                ],
                [
                    66,
                    68,
                    28,
                    58
                ],
                [
                    65,
                    34,
                    30,
                    90
                ],
                [
                    9,
                    100,
                    0,
                    16
                ],
                [
                    36,
                    69,
                    1,
                    83
                ],
                [
                    99,
                    87,
                    41,
                    73
                ],
                [
                    97,
                    35,
                    14,
                    25
                ],
                [
                    95,
                    88,
                    5,
                    51
                ],
                [
                    91,
                    23,
                    23,
                    56
                ],
                [
                    55,
                    12,
                    62,
                    54
                ],
                [
                    2,
                    19,
                    100,
                    69
                ],
                [
                    30,
                    43,
                    19,
                    54
                ],
                [
                    59,
                    25,
                    76,
                    100
                ],
                [
                    76,
                    72,
                    89,
                    18
                ],
                [
                    33,
                    63,
                    32,
                    35
                ],
                [
                    19,
                    83,
                    17,
                    16
                ],
                [
                    53,
                    47,
                    27,
                    7
                ],
                [
                    97,
                    42,
                    77,
                    87
                ],
                [
                    21,
                    67,
                    63,
                    58
                ],
                [
                    83,
                    74,
                    63,
                    100
                ],
                [
                    49,
                    72,
                    96,
                    32
                ],
                [
                    30,
                    96,
                    64,
                    96
                ],
                [
                    34,
                    62,
                    73,
                    50
                ],
                [
                    99,
                    61,
                    74,
                    37
                ],
                [
                    34,
                    13,
                    69,
                    21
                ],
                [
                    14,
                    79,
                    27,
                    7
                ],
                [
                    49,
                    15,
                    60,
                    61
                ],
                [
                    89,
                    88,
                    80,
                    44
                ],
                [
                    99,
                    23,
                    21,
                    57
                ]
            ],
            "label": {
                "show": true,
                "position": "right",
                "margin": 8,
                "valueAnimation": false
            }
        }
    ],
    "legend": [
        {
            "data": [
                ""
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "type": "value",
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                84,
                13,
                66,
                65,
                9,
                36,
                99,
                97,
                95,
                91,
                55,
                2,
                30,
                59,
                76,
                33,
                19,
                53,
                97,
                21,
                83,
                49,
                30,
                34,
                99,
                34,
                14,
                49,
                89,
                99
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": [
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "symbolSize": [
                    20,
                    50
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 2,
            "hoverLink": true,
            "orient": "vertical",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        },
        {
            "show": true,
            "type": "continuous",
            "min": 0,
            "max": 100,
            "inRange": {
                "color": [
                    "#50a3ba",
                    "#eac763",
                    "#d94e5d"
                ]
            },
            "calculable": true,
            "inverse": false,
            "splitNumber": 5,
            "dimension": 3,
            "hoverLink": true,
            "orient": "vertical",
            "padding": 5,
            "showLabel": true,
            "itemWidth": 20,
            "itemHeight": 140,
            "borderWidth": 0
        }
    ]
};
        chart_6b6bce871e714e279e547c7fa2c01887.setOption(option_6b6bce871e714e279e547c7fa2c01887);
    </script>
</body>
</html>




#### 46.词云图自定义字体范围


```python
from pyecharts.charts import *
from pyecharts import options as opts
import random

text = """
I used to rule the world
Seas would rise when I gave the word
Now in the morning I sleep alone
Sweep the streets I used to own
I used to roll the dice
Feel the fear in my enemy eyes
Listen as the crowd would sing
Now the old king is dead
Long live the king
One minute I held the key
Next the walls were closed on me
And I discovered that my castles stand
Upon pillars of salt and pillars of sand
I hear Jerusalem bells are ringing
Roman Cavalry choirs are singing
Be my mirror my sword and shield
My missionaries in a foreign field
For some reason I can't explain
Once you go there was never
Never an honest word
That was when I ruled the world
"""

word_list = set(text.split(' '))

words = [(word, random.randint(1, 100)) for word in word_list]


def wordcloud_custom_word_size():
    wordcloud = WordCloud(init_opts=opts.InitOpts(theme='light',
                                                  width='1000px',
                                                  height='600px'))
    wordcloud.add('',
                  words,
                  # 设置字体大小范围
                  word_size_range=[10, 50])

    return wordcloud


chart = wordcloud_custom_word_size()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts-wordcloud.min.js"></script>


</head>
<body >
    <div id="4eb301cf09af4612875756e26949fa72" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_4eb301cf09af4612875756e26949fa72 = echarts.init(
            document.getElementById('4eb301cf09af4612875756e26949fa72'), 'light', {renderer: 'canvas'});
        var option_4eb301cf09af4612875756e26949fa72 = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "wordCloud",
            "shape": "circle",
            "rotationRange": [
                -90,
                90
            ],
            "rotationStep": 45,
            "girdSize": 20,
            "sizeRange": [
                10,
                50
            ],
            "data": [
                {
                    "name": "minute",
                    "value": 25,
                    "textStyle": {
                        "color": "rgb(128,99,9)"
                    }
                },
                {
                    "name": "me\nAnd",
                    "value": 41,
                    "textStyle": {
                        "color": "rgb(24,60,47)"
                    }
                },
                {
                    "name": "field\nFor",
                    "value": 87,
                    "textStyle": {
                        "color": "rgb(125,137,118)"
                    }
                },
                {
                    "name": "foreign",
                    "value": 18,
                    "textStyle": {
                        "color": "rgb(130,26,96)"
                    }
                },
                {
                    "name": "closed",
                    "value": 14,
                    "textStyle": {
                        "color": "rgb(136,80,22)"
                    }
                },
                {
                    "name": "fear",
                    "value": 68,
                    "textStyle": {
                        "color": "rgb(155,3,63)"
                    }
                },
                {
                    "name": "king\nOne",
                    "value": 25,
                    "textStyle": {
                        "color": "rgb(2,49,92)"
                    }
                },
                {
                    "name": "word\nThat",
                    "value": 8,
                    "textStyle": {
                        "color": "rgb(115,18,130)"
                    }
                },
                {
                    "name": "ruled",
                    "value": 71,
                    "textStyle": {
                        "color": "rgb(26,117,26)"
                    }
                },
                {
                    "name": "singing\nBe",
                    "value": 46,
                    "textStyle": {
                        "color": "rgb(107,51,28)"
                    }
                },
                {
                    "name": "ringing\nRoman",
                    "value": 90,
                    "textStyle": {
                        "color": "rgb(3,22,117)"
                    }
                },
                {
                    "name": "bells",
                    "value": 39,
                    "textStyle": {
                        "color": "rgb(89,4,54)"
                    }
                },
                {
                    "name": "an",
                    "value": 20,
                    "textStyle": {
                        "color": "rgb(38,150,119)"
                    }
                },
                {
                    "name": "world\nSeas",
                    "value": 48,
                    "textStyle": {
                        "color": "rgb(142,102,7)"
                    }
                },
                {
                    "name": "own\nI",
                    "value": 21,
                    "textStyle": {
                        "color": "rgb(76,35,69)"
                    }
                },
                {
                    "name": "key\nNext",
                    "value": 4,
                    "textStyle": {
                        "color": "rgb(129,100,99)"
                    }
                },
                {
                    "name": "sand\nI",
                    "value": 98,
                    "textStyle": {
                        "color": "rgb(26,159,61)"
                    }
                },
                {
                    "name": "eyes\nListen",
                    "value": 51,
                    "textStyle": {
                        "color": "rgb(116,74,140)"
                    }
                },
                {
                    "name": "enemy",
                    "value": 34,
                    "textStyle": {
                        "color": "rgb(134,69,95)"
                    }
                },
                {
                    "name": "my",
                    "value": 30,
                    "textStyle": {
                        "color": "rgb(15,81,13)"
                    }
                },
                {
                    "name": "Cavalry",
                    "value": 90,
                    "textStyle": {
                        "color": "rgb(153,51,26)"
                    }
                },
                {
                    "name": "crowd",
                    "value": 99,
                    "textStyle": {
                        "color": "rgb(143,131,65)"
                    }
                },
                {
                    "name": "was",
                    "value": 3,
                    "textStyle": {
                        "color": "rgb(31,1,134)"
                    }
                },
                {
                    "name": "go",
                    "value": 93,
                    "textStyle": {
                        "color": "rgb(137,135,151)"
                    }
                },
                {
                    "name": "king",
                    "value": 23,
                    "textStyle": {
                        "color": "rgb(4,83,86)"
                    }
                },
                {
                    "name": "the",
                    "value": 29,
                    "textStyle": {
                        "color": "rgb(155,108,46)"
                    }
                },
                {
                    "name": "\nI",
                    "value": 71,
                    "textStyle": {
                        "color": "rgb(89,151,136)"
                    }
                },
                {
                    "name": "as",
                    "value": 27,
                    "textStyle": {
                        "color": "rgb(157,11,109)"
                    }
                },
                {
                    "name": "held",
                    "value": 21,
                    "textStyle": {
                        "color": "rgb(9,95,135)"
                    }
                },
                {
                    "name": "salt",
                    "value": 19,
                    "textStyle": {
                        "color": "rgb(34,44,91)"
                    }
                },
                {
                    "name": "alone\nSweep",
                    "value": 70,
                    "textStyle": {
                        "color": "rgb(135,104,138)"
                    }
                },
                {
                    "name": "discovered",
                    "value": 35,
                    "textStyle": {
                        "color": "rgb(158,9,46)"
                    }
                },
                {
                    "name": "can't",
                    "value": 89,
                    "textStyle": {
                        "color": "rgb(113,6,35)"
                    }
                },
                {
                    "name": "some",
                    "value": 18,
                    "textStyle": {
                        "color": "rgb(22,110,130)"
                    }
                },
                {
                    "name": "dice\nFeel",
                    "value": 13,
                    "textStyle": {
                        "color": "rgb(68,13,131)"
                    }
                },
                {
                    "name": "would",
                    "value": 5,
                    "textStyle": {
                        "color": "rgb(24,20,6)"
                    }
                },
                {
                    "name": "of",
                    "value": 18,
                    "textStyle": {
                        "color": "rgb(121,10,37)"
                    }
                },
                {
                    "name": "rise",
                    "value": 87,
                    "textStyle": {
                        "color": "rgb(124,60,75)"
                    }
                },
                {
                    "name": "explain\nOnce",
                    "value": 21,
                    "textStyle": {
                        "color": "rgb(73,98,16)"
                    }
                },
                {
                    "name": "roll",
                    "value": 41,
                    "textStyle": {
                        "color": "rgb(136,130,38)"
                    }
                },
                {
                    "name": "on",
                    "value": 13,
                    "textStyle": {
                        "color": "rgb(118,121,148)"
                    }
                },
                {
                    "name": "shield\nMy",
                    "value": 92,
                    "textStyle": {
                        "color": "rgb(77,125,113)"
                    }
                },
                {
                    "name": "word\nNow",
                    "value": 69,
                    "textStyle": {
                        "color": "rgb(5,43,136)"
                    }
                },
                {
                    "name": "and",
                    "value": 80,
                    "textStyle": {
                        "color": "rgb(16,107,77)"
                    }
                },
                {
                    "name": "a",
                    "value": 91,
                    "textStyle": {
                        "color": "rgb(68,56,115)"
                    }
                },
                {
                    "name": "Jerusalem",
                    "value": 56,
                    "textStyle": {
                        "color": "rgb(70,99,51)"
                    }
                },
                {
                    "name": "stand\nUpon",
                    "value": 20,
                    "textStyle": {
                        "color": "rgb(8,22,67)"
                    }
                },
                {
                    "name": "pillars",
                    "value": 60,
                    "textStyle": {
                        "color": "rgb(125,4,69)"
                    }
                },
                {
                    "name": "there",
                    "value": 32,
                    "textStyle": {
                        "color": "rgb(92,156,41)"
                    }
                },
                {
                    "name": "old",
                    "value": 54,
                    "textStyle": {
                        "color": "rgb(120,6,15)"
                    }
                },
                {
                    "name": "that",
                    "value": 87,
                    "textStyle": {
                        "color": "rgb(13,12,14)"
                    }
                },
                {
                    "name": "mirror",
                    "value": 16,
                    "textStyle": {
                        "color": "rgb(68,128,141)"
                    }
                },
                {
                    "name": "gave",
                    "value": 39,
                    "textStyle": {
                        "color": "rgb(33,104,141)"
                    }
                },
                {
                    "name": "sing\nNow",
                    "value": 8,
                    "textStyle": {
                        "color": "rgb(12,108,19)"
                    }
                },
                {
                    "name": "hear",
                    "value": 40,
                    "textStyle": {
                        "color": "rgb(158,83,137)"
                    }
                },
                {
                    "name": "sleep",
                    "value": 26,
                    "textStyle": {
                        "color": "rgb(147,78,15)"
                    }
                },
                {
                    "name": "morning",
                    "value": 96,
                    "textStyle": {
                        "color": "rgb(12,43,7)"
                    }
                },
                {
                    "name": "I",
                    "value": 92,
                    "textStyle": {
                        "color": "rgb(153,48,147)"
                    }
                },
                {
                    "name": "when",
                    "value": 20,
                    "textStyle": {
                        "color": "rgb(134,114,119)"
                    }
                },
                {
                    "name": "sword",
                    "value": 92,
                    "textStyle": {
                        "color": "rgb(100,105,62)"
                    }
                },
                {
                    "name": "streets",
                    "value": 29,
                    "textStyle": {
                        "color": "rgb(159,142,29)"
                    }
                },
                {
                    "name": "were",
                    "value": 74,
                    "textStyle": {
                        "color": "rgb(31,15,54)"
                    }
                },
                {
                    "name": "rule",
                    "value": 62,
                    "textStyle": {
                        "color": "rgb(97,82,98)"
                    }
                },
                {
                    "name": "honest",
                    "value": 90,
                    "textStyle": {
                        "color": "rgb(114,159,60)"
                    }
                },
                {
                    "name": "castles",
                    "value": 13,
                    "textStyle": {
                        "color": "rgb(92,66,49)"
                    }
                },
                {
                    "name": "reason",
                    "value": 84,
                    "textStyle": {
                        "color": "rgb(138,72,13)"
                    }
                },
                {
                    "name": "used",
                    "value": 3,
                    "textStyle": {
                        "color": "rgb(92,113,120)"
                    }
                },
                {
                    "name": "dead\nLong",
                    "value": 45,
                    "textStyle": {
                        "color": "rgb(49,133,10)"
                    }
                },
                {
                    "name": "choirs",
                    "value": 17,
                    "textStyle": {
                        "color": "rgb(35,134,154)"
                    }
                },
                {
                    "name": "missionaries",
                    "value": 6,
                    "textStyle": {
                        "color": "rgb(40,62,91)"
                    }
                },
                {
                    "name": "is",
                    "value": 81,
                    "textStyle": {
                        "color": "rgb(53,117,116)"
                    }
                },
                {
                    "name": "never\nNever",
                    "value": 81,
                    "textStyle": {
                        "color": "rgb(131,93,3)"
                    }
                },
                {
                    "name": "are",
                    "value": 82,
                    "textStyle": {
                        "color": "rgb(123,21,66)"
                    }
                },
                {
                    "name": "walls",
                    "value": 70,
                    "textStyle": {
                        "color": "rgb(111,159,144)"
                    }
                },
                {
                    "name": "in",
                    "value": 77,
                    "textStyle": {
                        "color": "rgb(119,159,95)"
                    }
                },
                {
                    "name": "live",
                    "value": 54,
                    "textStyle": {
                        "color": "rgb(146,119,47)"
                    }
                },
                {
                    "name": "you",
                    "value": 74,
                    "textStyle": {
                        "color": "rgb(130,85,94)"
                    }
                },
                {
                    "name": "to",
                    "value": 76,
                    "textStyle": {
                        "color": "rgb(101,139,142)"
                    }
                },
                {
                    "name": "world\n",
                    "value": 20,
                    "textStyle": {
                        "color": "rgb(139,65,70)"
                    }
                }
            ],
            "drawOutOfBound": false,
            "textStyle": {
                "emphasis": {}
            }
        }
    ],
    "legend": [
        {
            "data": [],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    }
};
        chart_4eb301cf09af4612875756e26949fa72.setOption(option_4eb301cf09af4612875756e26949fa72);
    </script>
</body>
</html>




#### 47.Map带视觉组件


```python
from pyecharts.charts import *
from pyecharts import options as opts

data = [('广东', 10430),
        ('山东', 9579),
        ('河南', 9402),
        ('四川', 8041),
        ('江苏', 7866),
        ('河北', 7185),
        ('湖南', 6568),
        ('安徽', 5950),
        ('湖北', 5724),
        ('浙江', 5442),
        ('广西', 4603),
        ('云南', 4597),
        ('江西', 4457),
        ('辽宁', 4375),
        ('黑龙江', 3831),
        ('陕西', 3733),
        ('山西', 3571),
        ('福建', 3552),
        ('贵州', 3477),
        ('重庆', 2884),
        ('吉林', 2746),
        ('甘肃省', 2557),
        ('内蒙古', 2471),
        ('台湾', 2316),
        ('上海', 2301),
        ('新疆', 2181),
        ('北京', 1961),
        ('天津', 1294),
        ('海南', 867),
        ('香港', 710),
        ('宁夏', 630),
        ('青海', 562),
        ('西藏', 300),
        ('澳门', 55)]


def map_with_viusalmap():
    map_chart = Map(init_opts=opts.InitOpts(theme='light',
                                            width='1000px',
                                            height='600px'))
    map_chart.add('人口（万人）',
                  data_pair=data,
                  maptype='china',
                  # 关闭symbol的显示
                  is_map_symbol_show=False)

    map_chart.set_global_opts(visualmap_opts=opts.VisualMapOpts(
        max_=10430,  # visualmap默认映射数据范围是【0，100】，需调整
        is_piecewise=True,
        range_color=["#CCD3D9", "#E6B6C2", "#D4587A", "#DC364C"]
    ))
    return map_chart


chart = map_with_viusalmap()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>
            <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/maps/china.js"></script>


</head>
<body >
    <div id="5dca1d2a34a04e999333f2cc41107a3d" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_5dca1d2a34a04e999333f2cc41107a3d = echarts.init(
            document.getElementById('5dca1d2a34a04e999333f2cc41107a3d'), 'light', {renderer: 'canvas'});
        var option_5dca1d2a34a04e999333f2cc41107a3d = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "series": [
        {
            "type": "map",
            "name": "\u4eba\u53e3\uff08\u4e07\u4eba\uff09",
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "map": "china",
            "data": [
                {
                    "name": "\u5e7f\u4e1c",
                    "value": 10430
                },
                {
                    "name": "\u5c71\u4e1c",
                    "value": 9579
                },
                {
                    "name": "\u6cb3\u5357",
                    "value": 9402
                },
                {
                    "name": "\u56db\u5ddd",
                    "value": 8041
                },
                {
                    "name": "\u6c5f\u82cf",
                    "value": 7866
                },
                {
                    "name": "\u6cb3\u5317",
                    "value": 7185
                },
                {
                    "name": "\u6e56\u5357",
                    "value": 6568
                },
                {
                    "name": "\u5b89\u5fbd",
                    "value": 5950
                },
                {
                    "name": "\u6e56\u5317",
                    "value": 5724
                },
                {
                    "name": "\u6d59\u6c5f",
                    "value": 5442
                },
                {
                    "name": "\u5e7f\u897f",
                    "value": 4603
                },
                {
                    "name": "\u4e91\u5357",
                    "value": 4597
                },
                {
                    "name": "\u6c5f\u897f",
                    "value": 4457
                },
                {
                    "name": "\u8fbd\u5b81",
                    "value": 4375
                },
                {
                    "name": "\u9ed1\u9f99\u6c5f",
                    "value": 3831
                },
                {
                    "name": "\u9655\u897f",
                    "value": 3733
                },
                {
                    "name": "\u5c71\u897f",
                    "value": 3571
                },
                {
                    "name": "\u798f\u5efa",
                    "value": 3552
                },
                {
                    "name": "\u8d35\u5dde",
                    "value": 3477
                },
                {
                    "name": "\u91cd\u5e86",
                    "value": 2884
                },
                {
                    "name": "\u5409\u6797",
                    "value": 2746
                },
                {
                    "name": "\u7518\u8083\u7701",
                    "value": 2557
                },
                {
                    "name": "\u5185\u8499\u53e4",
                    "value": 2471
                },
                {
                    "name": "\u53f0\u6e7e",
                    "value": 2316
                },
                {
                    "name": "\u4e0a\u6d77",
                    "value": 2301
                },
                {
                    "name": "\u65b0\u7586",
                    "value": 2181
                },
                {
                    "name": "\u5317\u4eac",
                    "value": 1961
                },
                {
                    "name": "\u5929\u6d25",
                    "value": 1294
                },
                {
                    "name": "\u6d77\u5357",
                    "value": 867
                },
                {
                    "name": "\u9999\u6e2f",
                    "value": 710
                },
                {
                    "name": "\u5b81\u590f",
                    "value": 630
                },
                {
                    "name": "\u9752\u6d77",
                    "value": 562
                },
                {
                    "name": "\u897f\u85cf",
                    "value": 300
                },
                {
                    "name": "\u6fb3\u95e8",
                    "value": 55
                }
            ],
            "roam": true,
            "aspectScale": 0.75,
            "nameProperty": "name",
            "selectedMode": false,
            "zoom": 1,
            "zlevel": 0,
            "z": 2,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "mapValueCalculation": "sum",
            "showLegendSymbol": false,
            "emphasis": {}
        }
    ],
    "legend": [
        {
            "data": [
                "\u4eba\u53e3\uff08\u4e07\u4eba\uff09"
            ],
            "selected": {},
            "show": true,
            "padding": 5,
            "itemGap": 10,
            "itemWidth": 25,
            "itemHeight": 14,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderRadius": 0,
            "pageButtonItemGap": 5,
            "pageButtonPosition": "end",
            "pageFormatter": "{current}/{total}",
            "pageIconColor": "#2f4554",
            "pageIconInactiveColor": "#aaa",
            "pageIconSize": 15,
            "animationDurationUpdate": 800,
            "selector": false,
            "selectorPosition": "auto",
            "selectorItemGap": 7,
            "selectorButtonGap": 10
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ],
    "visualMap": {
        "show": true,
        "type": "piecewise",
        "min": 0,
        "max": 10430,
        "inRange": {
            "color": [
                "#CCD3D9",
                "#E6B6C2",
                "#D4587A",
                "#DC364C"
            ]
        },
        "calculable": true,
        "inverse": false,
        "splitNumber": 5,
        "hoverLink": true,
        "orient": "vertical",
        "padding": 5,
        "showLabel": true,
        "itemWidth": 20,
        "itemHeight": 14,
        "borderWidth": 0
    }
};
        chart_5dca1d2a34a04e999333f2cc41107a3d.setOption(option_5dca1d2a34a04e999333f2cc41107a3d);
    </script>
</body>
</html>




#### 48.Page更改布局

from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def page_simple_layout():
    # 图表1
    bar_1 = Bar(init_opts=opts.InitOpts(theme='light',
                                        width='500px',
                                        height='300px'))
    bar_1.add_xaxis(Faker.choose())
    bar_1.add_yaxis('A', Faker.values())
    bar_1.add_yaxis('B', Faker.values())

    # 图表2
    bar_2 = Bar(init_opts=opts.InitOpts(theme='light',
                                        width='500px',
                                        height='300px'))
    bar_2.add_xaxis(Faker.choose())
    bar_2.add_yaxis('A', Faker.values())
    # x,y轴翻转
    bar_2.reversal_axis()

    # 图表3
    line = Line(init_opts=opts.InitOpts(theme='light',
                                        width='500px',
                                        height='300px'))
    line.add_xaxis(Faker.choose())
    line.add_yaxis('A', Faker.values())
    line.add_yaxis('B', Faker.values())

    # 图表4
    pie = Pie(init_opts=opts.InitOpts(theme='light',
                                      width='500px',
                                      height='300px'))
    pie.add("",
            [list(z) for z in zip(Faker.choose(), Faker.values())],
            radius=["40%", "75%"])

    page = Page(layout=Page.SimplePageLayout)
    # 需要自行调整每个 chart 的 height/width，布局会因为页面大小而不同
    page.add(bar_1, bar_2, line, pie)

    return page


chart = page_simple_layout()
from IPython.display import HTML
HTML(chart.render_embed())


#### 49.一个Tab下带多个图表

* 通过Grid将多个图表组合，然后再将Grid添加到Tab中；


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def tab_with_multiple_chart():
    # 图表1
    bar = Bar()
    bar.add_xaxis(Faker.choose())
    bar.add_yaxis("商家A", Faker.values())
    bar.add_yaxis("商家B", Faker.values())

    # 图表2
    line = Line()
    line.add_xaxis(Faker.choose())
    line.add_yaxis("商家A", Faker.values())
    line.add_yaxis("商家B", Faker.values())

    # 先通过Grid将图表1和图表2组合起来
    grid = Grid()
    grid.add(bar, grid_opts=opts.GridOpts(pos_bottom="60%"))
    grid.add(line, grid_opts=opts.GridOpts(pos_top="60%"))

    # 再将Grid添加到Tab
    tab = Tab()
    tab.add(grid, '示例')

    return tab


chart = tab_with_multiple_chart()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
            <style>
        .tab {
            overflow: hidden;
            border: 1px solid #ccc;
            background-color: #f1f1f1;
        }

        .tab button {
            background-color: inherit;
            float: left;
            border: none;
            outline: none;
            cursor: pointer;
            padding: 12px 16px;
            transition: 0.3s;
        }

        .tab button:hover {
            background-color: #ddd;
        }

        .tab button.active {
            background-color: #ccc;
        }

        .chart-container {
            display: block;
        }

        .chart-container:nth-child(n+2) {
            display: none;
        }
    </style>
    <div class="tab">
            <button class="tablinks" onclick="showChart(event, '8176a629f7374460bee84d55d03395da')">示例</button>
    </div>

    <div class="box">
                <div id="8176a629f7374460bee84d55d03395da" class="chart-container" style="width:900px; height:500px; "></div>
    <script>
            document.getElementById('8176a629f7374460bee84d55d03395da').style.width = document.getElementById('8176a629f7374460bee84d55d03395da').parentNode.clientWidth + 'px';
        var chart_8176a629f7374460bee84d55d03395da = echarts.init(
            document.getElementById('8176a629f7374460bee84d55d03395da'), 'white', {renderer: 'canvas'});
        var option_8176a629f7374460bee84d55d03395da = {
    "animation": true,
    "animationThreshold": 2000,
    "animationDuration": 1000,
    "animationEasing": "cubicOut",
    "animationDelay": 0,
    "animationDurationUpdate": 300,
    "animationEasingUpdate": "cubicOut",
    "animationDelayUpdate": 0,
    "aria": {
        "enabled": false
    },
    "color": [
        "#5470c6",
        "#91cc75",
        "#fac858",
        "#ee6666",
        "#73c0de",
        "#3ba272",
        "#fc8452",
        "#9a60b4",
        "#ea7ccc"
    ],
    "series": [
        {
            "type": "bar",
            "name": "\u5546\u5bb6A",
            "xAxisIndex": 0,
            "yAxisIndex": 0,
            "legendHoverLink": true,
            "data": [
                35,
                25,
                53,
                26,
                120,
                83,
                96
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "bar",
            "name": "\u5546\u5bb6B",
            "xAxisIndex": 0,
            "yAxisIndex": 0,
            "legendHoverLink": true,
            "data": [
                134,
                67,
                91,
                143,
                42,
                64,
                114
            ],
            "realtimeSort": false,
            "showBackground": false,
            "stackStrategy": "samesign",
            "cursor": "pointer",
            "barMinHeight": 0,
            "barCategoryGap": "20%",
            "barGap": "30%",
            "large": false,
            "largeThreshold": 400,
            "seriesLayoutBy": "column",
            "datasetIndex": 0,
            "clip": true,
            "zlevel": 0,
            "z": 2,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            }
        },
        {
            "type": "line",
            "name": "\u5546\u5bb6A",
            "connectNulls": false,
            "xAxisIndex": 1,
            "yAxisIndex": 1,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u5468\u4e00",
                    51
                ],
                [
                    "\u5468\u4e8c",
                    144
                ],
                [
                    "\u5468\u4e09",
                    114
                ],
                [
                    "\u5468\u56db",
                    46
                ],
                [
                    "\u5468\u4e94",
                    138
                ],
                [
                    "\u5468\u516d",
                    53
                ],
                [
                    "\u5468\u65e5",
                    117
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        },
        {
            "type": "line",
            "name": "\u5546\u5bb6B",
            "connectNulls": false,
            "xAxisIndex": 1,
            "yAxisIndex": 1,
            "symbolSize": 4,
            "showSymbol": true,
            "smooth": false,
            "clip": true,
            "step": false,
            "stackStrategy": "samesign",
            "data": [
                [
                    "\u5468\u4e00",
                    66
                ],
                [
                    "\u5468\u4e8c",
                    64
                ],
                [
                    "\u5468\u4e09",
                    37
                ],
                [
                    "\u5468\u56db",
                    94
                ],
                [
                    "\u5468\u4e94",
                    135
                ],
                [
                    "\u5468\u516d",
                    132
                ],
                [
                    "\u5468\u65e5",
                    41
                ]
            ],
            "hoverAnimation": true,
            "label": {
                "show": true,
                "margin": 8,
                "valueAnimation": false
            },
            "logBase": 10,
            "seriesLayoutBy": "column",
            "lineStyle": {
                "show": true,
                "width": 1,
                "opacity": 1,
                "curveness": 0,
                "type": "solid"
            },
            "areaStyle": {
                "opacity": 0
            },
            "zlevel": 0,
            "z": 0
        }
    ],
    "legend": [
        {
            "data": [
                "\u5546\u5bb6A",
                "\u5546\u5bb6B"
            ],
            "selected": {}
        },
        {
            "data": [
                "\u5546\u5bb6A",
                "\u5546\u5bb6B"
            ],
            "selected": {}
        }
    ],
    "tooltip": {
        "show": true,
        "trigger": "item",
        "triggerOn": "mousemove|click",
        "axisPointer": {
            "type": "line"
        },
        "showContent": true,
        "alwaysShowContent": false,
        "showDelay": 0,
        "hideDelay": 100,
        "enterable": false,
        "confine": false,
        "appendToBody": false,
        "transitionDuration": 0.4,
        "textStyle": {
            "fontSize": 14
        },
        "borderWidth": 0,
        "padding": 5,
        "order": "seriesAsc"
    },
    "xAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u6cb3\u9a6c",
                "\u87d2\u86c7",
                "\u8001\u864e",
                "\u5927\u8c61",
                "\u5154\u5b50",
                "\u718a\u732b",
                "\u72ee\u5b50"
            ]
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 1,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0,
            "data": [
                "\u5468\u4e00",
                "\u5468\u4e8c",
                "\u5468\u4e09",
                "\u5468\u56db",
                "\u5468\u4e94",
                "\u5468\u516d",
                "\u5468\u65e5"
            ]
        }
    ],
    "yAxis": [
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 0,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        },
        {
            "show": true,
            "scale": false,
            "nameLocation": "end",
            "nameGap": 15,
            "gridIndex": 1,
            "inverse": false,
            "offset": 0,
            "splitNumber": 5,
            "minInterval": 0,
            "splitLine": {
                "show": true,
                "lineStyle": {
                    "show": true,
                    "width": 1,
                    "opacity": 1,
                    "curveness": 0,
                    "type": "solid"
                }
            },
            "animation": true,
            "animationThreshold": 2000,
            "animationDuration": 1000,
            "animationEasing": "cubicOut",
            "animationDelay": 0,
            "animationDurationUpdate": 300,
            "animationEasingUpdate": "cubicOut",
            "animationDelayUpdate": 0
        }
    ],
    "grid": [
        {
            "show": false,
            "zlevel": 0,
            "z": 2,
            "bottom": "60%",
            "containLabel": false,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderWidth": 1,
            "shadowOffsetX": 0,
            "shadowOffsetY": 0
        },
        {
            "show": false,
            "zlevel": 0,
            "z": 2,
            "top": "60%",
            "containLabel": false,
            "backgroundColor": "transparent",
            "borderColor": "#ccc",
            "borderWidth": 1,
            "shadowOffsetX": 0,
            "shadowOffsetY": 0
        }
    ],
    "title": [
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        },
        {
            "show": true,
            "target": "blank",
            "subtarget": "blank",
            "padding": 5,
            "itemGap": 10,
            "textAlign": "auto",
            "textVerticalAlign": "auto",
            "triggerEvent": false
        }
    ]
};
        chart_8176a629f7374460bee84d55d03395da.setOption(option_8176a629f7374460bee84d55d03395da);
    </script>
    </div>

    <script>
    </script>
    <script>
        (function() {
            containers = document.getElementsByClassName("chart-container");
            if(containers.length > 0) {
                containers[0].style.display = "block";
            }
        })()

        function showChart(evt, chartID) {
            let containers = document.getElementsByClassName("chart-container");
            for (let i = 0; i < containers.length; i++) {
                containers[i].style.display = "none";
            }

            let tablinks = document.getElementsByClassName("tablinks");
            for (let i = 0; i < tablinks.length; i++) {
                tablinks[i].className = "tablinks";
            }

            document.getElementById(chartID).style.display = "block";
            evt.currentTarget.className += " active";
        }
    </script>
</body>
</html>




#### 50.Timeline 自动播放


```python
from pyecharts.charts import *
from pyecharts import options as opts
from pyecharts.faker import Faker


def timeline_auto_play():
    timeline = Timeline(init_opts=opts.InitOpts(theme='light',
                                                width='1000px',
                                                height='600px'))
    timeline.add_schema(is_auto_play=True,  # 自动播放
                        is_loop_play=True  # 循环播放
                        )
    for year in range(2000, 2020):
        bar = Bar()
        bar.add_xaxis(['香蕉', '梨子', '水蜜桃', '核桃', '西瓜', '苹果', '菠萝'])
        bar.add_yaxis('A', Faker.values())
        bar.add_yaxis('B', Faker.values())
        timeline.add(bar, '{}年'.format(year))
    return timeline


chart = timeline_auto_play()
from IPython.display import HTML
HTML(chart.render_embed())
```




<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Awesome-pyecharts</title>
                <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/echarts@5.4.2/dist/echarts.min.js"></script>


</head>
<body >
    <div id="49b90bd150bb4b3eb6216ae3f578d1da" class="chart-container" style="width:1000px; height:600px; "></div>
    <script>
        var chart_49b90bd150bb4b3eb6216ae3f578d1da = echarts.init(
            document.getElementById('49b90bd150bb4b3eb6216ae3f578d1da'), 'light', {renderer: 'canvas'});
        var option_49b90bd150bb4b3eb6216ae3f578d1da = {
    "baseOption": {
        "series": [
            {
                "type": "bar",
                "name": "A",
                "legendHoverLink": true,
                "data": [
                    74,
                    56,
                    135,
                    132,
                    95,
                    133,
                    103
                ],
                "realtimeSort": false,
                "showBackground": false,
                "stackStrategy": "samesign",
                "cursor": "pointer",
                "barMinHeight": 0,
                "barCategoryGap": "20%",
                "barGap": "30%",
                "large": false,
                "largeThreshold": 400,
                "seriesLayoutBy": "column",
                "datasetIndex": 0,
                "clip": true,
                "zlevel": 0,
                "z": 2,
                "label": {
                    "show": true,
                    "margin": 8,
                    "valueAnimation": false
                }
            },
            {
                "type": "bar",
                "name": "B",
                "legendHoverLink": true,
                "data": [
                    124,
                    74,
                    40,
                    119,
                    56,
                    100,
                    147
                ],
                "realtimeSort": false,
                "showBackground": false,
                "stackStrategy": "samesign",
                "cursor": "pointer",
                "barMinHeight": 0,
                "barCategoryGap": "20%",
                "barGap": "30%",
                "large": false,
                "largeThreshold": 400,
                "seriesLayoutBy": "column",
                "datasetIndex": 0,
                "clip": true,
                "zlevel": 0,
                "z": 2,
                "label": {
                    "show": true,
                    "margin": 8,
                    "valueAnimation": false
                }
            }
        ],
        "timeline": {
            "axisType": "category",
            "currentIndex": 0,
            "orient": "horizontal",
            "autoPlay": true,
            "controlPosition": "left",
            "loop": true,
            "rewind": false,
            "show": true,
            "inverse": false,
            "bottom": "-5px",
            "progress": {},
            "data": [
                "2000\u5e74",
                "2001\u5e74",
                "2002\u5e74",
                "2003\u5e74",
                "2004\u5e74",
                "2005\u5e74",
                "2006\u5e74",
                "2007\u5e74",
                "2008\u5e74",
                "2009\u5e74",
                "2010\u5e74",
                "2011\u5e74",
                "2012\u5e74",
                "2013\u5e74",
                "2014\u5e74",
                "2015\u5e74",
                "2016\u5e74",
                "2017\u5e74",
                "2018\u5e74",
                "2019\u5e74"
            ]
        },
        "xAxis": [
            {
                "show": true,
                "scale": false,
                "nameLocation": "end",
                "nameGap": 15,
                "gridIndex": 0,
                "inverse": false,
                "offset": 0,
                "splitNumber": 5,
                "minInterval": 0,
                "splitLine": {
                    "show": true,
                    "lineStyle": {
                        "show": true,
                        "width": 1,
                        "opacity": 1,
                        "curveness": 0,
                        "type": "solid"
                    }
                },
                "animation": true,
                "animationThreshold": 2000,
                "animationDuration": 1000,
                "animationEasing": "cubicOut",
                "animationDelay": 0,
                "animationDurationUpdate": 300,
                "animationEasingUpdate": "cubicOut",
                "animationDelayUpdate": 0,
                "data": [
                    "\u9999\u8549",
                    "\u68a8\u5b50",
                    "\u6c34\u871c\u6843",
                    "\u6838\u6843",
                    "\u897f\u74dc",
                    "\u82f9\u679c",
                    "\u83e0\u841d"
                ]
            }
        ],
        "yAxis": [
            {
                "show": true,
                "scale": false,
                "nameLocation": "end",
                "nameGap": 15,
                "gridIndex": 0,
                "inverse": false,
                "offset": 0,
                "splitNumber": 5,
                "minInterval": 0,
                "splitLine": {
                    "show": true,
                    "lineStyle": {
                        "show": true,
                        "width": 1,
                        "opacity": 1,
                        "curveness": 0,
                        "type": "solid"
                    }
                },
                "animation": true,
                "animationThreshold": 2000,
                "animationDuration": 1000,
                "animationEasing": "cubicOut",
                "animationDelay": 0,
                "animationDurationUpdate": 300,
                "animationEasingUpdate": "cubicOut",
                "animationDelayUpdate": 0
            }
        ],
        "legend": [
            {
                "data": [
                    "A",
                    "B"
                ],
                "selected": {}
            }
        ]
    },
    "options": [
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        92,
                        27,
                        31,
                        84,
                        40,
                        80,
                        84
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        78,
                        44,
                        96,
                        90,
                        37,
                        78,
                        100
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        58,
                        139,
                        25,
                        149,
                        52,
                        91,
                        116
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        39,
                        85,
                        77,
                        131,
                        57,
                        45,
                        43
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        26,
                        29,
                        117,
                        76,
                        91,
                        145,
                        20
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        57,
                        91,
                        63,
                        148,
                        86,
                        110,
                        80
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        127,
                        25,
                        85,
                        56,
                        62,
                        20,
                        66
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        120,
                        65,
                        110,
                        126,
                        125,
                        121,
                        100
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        68,
                        119,
                        108,
                        25,
                        136,
                        45,
                        97
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        62,
                        81,
                        102,
                        27,
                        64,
                        133,
                        121
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        132,
                        81,
                        49,
                        95,
                        142,
                        23,
                        27
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        41,
                        81,
                        78,
                        89,
                        77,
                        39,
                        98
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        94,
                        134,
                        137,
                        23,
                        87,
                        23,
                        89
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        61,
                        87,
                        82,
                        22,
                        41,
                        63,
                        20
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        74,
                        23,
                        26,
                        81,
                        31,
                        92,
                        36
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        139,
                        39,
                        110,
                        89,
                        129,
                        110,
                        77
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        67,
                        58,
                        68,
                        114,
                        81,
                        69,
                        36
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        136,
                        94,
                        82,
                        26,
                        60,
                        110,
                        78
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        132,
                        80,
                        117,
                        150,
                        147,
                        46,
                        91
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        67,
                        24,
                        148,
                        42,
                        110,
                        111,
                        81
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        95,
                        76,
                        85,
                        46,
                        115,
                        148,
                        132
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        75,
                        96,
                        128,
                        56,
                        82,
                        20,
                        43
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        61,
                        114,
                        132,
                        125,
                        79,
                        108,
                        66
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        111,
                        78,
                        86,
                        81,
                        122,
                        32,
                        79
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        114,
                        70,
                        76,
                        69,
                        106,
                        77,
                        121
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        64,
                        38,
                        100,
                        71,
                        40,
                        97,
                        55
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        40,
                        38,
                        50,
                        39,
                        121,
                        91,
                        116
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        111,
                        35,
                        65,
                        82,
                        55,
                        119,
                        108
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        133,
                        86,
                        87,
                        56,
                        81,
                        134,
                        129
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        75,
                        70,
                        42,
                        125,
                        140,
                        140,
                        131
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        148,
                        145,
                        21,
                        26,
                        143,
                        29,
                        72
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        130,
                        136,
                        24,
                        136,
                        62,
                        94,
                        72
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        67,
                        65,
                        50,
                        74,
                        32,
                        40,
                        132
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        79,
                        101,
                        127,
                        119,
                        59,
                        55,
                        63
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        77,
                        123,
                        127,
                        69,
                        28,
                        73,
                        84
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        147,
                        85,
                        64,
                        109,
                        42,
                        111,
                        104
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        85,
                        95,
                        42,
                        46,
                        64,
                        122,
                        122
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        21,
                        67,
                        44,
                        103,
                        110,
                        90,
                        128
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        },
        {
            "legend": [
                {
                    "data": [
                        "A",
                        "B"
                    ],
                    "selected": {}
                }
            ],
            "series": [
                {
                    "type": "bar",
                    "name": "A",
                    "legendHoverLink": true,
                    "data": [
                        74,
                        56,
                        135,
                        132,
                        95,
                        133,
                        103
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                },
                {
                    "type": "bar",
                    "name": "B",
                    "legendHoverLink": true,
                    "data": [
                        124,
                        74,
                        40,
                        119,
                        56,
                        100,
                        147
                    ],
                    "realtimeSort": false,
                    "showBackground": false,
                    "stackStrategy": "samesign",
                    "cursor": "pointer",
                    "barMinHeight": 0,
                    "barCategoryGap": "20%",
                    "barGap": "30%",
                    "large": false,
                    "largeThreshold": 400,
                    "seriesLayoutBy": "column",
                    "datasetIndex": 0,
                    "clip": true,
                    "zlevel": 0,
                    "z": 2,
                    "label": {
                        "show": true,
                        "margin": 8,
                        "valueAnimation": false
                    }
                }
            ],
            "xAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0,
                    "data": [
                        "\u9999\u8549",
                        "\u68a8\u5b50",
                        "\u6c34\u871c\u6843",
                        "\u6838\u6843",
                        "\u897f\u74dc",
                        "\u82f9\u679c",
                        "\u83e0\u841d"
                    ]
                }
            ],
            "yAxis": [
                {
                    "show": true,
                    "scale": false,
                    "nameLocation": "end",
                    "nameGap": 15,
                    "gridIndex": 0,
                    "inverse": false,
                    "offset": 0,
                    "splitNumber": 5,
                    "minInterval": 0,
                    "splitLine": {
                        "show": true,
                        "lineStyle": {
                            "show": true,
                            "width": 1,
                            "opacity": 1,
                            "curveness": 0,
                            "type": "solid"
                        }
                    },
                    "animation": true,
                    "animationThreshold": 2000,
                    "animationDuration": 1000,
                    "animationEasing": "cubicOut",
                    "animationDelay": 0,
                    "animationDurationUpdate": 300,
                    "animationEasingUpdate": "cubicOut",
                    "animationDelayUpdate": 0
                }
            ],
            "tooltip": {
                "show": true,
                "trigger": "item",
                "triggerOn": "mousemove|click",
                "axisPointer": {
                    "type": "line"
                },
                "showContent": true,
                "alwaysShowContent": false,
                "showDelay": 0,
                "hideDelay": 100,
                "enterable": false,
                "confine": false,
                "appendToBody": false,
                "transitionDuration": 0.4,
                "textStyle": {
                    "fontSize": 14
                },
                "borderWidth": 0,
                "padding": 5,
                "order": "seriesAsc"
            },
            "color": [
                "#5470c6",
                "#91cc75",
                "#fac858",
                "#ee6666",
                "#73c0de",
                "#3ba272",
                "#fc8452",
                "#9a60b4",
                "#ea7ccc"
            ]
        }
    ]
};
        chart_49b90bd150bb4b3eb6216ae3f578d1da.setOption(option_49b90bd150bb4b3eb6216ae3f578d1da);
    </script>
</body>
</html>





```python

```
