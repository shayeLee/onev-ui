## Frame 骨架

用于构建一个视图，界面，应用的结构组件。

### 基本用法


:::demo frame 组件分为主体，头部，底部，左侧，右侧五个部分。

```html
<template>
<div class="demo">
    <o-frame class="demo-o-frame"
    style="height: 500px; width:100%"
    :fillHeader="fillHeader"
    :fillFooter="fillFooter"
    :transition="transition"
    :header-size="headerSize"
    :footer-size="footerSize"
    :left-size="leftSize"
    :right-size="rightSize">
      <div style="height: 100%;width: 100%;background-color: #E7E7E7"></div>
      <div v-if="showHeader" style="height:100%; background-color: #409EFF" class="demo-o-frame-header" slot="header"></div>
      <div v-if="showFooter" style="height:100%; background-color: #409EFF" class="demo-o-frame-footer" slot="footer"></div>
      <div v-if="showLeft" style="height:100%;width:100%; background-color: #B1A2FF" class="demo-o-frame-left" slot="left"></div>
      <div v-if="showRight" style="height:100%;width:100%; background-color: #B1A2FF" class="demo-o-frame-right" slot="right"></div>
    </o-frame>
    
    <div class="demo-handler" style="margin-top: 40px">
            <el-form ref="form" inline label-width="80px">
                <el-form-item label="头部填充">
                   <el-radio-group v-model="fillHeader" size="mini">
                     <el-radio-button label="both"></el-radio-button>
                     <el-radio-button label="none"></el-radio-button>
                     <el-radio-button label="left"></el-radio-button>
                     <el-radio-button label="right"></el-radio-button>
                   </el-radio-group>
                </el-form-item>
                <el-form-item label="底部填充">
                  <el-radio-group v-model="fillFooter" size="mini">
                    <el-radio-button label="both"></el-radio-button>
                    <el-radio-button label="none"></el-radio-button>
                    <el-radio-button label="left"></el-radio-button>
                    <el-radio-button label="right"></el-radio-button>
                  </el-radio-group>
                </el-form-item>
                <el-form-item label="过渡效果">
                  <el-switch v-model="transition"></el-switch>
                </el-form-item>
                <el-form-item label="切换头部">
                  <el-switch v-model="showHeader"></el-switch>
                </el-form-item>
                <el-form-item label="切换底部">
                  <el-switch v-model="showFooter"></el-switch>
                </el-form-item>
                <el-form-item label="切换左栏">
                  <el-switch v-model="showLeft"></el-switch>
                </el-form-item>
                <el-form-item label="切换右栏">
                  <el-switch v-model="showRight"></el-switch>
                </el-form-item>
            </el-form>
    </div>
  </div>
</template>

<script>
export default {
	data () {
		return {
			fillHeader: 'both',
                        fillFooter: 'both',
			showHeader: true,
			showFooter: true,
			showLeft: true,
			showRight: true,
                        headerSize: 50,
                        footerSize: 50,
                        leftSize: 100,
                        rightSize: 100,
                        transition: true
		}
	}
}
</script>

```
:::


### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| fillHeader | 头部布局类型 | string | 'left'/'right'/'both'/'none' | 'both' |
| fillFooter | 底部布局类型 | string | 'left'/'right'/'both'/'none' | 'both' |
| headerSize | 头部尺寸 | Size | - | 50 |
| footerSize | 底部尺寸 | Size | - | 50 |
| leftSize | 左翼尺寸 | Size | - | 100 |
| rightSize | 右翼尺寸 | Size | - | 100 |
| headerIndex | 头部层级 | number | - | 1 |
| footerIndex | 底部层级 | number | - | 1 |
| leftIndex | 左翼层级 | number | - | 1 |
| rightIndex | 右翼层级 | number | - | 1 |
| headerFloat | 头部悬浮 | boolean | - | false |
| footerFloat | 底部悬浮 | boolean | - | false |
| leftFloat | 左翼悬浮 | boolean | - | false |
| rightFloat | 右翼悬浮 | boolean | - | false |
| transition | 部件过渡效果  | boolean | - | false |
### Slots
| 插槽 名称 | 说明  |
|---------- |-------- |
|  | default| 默认插槽 |
| header | 头部 |
| footer | 底部 |
| left | 左翼 |
| right | 右翼 |
