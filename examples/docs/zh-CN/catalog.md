## Catalog 目录

目录用法，在父级元素支持滚动的情况下生效。


### 基础用法

目录默认为底部显示，目前只允许一级目录与二级目录功能，为保持美观，目录名称不宜过长。

:::demo 

```html
<el-row>
 <div style="height: 500px">
<div>
 <el-button><div @click="list.shift()">删除</div></el-button>
 <el-button><div @click="list.push({value:'mulu'})">添加</div></el-button>
</div>
 <o-catalog  @change="openFullScreen"  :pageSize="8" >
      <o-catalog-pane  style="height: 400px;" :label="test"><div>牛逼咯</div></o-catalog-pane>
      <o-catalog-pane label="目录二">
             <div  style="height: 200px;">我的生命之道就是吃吃吃吃</div>
             <o-catalog-pane  style="height: 200px;"  v-for="(tip,index) in list" :label="tip.value" :key="index">{{tip.value}}</o-catalog-pane>
      </o-catalog-pane>
      <o-catalog-pane  style="height: 400px;" label="目录三">目录三</o-catalog-pane>
      <o-catalog-pane  style="height: 400px;" label="目录四">目录四</o-catalog-pane>
      <o-catalog-pane  style="height: 400px;" label="目录五">目录五</o-catalog-pane>
 </o-catalog>
</div>
</el-row>

<script>
  export default {
     data(){
        return {
            list:[],
            test:'测试标题',
        }
    },
    methods: {
      openFullScreen(val) {

      },
     
    },
    mounted(){
             let arr=[];
             for(let i=0;i<3;i++){
                 let data={
                     value:'目录'+i
                 }
                 arr.push(data);
             }
             this.list=arr;
        }

  }
</script>
```
:::

### 添加目录翻页工功能

目录支持翻页功能。

:::demo 

```html
<el-row>
<el-button type="text" @click="addData">点击</el-button>
<el-button type="text" @click="deleteF">切换数据</el-button>
<el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
   v-if='dialogVisible'
>
   <div style="height: 500px">
   <o-catalog :pageSize="8" type="danger" :toggle="true"  :arrow="true">
        <o-catalog-pane  style="height: 400px;" label="目录一" ><span> 目录一</span></o-catalog-pane>
        <o-catalog-pane label="目录二">
               <o-catalog-pane  style="height: 200px;" :label="tab.value" v-for="(tab,index) in list" :key="index">
                  <div>{{tab.value}}</div>
                </o-catalog-pane>
        </o-catalog-pane>
        <o-catalog-pane  style="height: 500px;" label="目录三">             
        <div  style="height: 200px;">我的生命之道就是吃吃吃吃</div>
         </o-catalog-pane>
        <o-catalog-pane  style="height: 400px;" label="目录四">目录四</o-catalog-pane>
        <o-catalog-pane  style="height: 900px;" label="目录五">目录五</o-catalog-pane>
   </o-catalog>
  </div>
   <div slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
   </div>     
</el-dialog>

</el-row>
<script>
  export default {
     data(){
        return {
            list:[],
            tab:10,
            dialogVisible: false
        }
    },
    methods: {
      openFullScreen() {
      },
      deleteF(){
         this.dialogVisible=true;
          let arr=[];
          let len=Math.floor(Math.random()*10);  
                   for(let i=0;i<=len;i++){
                       let data={
                           value:'目录重新排序'+i
                       }
                       arr.push(data);
                   }
           this.list=arr;

      },
      addData(){
         this.dialogVisible=true;
          let arr=[];
                   for(let i=0;i<20;i++){
                       let data={
                           value:'目录'+i
                       }
                       arr.push(data);
                   }
                   this.list=arr;
      }
    }
  
  }
</script>


```
:::

### 列表显示（隐藏）以及滚动条置顶
可根据实际场景自定义节点主题或直接使用图标。

:::demo 使用`toggle`列表显示隐藏功能，`arrow`滚动条置顶功能，`placement`滚动条位置。

```html
<el-row>
 <div style="height: 500px">
 <o-catalog type="warning" @tab-click="openFullScreen"  placement="top" :toggle="true"  :arrow="true" color="#333">
      <o-catalog-pane style="color: red ;height: 400px;" label="目录一" v-if="showT">
      <div @click="deleteF"> 目录一点击事件测试</div>
</o-catalog-pane>
      <o-catalog-pane style="color: skyblue;height: 200px;" label="目录二">目录二</o-catalog-pane>
      <o-catalog-pane style="color: red;height: 500px;" label="目录三">目录三</o-catalog-pane>
      <o-catalog-pane style="color: skyblue;height: 400px;" label="目录四">
            <div>智人是机会主义的杂食动物，在提取、生产、加工和保存食物方面表现出卓越的独创性。<br/>
            智人是唯一可以控制或开火的物种，所有已知的现存智人群体都在进行烹饪。<br/>饮食的区域差异受特定环境中的可获得性，<br/>
            文化传统如食物偏好和避免以及遗传因素的影响。乳糖酶的持久性允许一<br/>些智人在一生中消费牛奶和乳制品，这是最近对乳制品消费的适应性调整<br/>
            ，这只会在具有奶牛养殖传统的智人中发挥作用</div>
     </o-catalog-pane>
 </o-catalog>
</div>
</el-row>

<script>
  export default {
     data(){
        return {
            showT:true
        }
    },
    methods: {
      openFullScreen() {
      },
      deleteF(){
          this.showT=false;
      }
    },
 
  
  }
</script>

```
:::

### Attributes
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| placement | 设置时间轴位置| string| top/bottom | top |
| type | 类型 | string| primary / success / warning / danger / info  | default |
| color | 未选中的文字颜色 | string| hex  | #ddd |
| icon | 设置选中的图标 | string| — | — |
| height | 设置滚动高度 | string| — | 父元素的高度 |
| toggle | 是否展示列表 | Boolean| — | true |
| arrow | 置顶滚动条 | Boolean| — | true |
| pageSize | 滚动条显示条数 | number| — | —  |
### Catalog Events
| 事件名称      | 说明    | 回调参数      |
|---------- |-------- |---------- |
| tab-click  | 点击目录时回调 | 选中的 catalog 值 |
| change  | 目录变化回调 |  catalog 值 |

### Catalog-pane Attributes
| 参数       | 说明     | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| label     | 选项卡标题   | string   | — |    —     |
