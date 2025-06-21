## ModuleMenus 多模块菜单布局样板

顶部模块导航，侧边模块菜单列表的布局样板

### 基础用法

:::demo 666

```html
<el-row>
    <div>
        <o-module-menus></o-module-menus>    
    </div>
</el-row>

<script>
    export default {
        data() {
            return {};
        },
        methods: {
            
        }
    };
</script>
```

:::

### Attributes

| 参数          | 说明           | 类型    | 可选值                                      | 默认值       |
| ------------- | -------------- | ------- | ------------------------------------------- | ------------ |
| v-model/value | 绑定值目录下标 | number  | —                                           | —            |
| placement     | 设置时间轴位置 | string  | top/bottom                                  | top          |
| type          | 类型           | string  | primary / success / warning / danger / info | default      |
| icon          | 设置选中的图标 | string  | —                                           | —            |
| height        | 设置滚动高度   | string  | —                                           | 父元素的高度 |
| toggle        | 是否展示列表   | Boolean | —                                           | true         |
| arrow         | 置顶滚动条     | Boolean | —                                           | true         |

### Catalog Events

| 事件名称  | 说明           | 回调参数          |
| --------- | -------------- | ----------------- |
| tab-click | 点击目录时回调 | 选中的 catalog 值 |

### Catalog-pane Attributes

| 参数  | 说明       | 类型   | 可选值 | 默认值 |
| ----- | ---------- | ------ | ------ | ------ |
| label | 选项卡标题 | string | —      | —      |
