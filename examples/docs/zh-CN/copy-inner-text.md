## v-copy-inner-text

基本用法


:::demo 
```html
<el-row>
  <div class="gallery-demo" v-copy-inner-text>
    asdsadas

    d
    as
    das
    d
    as
    d
  </div>
</el-row>
<script>
export default {
    data(){
        return {
          
        }
    },
    computed:{
        
    },
    mounted(){

    }
}
</script>


```

:::


自定义数据以及开启通知


:::demo 
```html
<el-row>
  <div class="gallery-demo" v-copy-inner-text="{notice:true,data:11111111111,disabled:disabled}">
    asdsadas

    d
    as
    das
    d
    as
    d
  </div>
    <el-button @click="disabled=!disabled">
    {{disabled?'开启':'禁用'}}
    </el-button>
</el-row>
<script>
export default {
    data(){
        return {
          disabled:false
        }
    },
    computed:{
        
    },
    mounted(){

    }
}
</script>


```

:::


### 参数字段说明
| 参数      | 作用    |默认    |
|---------- |-------- |-------- |
|notice |是否有通知提示|false|
|disabled |是否禁用|false|
|data |需要复制的内容，添加这个选项之后将不会复制innertext|-|
|callback |触发复制时调用的回调|-|
