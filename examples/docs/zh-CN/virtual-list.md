## 虚拟列表
虚拟列表

### 使用props.list渲染

:::demo 
```html
<div style="height:300px">
  <o-virtual-list :list="data" @scroll-end="loadData" :item-min-height="18">
  </o-virtual-list>
</div> 
<script>
export default {
    data(){
        const data=new Array(1000).fill(null).map((_,i)=>({
          id:i,
          render:h=>h('div',[`list item ${i}`])
          }))
        return {
           data
        }
    },
    computed:{
        
    },
    mounted(){

    },
    methods:{
        async beforeClose(){
            console.log('before close')
            await new Promise((resolve,reject)=>{
                setTimeout(resolve,3000)
            })
            console.log('before close')
        },
        loadData(){
          console.log('loadData')
        }
    }
}
</script>

```
:::

### 使用slot渲染

:::demo 
```html
<div style="height:300px">
  <o-virtual-list use-slot :list="data" @scroll-end="loadData" :item-min-height="18">
    <div v-for="i in data" :key="i.id">
      list item {{i.id}}
    </div>
  </o-virtual-list>
</div> 
<script>
export default {
    data(){
        const data=new Array(1000).fill(null).map((_,i)=>({
          id:i,
          render:h=>h('div',[`list item ${i}`])
          }))
        return {
           data
        }
    },
    computed:{
        
    },
    mounted(){

    },
    methods:{
        async beforeClose(){
            console.log('before close')
            await new Promise((resolve,reject)=>{
                setTimeout(resolve,3000)
            })
            console.log('before close')
        },
        loadData(){
          console.log('loadData')
        }
    }
}
</script>

```
:::

##### props

| 名称      | 类型                             | 默认值 | 说明                   | 必须 |
| --------- | -------------------------------- | ------ | ---------------------- | ---- |
| list | Array\<ListItem\> | []    | 列表数据 | n    |
| itemMinHeight | number | 30 | 列表项最小高度，在列表项还没渲染时作为高度使用 | n |
| throttleTime | number | 300 | 渲染列表计算间隔 | n |
| outsideRemain | number | 10 | 屏幕上下边缘外的列表项保留个数 | n |


##### slots

| 名称   | 位置         |
| ------ | ------------ |
| before | 列表区域以上 |
| after  | 列表区域以下 |



