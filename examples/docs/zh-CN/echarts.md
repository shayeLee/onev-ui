## Echarts 图表


### 基础用法


:::demo 

```html
<template>
  <o-echarts type="histogram" :data="chartData" :events="events"></o-echarts>
</template>

<script>
  export default {
    data: function () {
      return {
        chartData: {
          columns: ['日期', '访问用户', '下单用户', '下单率'],
          rows: [
            { '日期': '1/1', '访问用户': 1393, '下单用户': 1093, '下单率': 0.32 },
            { '日期': '1/2', '访问用户': 3530, '下单用户': 3230, '下单率': 0.26 },
            { '日期': '1/3', '访问用户': 2923, '下单用户': 2623, '下单率': 0.76 },
            { '日期': '1/4', '访问用户': 1723, '下单用户': 1423, '下单率': 0.49 },
            { '日期': '1/5', '访问用户': 3792, '下单用户': 3492, '下单率': 0.323 },
            { '日期': '1/6', '访问用户': 4593, '下单用户': 4293, '下单率': 0.78 }
          ],
        },
        events: {
          click: (e) => {
            console.log('rowData =>', this.chartData.rows[e.dataIndex])
            console.log('columnValue =>', this.chartData.rows[e.dataIndex][e.seriesName])
          }
        }
      }
    }
  }
</script>

```

:::

### Attributes
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| type     | 图表类型   | String  |   参考下文            |    []    |

### 图表类型
```
|- lib/
    |- line  -------------- 折线图
    |- bar  --------------- 条形图
    |- histogram  --------- 柱状图
    |- pie  --------------- 饼图
    |- ring  -------------- 环图
    |- funnel  ------------ 漏斗图
    |- waterfall  --------- 瀑布图
    |- radar  ------------- 雷达图
    |- map  --------------- 地图
    |- sankey  ------------ 桑基图
    |- heatmap  ----------- 热力图
    |- scatter  ----------- 散点图
    |- candle  ------------ k线图
    |- gauge  ------------- 仪表盘
    |- tree  -------------- 树图
    |- bmap  -------------- 百度地图
    |- amap  -------------- 高德地图
```

### 其他属性
参考[v-charts](https://v-charts.js.org/#/props)组件文档，OEcharts上除type的其他属性都会被v-charts继承


