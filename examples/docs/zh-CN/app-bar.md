## AppBar 工具条

用于丰富页面多媒体。

### 基本用法


:::demo app-bar 组件提供五种默认尺寸。

```html
<template>
        <div class="box">
          <div class="top">
              <el-button class="item" @click="fixed = 'top-start'">上左</el-button>
              <el-button class="item" @click="fixed = 'top'">上边</el-button>
              <el-button class="item" @click="fixed = 'top-end'">上右</el-button>
          </div>
          <div class="left">
              <el-button class="item" @click="fixed = 'left-start'">左上</el-button>
              <el-button class="item" @click="fixed = 'left'">左边</el-button>
              <el-button class="item" @click="fixed = 'left-end'">左下</el-button>
          </div>
          <div class="right">
              <el-button class="item" @click="fixed = 'right-start'">右上</el-button>
              <el-button class="item" @click="fixed = 'right'">右边</el-button>
              <el-button class="item" @click="fixed = 'right-end'">右下</el-button>
          </div>
          <div class="bottom">
              <el-button class="item" @click="fixed = 'bottom-start'">下左</el-button>
              <el-button class="item" @click="fixed = 'bottom'">下边</el-button>
              <el-button class="item" @click="fixed = 'bottom-end'">下右</el-button>
          </div>
          <o-app-bar :fixed="fixed" :block="block" :size="size">
            <div slot="left" class="px-md py-md">左插槽 </div>
            <div slot="right" class="px-md py-md">右插槽 </div>
          工具条  工具条  工具条  工具条
            工具条  工具条  工具条  工具条
              工具条  工具条  工具条  工具条
                工具条  工具条  工具条  工具条
                  工具条  工具条  工具条  工具条
                    工具条  工具条  工具条  工具条
                      工具条  工具条  工具条  工具条
                        工具条  工具条  工具条  工具条
                          工具条  工具条  工具条  工具条
                            工具条  工具条  工具条  工具条
                              工具条  工具条  工具条  工具条
                                工具条  工具条  工具条  工具条
                                  工具条  工具条  工具条  工具条
                                    工具条  工具条  工具条  工具条
                                      工具条  工具条  工具条  工具条
                                        工具条  工具条  工具条  工具条
                                          工具条  工具条  工具条  工具条
                                            工具条  工具条  工具条  工具条
                                              工具条  工具条  工具条  工具条
                                                工具条  工具条  工具条  工具条
          </o-app-bar>
        </div>
</template>
<script>
        export default {
         data(){
             return {
                fixed: 'none',
                block: true,
                size: 'md',
             }
         },
         computed:{
             
         },
         methods: {
                handleFixed (val) {
                        this.fixed = val
                }
         },
         mounted(){
        
         }
        }
</script>
```
:::

### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| size | 组件的尺寸,可传入字符串或者数字，传入数字则单位为px,传入xs,sm,md,lg,xg则展示对应的预设尺寸，否则为字符串单位，像'50px' | 'xs'/'sm'/'md'/'lg'/'xl'/string/number | — | md |
| block |块级工具条 |String|-|----
| fixed |定位的位置  | String  |  none/top/top-start/top-end/bottom/bottom-start/bottom-end/left/left-start/left-end/right/right-start/right-end |  none |

### Slots
| 插槽 名称 | 说明  |
|---------- |-------- |
| - | 默认内容插槽 |
| left | 左侧内容 |
| right | 右侧内容 |
