## 部门人员 选择器

当选项过多时，使用下拉菜单展示并选择内容。

### 基础用法

部门基础用法
:::demo `v-model`的值为当前被选中的`tree`的 id 属性值

```html
<template>
  <div>
  <el-form ref="form" :model="form" label-width="80px">
    <el-form-item prop="value" label="部门">
      <o-department
      tip="*简单备注说明"
      v-model="form.value"
      collapse-tags
      title="部门多选"
      :tree="options"
      multiple
      clearable
      placeholder="请选择"
    ></o-department>

    <el-form-item>
    <el-button type="primary" @click="submitForm('form')">立即创建</el-button>
    <el-button @click="resetForm('form')">重置</el-button>
  </el-form-item>
    </el-form-item>
  </el-form>



    普通多选
    <o-department
      v-model="value"
      collapse-tags
      disabled
      title="部门多选"
      :tree="options"
      multiple
      clearable
      placeholder="请选择"
    ></o-department>
    <o-department
      v-model="value3"
      title="部门多选"
      :tree="options"
      multiple
      clearable
      placeholder="请选择1"
    ></o-department>
      
    ogs样式
    <o-department
            platform="ogs"
            v-model="value"
            title="部门多选"
            position="center"
            :tree="options"
            multiple
            placeholder="请选择"
    ></o-department>
  </div>

  <div>
    单选 {{value2}}
    <o-department
      v-model="value2"
      size="small"
      title="部门单选"
      clearable
      :tree="options"
      placeholder="请选择"
    ></o-department>
    <o-department
      v-model="value2"
      size="mini"
      :tree="options"
      placeholder="请选择"
    ></o-department>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        form:{
          value:[]
        },
        options: [],
        value: [],
        value2: 7,
        value3: [],
      };
    },
    methods:{
      submitForm(){
        this.$message.info(JSON.stringify(this.form))

      },
      resetForm(formName){
        this.$refs[formName].resetFields();
      }
    },
    mounted(){
      setTimeout(() => {
       this.value = [9, 10, 5194, 15104, 49, 410] 
      }, 500)
      setTimeout(() => {
        this.options = [
            {
            id: 1,
            label: "技术部技术部技术部技术部技术部技术部技术部技术部技术部技术部",
            children: [
                {
                id: 4,
                label: "系统开发组",
                disabled:true,
                children: [
                    {
                    id: 9,
                    label: "php",
                  },
                    {
                    id: 10,
                    label: "前端",
                  },
                ],
              },
                {
                id: 551,
                label: "系统开发组1",
                children: [
                    {
                    id: 519,
                    label: "php1",
                    avatar: "",
                  },
                    {
                    id: 1510,
                    label: "前端1",
                  },
                ],
              },
                {
                id: 5514,
                label: "系统开发组4",
                children: [
                    {
                    id: 5194,
                    label: "php14",
                  },
                    {
                    id: 15104,
                    label: "前端14",
                  },
                ],
              },
                {
                id: 44,
                label: "测试组",
                children: [
                    {
                    id: 49,
                    label: "测试组1",
                  },
                    {
                    id: 410,
                    label: "测试组2",
                  },
                ],
              },
            ],
          },
            {
            id: 2,
            label: "人事部",
            children: [
                {
                id: 5,
                label: "二级 2-1",
              },
                {
                id: 6,
                label: "二级 2-2",
              },
            ],
          },
            {
            id: 3,
            label: "行政部",
            children: [
                {
                id: 7,
                label: "二级 3-1",
              },
                {
                id: 8,
                label: "二级 3-2",
              },
            ],
          },
        ]
      }, 1700)  
    }  
  };
</script>
```

:::

人员选择用法
:::demo

```html
<template>
  <div>
    多选
    <o-department
      v-model="value"
      collapse-tags
      title="人员选择"
      :tree="options"
      multiple
      type="user"
      clearable
      placeholder="请选择"
    ></o-department>
  </div>

  <div>
    单选
    <o-department
      v-model="value2"
      size="small"
      title="人员选择"
      type="user"
      clearable
      :tree="options"
      placeholder="请选择"
    ></o-department>
  </div>
  <div>
      隐藏保存按钮
    <o-department
      v-model="value2"
      size="small"
      title="人员选择"
      type="user"
      clearable
      :tree="options"
      placeholder="请选择"
    ></o-department>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        options: [
          {
            id: 1,
            label: "技术部",
            children: [
              {
                id: 800001,
                type: "user",
                avatar:
                  "",
                label: "常峰(离职)",
              },
              {
                id: 800002,
                type: "user",
                avatar:
                  "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                label: "常峰1",
              },
              {
                id: "800003",
                type: "user",
                avatar:
                  "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                label: "常峰3",
              },
              {
                id: "800004",
                type: "user",
                avatar:
                  "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                label: "常峰4",
              },
              {
                id: 4,
                label: "系统开发组123123fsdfafasdfafafafsdfs",
                children: [
                  {
                    id: 800006,
                    type: "user",
                    avatar:
                      "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                    label: "常峰6常峰6常峰6常峰6常峰6常峰6常峰6常峰6常峰6常峰6常峰6",
                  },
                  {
                    id: 800007,
                    type: "user",
                    avatar:
                      "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                    label: "常峰7sdafasfasfasf常峰7sdafasfasfasf常峰7sdafasfasfasf",
                  },
                ],
              },
              {
                id: 551,
                label: "系统开发组1",
                children: [
                  {
                    id: 800032,
                    type: "user",
                    avatar:
                      "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                    label: "陈某某",
                  },
                  {
                    id: 1510,
                    label: "前端1",
                    children: [
                      {
                        id: "800033",
                        type: "user",
                        avatar:
                          "https://static-legacy.dingtalk.com/media/lADPBbCc1XHROVrNBNrNBNo_1242_1242.jpg",
                        label: "陈4某",
                      },
                    ],
                  },
                ],
              },
              {
                id: 5514,
                label: "系统开发组4",
                children: [
                  {
                    id: 5194,
                    label: "php14",
                  },
                  {
                    id: 15104,
                    label: "前端14",
                  },
                ],
              },
              {
                id: 44,
                label: "测试组",
                children: [
                  {
                    id: 49,
                    label: "测试组1",
                  },
                  {
                    id: 410,
                    label: "测试组2",
                  },
                ],
              },
            ],
          },
          {
            id: 2,
            label: "人事部",
            children: [
              {
                id: 5,
                label: "二级 2-1",
              },
              {
                id: 6,
                label: "二级 2-2",
              },
            ],
          },
          {
            id: 3,
            label: "行政部",
            children: [
              {
                id: 7,
                label: "二级 3-1",
              },
              {
                id: 8,
                label: "二级 3-2",
              },
            ],
          },
        ],
        value: [800006, 800007],
        value2: 800002,
      };
    },
  };
</script>
```

:::

:::tip
如果 Select 的绑定值为对象类型，请务必指定 `value-key` 作为它的唯一性标识。
:::

### Select Attributes

| 参数                  | 说明                                                                           | 类型                      | 可选值            | 默认值     |
| --------------------- | ------------------------------------------------------------------------------ | ------------------------- | ----------------- | ---------- |
| value / v-model       | 绑定值                                                                         | boolean / string / number | —                 | —          |
| multiple              | 是否多选                                                                       | boolean                   | —                 | false      |
| platform              | 使用平台（平台不同，样式和功能可能有不同）                                          | string                    | default/ogs       | default    |
| size                  | 输入框尺寸                                                                     | string                    | medium/small/mini | —          |
| clearable             | 是否可以清空选项                                                               | boolean                   | —                 | false      |
| collapse-tags         | 多选时是否将选中值按文字的形式展示                                             | boolean                   | —                 | false      |
| placeholder           | 占位符                                                                         | string                    | —                 | 请选择     |
| position      | posición del popover en la pantalla      | string         | start/center/end | 
| hide-button      | 隐藏 保存按钮      | boolean         |  true/false |  false

### Select Events

| 事件名称       | 说明                                     | 回调参数                      |
| -------------- | ---------------------------------------- | ----------------------------- |
| change         | 选中值发生变化时触发                     | 目前的选中值                  |
| visible-change | 下拉框出现/隐藏时触发                    | 出现则为 true，隐藏则为 false |
| remove-tag     | 多选模式下移除 tag 时触发                | 移除的 tag 值                 |
| clear          | 可清空的单选模式下用户点击清空按钮时触发 | —                             |
| blur           | 当 input 失去焦点时触发                  | (event: Event)                |
| focus          | 当 input 获得焦点时触发                  | (event: Event)                |




### Option Attributes

| 参数     | 说明                                      | 类型                 | 可选值 | 默认值 |
| -------- | ----------------------------------------- | -------------------- | ------ | ------ |
| value    | 选项的值                                  | string/number/object | —      | —      |
| label    | 选项的标签，若不设置则默认与 `value` 相同 | string/number        | —      | —      |
| disabled | 是否禁用该选项                            | boolean              | —      | false  |

### Methods

| 方法名 | 说明                            | 参数 |
| ------ | ------------------------------- | ---- |
| focus  | 使 input 获取焦点               | -    |
| blur   | 使 input 失去焦点，并隐藏下拉框 | -    |
