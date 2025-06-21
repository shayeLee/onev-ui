## Notice 公告通知

用于页面中展示通知。

### 基本用法

:::demo 属性`msg`必传。
```html
<template>
    <o-notice msg="这是一条通知公告&nbsp;&nbsp&nbsp&nbsp777"></o-notice>
</template>
```
:::

### 文字超出容器宽度

:::demo 
```html
<template>
    <o-notice msg="这是一条很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长很长的很长很长很长很长很长很长通知公告"></o-notice>
</template>
```
:::

### 属性`msg`值为无效值

:::demo
```html
<template>
    <p>msg=''</p>
    <o-notice msg="" style="margin-bottom: 20px;"></o-notice>
    <p>msg=true</p>
    <o-notice :msg="true"></o-notice>
</template>
```
:::

### 关闭提示

:::demo
```html
<template>
    <o-notice msg="这是一条通知公告这是一条通知公告这是一条通知公告这是一条通知公告" :before-close="handleClose"></o-notice>
</template>
<script>
    export default {
        methods: {
             handleClose(msg) {
                return this.$confirm('确认要关闭公告吗?', '提示', {
                  confirmButtonText: '确定',
                  cancelButtonText: '取消',
                  type: 'warning'
                })
             }
        }
    }
</script>
```
:::

### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| msg       | 通知内容       | string    | 必传                              | — |

### Events
| 事件名称 | 说明 | 回调参数 |
|---------- |-------- |---------- |
| close | 关闭时触发的事件 | msg |
