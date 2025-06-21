## Popover下拉选框



### 基础用法



:::demo
```html
<div>
<o-popover-select    style="margin-left:10px" v-model="value1">
    <o-popover-option :disabled="item%2===0" v-bind="item" v-for="(item,i) in options" :key="i">
    </o-popover-option>
</o-popover-select>
<o-popover-select  disabled  style="margin-left:10px" >
    <o-popover-option :disabled="item%2===0" v-bind="item" v-for="(item,i) in options" :key="i">

    </o-popover-option>
</o-popover-select>
<o-popover-select filterable multiple style="margin-left:10px" v-model="value2">
    <o-popover-option :disabled="item%2===0" v-bind="item" v-for="(item,i) in options.concat(options, options, options, options)" :key="i">

    </o-popover-option>
</o-popover-select>
<o-popover-select   multiple style="margin-left:10px" v-model="value2">
    <o-popover-option :disabled="item%2===0" v-bind="item" v-for="(item,i) in options" :key="i">
    </o-popover-option>
</o-popover-select>
<o-popover-select   multiple style="margin-left:10px" v-model="value2">
    <span slot="reference" style="cursor: pointer">
        自定义 reference
    </span>
    <o-popover-option :disabled="item%2===0" v-bind="item" v-for="(item,i) in options" :key="i">
    </o-popover-option>
</o-popover-select>
</div>
</div>
<script>
    export default {
      data() {
        return {
          value1:null,
          value2:['Beijing'],
          options:[{
                            value: 'Beijing',
                            label: '北京'
                          }, {
                            value: 'Shanghai',
                            label: '上海'
                          }, {
                            value: 'Nanjing',
                            label: '南京'
                          }, {
                            value: 'Chengdu',
                            label: '成都'
                          }, {
                            value: 'Shenzhen',
                            label: '深圳'
                          }, {
                            value: 'Guangzhou',
                            label: '广州'
                          }]
        };
      },
      methods: {
        open(val) {
          this.dialogVisible = true
        },
        mkArray(num){
          return new Array(num)
        }
      }
    }
</script>
```
:::





### Select Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| size   | 显示尺寸 | string | mini,small,normal | mini |
| placeholder   | placeholder | string | - | 请选择 |
| value / v-model   | 绑定值 | any | - | - |
| multiple    | 是否多选 | boolean |-| false |
| disabled    | 是否禁用 | boolean |-| false |
| filterable    | 是否可搜索 | boolean |-| false |


### Select Events
| 事件名称 | 说明 | 回调参数 |
|------|--------|----|
| input| 选中时触发 |选中值|
| change| 选中时触发 |选中值|




### Select Slot
| name | 说明 |
|------|--------|
| — | 下拉框区域 |
| reference | 触发 Popover 显示的 HTML 元素 |

### Option Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| label   | 选项的标签，若不设置则默认与 value 相同 | string | -| - |
| value   | 选项的值 | any | - | - |
| disabled   | 	是否禁用该选项 | boolean | - | 禁用 |

