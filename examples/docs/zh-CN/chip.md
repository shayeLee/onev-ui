## Chip 标签(material风格)

material风格标签, 用于标记和选择。

### 基本用法

页面中的非浮层元素，不会自动消失。

:::demo 组件提供五种主题，五种尺寸。
```html
<template>
  <div class="demo" >
                <div class="mb-sm">
                        <o-chip v-for="(breakpoint,bi) in ['xs', 'sm', 'md', 'lg', 'xl']"
                          :key="bi"
                          :size="breakpoint"
                          class="mr-sm"
                          shape="circle"
                          closeable closeover>
                          {{breakpoint}}
                        </o-chip>
                </div>
                <div class="mb-sm">
                  <o-chip v-for="(shape,si) in ['square', 'corner', 'round', 'circle']"
                          :key="si"
                          size="md"
                          :shape="shape"
                          class="mr-sm"
                          closeable closeover>
                    <o-avatar slot="media"
                                                      size="md"
                                                     :shape="shape"
                                                     src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3684399326,3232919480&fm=26&gp=0.jpg">
                                         
                                                   </o-avatar>
                          {{shape}}
                        </o-chip>
                </div>
                       <div class="mb-sm">
                                  <o-chip v-for="(color,ci) in ['default', 'primary', 'success', 'info', 'warning', 'danger']"
                                          :key="ci"
                                          size="md"
                                          :color="color"
                                          class="mr-sm"
                                          shape="circle"
                                          closeable closeover>
                                          {{color}}
                                        </o-chip>
                                </div>
                <div class="mb-sm">
                   <o-chip size="md"
                                     color="primary"
                                     class="mr-sm"
                                     shape="circle"
                                     closeable closeover>
                                  <o-avatar slot="media"
                                            size="md"
                                           shape="circle"
                                           src="https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=3684399326,3232919480&fm=26&gp=0.jpg">
                                       
                                         </o-avatar>
                                     media-slot
                           </o-chip>
                </div>
  </div>
</template>
```
:::


### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| shape | 形状 | string | circle/corner/round/square | circle |
| size | 图片的尺寸,可传入字符串或者数字，传入数字则单位为px,传入xs,sm,md,lg,xg则展示对应的预设尺寸，否则为字符串单位，像'10vh' | string/number | — | md |
| src | 图片url | string | — | — |
| closeable |是否显示关闭按钮|Boolean|-|false
| closeover|关闭按钮hover切换 |Boolean|-|false

### Slots
| 事件名称 | 说明 | 回调参数 |
|---------- |-------- |---------- |
| media | 富媒体插槽 | — |
| - | 文字 | — |

### Events
| 事件名称 | 说明 | 回调参数 |
|---------- |-------- |---------- |
| close | 点击关闭按钮的回调 | — |
