## topo
topo


:::demo 
```html
<div  >
    <div style="height:500px">
        <o-topo :nodes="nodes" :edges="edges" :options="options" ref="topo" />
    </div>
    <el-button @click="log">
        log
    </el-button>
</div>
<script>
export default {
    data(){
        return {
            nodes:[
                {id: 1, label: 'Node 1',color:{
                    background:'red'
                },shape:'box',x: 45, y: 78},
                {id: 2, label: 'Node 2',shape:'database',x: -152, y: -7},
                {id: 3, label: 'Node 3',x: 208, y: -19},
                {id: 4, label: 'Node 4',x: -297, y: 161},
                {id: 5, label: 'Node 5',x: 77, y: -190}            
            ],
            edges:[
                {from: 3, to: 1,label:'zzzz\nbbbb', smooth: {type: "curvedCCW", roundness: 0.2}},
                {from: 1, to: 3, arrows: 'to', label: "-----", smooth: {type: "curvedCCW", roundness: 0.4}},
              {from: 1, to: 3, arrows: 'to', label: "11111"},
 
                {from: 1, to: 2,color:{color:'green'}},
                {from: 2, to: 4},
                {from: 2, to: 5}
            ],
            options:{
                
            }           
        }
    },
    computed:{
        
    },
    mounted(){
        
    },
    methods:{
        log(){
            console.log(this.$refs.topo.getPositions())
        }   
    }
}
</script>


```

:::

### props
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| visible     | 控制显示隐藏   | boolean  |   -            |    false    |



### Events
| 参数      | 触发时机    | 回调参数      |
|---------- |-------- |---------- |
| open     |  打开时  | -  |




