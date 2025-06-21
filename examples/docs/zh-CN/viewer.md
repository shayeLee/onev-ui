## Viewer 图片查看
图片查看组件

### 基础用法

:::demo
```html
<el-row>
  <div>
    <img v-for="(img, i) of imgs" :src="img" width="160" @click="index=i" />
  </div>
  <o-viewer ref="viewer" :images="imgs" :index.sync="index" :close="close"></o-viewer>
  <div>
    <el-button type="primary" @click="addImg">增加一张图片</el-button>
  </div>
</el-row>
<script>
  export default {
    data() {
      return {
        close: false,
        index: -1,
        newImg: require("../../assets/images/compo-2.png"),
        imgs: [
          require("../../assets/images/1.99.jpg"),
          require("../../assets/images/compo-2.png")
        ]
      }
    },
    methods: {
      addImg() {
        this.imgs = this.imgs.concat([this.newImg]);
        this.$refs.viewer.view(0)
      }
    }
  }
</script>
```
:::

### Attributes
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| images     | 图片地址   | Array  |   -            |    必传    |
| index     | 当前的图片序号，可用.sync绑定   | number  |   -            |    必传    |
| close     | 关闭图标是否显示   | boolean  |  true/false         |   true |
| options     | viewer.js选项，参照[文档](https://github.com/fengyuanchen/viewerjs#options)   | object  |   -            |    -    |

### 图片为对象时字段说明
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| href     | 图片地址   | string  |   -            |    -    |