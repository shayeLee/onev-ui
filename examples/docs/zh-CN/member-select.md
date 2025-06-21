## 人员选择器


### o-member-select （弹窗形式）

:::demo 

```html
<template>
    <el-button @click="visible=true">
    打开选择器（多选）
    </el-button>
      <el-button @click="visible2=true">
        打开选择器
        </el-button>
        
    <o-member-select multiple :users.sync="users" v-model="email" :visible.sync="visible"></o-member-select>
    <o-member-select  :users.sync="users2" v-model="email2" :visible.sync="visible2"></o-member-select>
    <div>
    多选值:{{email}}
    </div>
    <div>
                单选值:{{email2}}
    
    </div>
</template>
<script>
export  default {
  data(){
    return {
      visible:false,
      email:[],
      users:[],
      users2:'',
      email2:'',
      visible2:false
    }
  }
}
</script>

```
:::

### member-select-trigger

:::demo 

```html
<template>
    <o-member-select-trigger :modal-config="{'close-on-click-modal':false}" multiple :users.sync="users" v-model="email" ></o-member-select-trigger>
    <o-member-select-trigger  :users.sync="users2" v-model="email2" ></o-member-select-trigger>
     <div>
        多选值:{{email}}
        </div>
        <div>
                    单选值:{{email2}}
        
        </div>
</template>
<script>
export  default {
  data(){
    return {
      visible:false,
      email:["yushan@onemt.com.cn", "zhangfangyuan@onemt.com.cn"],
      users:[],
      users2:'',
      email2:"yushan@onemt.com.cn",
      visible2:false
    }
  }
}
</script>
```
:::


###  Attributes
| 参数                  | 说明                                               | 类型                        | 可选值  | 默认值   |
| --------------------- | ---------------------------------------- | --------------------------- | ---- | ----- |
| visible                  | 是否可见 (仅o-member-select)                                           | boolean                       | —    | false     |
| value                  | 邮箱                                           | string/string[]                   | —    | -     |
| multiple                  | 是否多选                                           | boolean                   | —    | false     |
| users                  | 选中的人员数据(可用sync修饰符)                                           | object[]                   | —    | -     |
| type                  | 显示模式（仅o-member-select-trigger）                                           | string                   | chip\avatar-chip\avatar    | -     |
| modalConfig                  | 所有弹窗相关配置                                          | object                   | -    | -     |

###  Events
| 事件名称      | 说明    | 回调参数      |
|---------- |-------- |---------- |
| input  | 点击确认后触发 | 更新后的邮箱 |
| update:users  | 点击确认后触发 | 更新后的人员具体数据 |
