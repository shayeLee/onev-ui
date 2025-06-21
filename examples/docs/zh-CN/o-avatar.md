## Avatar 头像

用于丰富页面多媒体。

### 基本用法


:::demo avatar 组件提供五种默认尺寸。

```html
<template>
  <div class="demo">
          <o-avatar v-for="(breakpoint,bi) in ['xs', 'sm', 'md', 'lg', 'xl']"
            :key="bi"
            :size="breakpoint"
            type="circle"
            closeable
            src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3684399326,3232919480&fm=26&gp=0.jpg">
            {{breakpoint}}
          </o-avatar>
            <o-avatar v-for="(type,ti) in ['square', 'corner', 'round', 'circle']"
              :key="ti+1000"
              size="md"
              :type="type"
              hoverable
              src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3684399326,3232919480&fm=26&gp=0.jpg">
              {{type}}
            </o-avatar>
  </div>
</template>
```
:::


### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| shape | 形状 | string | circle/round/corner/square | circle |
| size | 图片的尺寸,可传入字符串或者数字，传入数字则单位为px,传入xs,sm,md,lg,xg则展示对应的预设尺寸，否则为字符串单位，像'50px' | 'xs'/'sm'/'md'/'lg'/'xl'/string/number | — | md |
| src | 图片url | string | — | — |
|name|没有图片时显示的文字, 同默认slot |String|-|----
|fontSize|文字大小|Number|-|12
|sliceStart|是否从文字开头截取|Boolean|-|false
|lengthLimit|截取文字的长度|Number|-|2
|closeable|是否显示关闭按钮|Boolean|-|false
|hoverable|是否显示hover的头像边框|Boolean|-|false
### Slots
| 插槽 名称 | 说明  |
|---------- |-------- |
| - | 头像的文字 |

### Events
| 事件名称 | 说明 | 回调参数 |
|---------- |-------- |---------- |
| close | 点击关闭按钮的回调 | — |
