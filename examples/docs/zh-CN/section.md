## Section 段落组件

用于展示文本段落。

### 基本用法


:::demo section 组件。

```html
<template>
  <div class="demo">
    <o-section dir="rtl" class="m-md" :font-size="14"  :ellipsis="3" style="background-color: white">
            h啊实打实h啊实打实h啊实打实
            h啊实打实
            h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实
            h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实
            h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实h啊实打实
            h啊实打实h啊实打实h啊实打实
    </o-section>
  </div>
</template>
```
:::


### Attributes
| 参数      | 说明          | 类型      | 可选值    | 默认值  |
|---------- |-------------- |---------- |------------ |-------- |
| fontSize | 字体 | string / number | — | 14 |
| lineHeight | 行高，只能是数字，字体的倍数，比如 1.5 | — | 1.5 |
| ellipsis | 行数限制， 0 表示没有限制 | number | — | 0 |
