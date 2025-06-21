## window 窗口组件
可拖动的弹出窗口


:::demo 
```html
<el-row>
  <div class="gallery-demo">
    <el-button @click="visible1=!visible1">
        开关弹窗1
    </el-button>
    <el-button @click="handleOpen">
        开关弹窗2
    </el-button>
    <el-button @click="handleOpen2">
        开关弹窗3
    </el-button>
  </div>
  <o-window class="gm-form" :width="1000" :keep-size="true" :inner-screen="true"  :visible.sync="visible1" title="测试窗口1">
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
    <el-button @click="download">下载</el-button>
    <el-select v-model="value" placeholder="请选择">
        <el-option
            v-for="item in options"
            :key="item.value"
            :label="item.label"
            :value="item.value">
        </el-option>
    </el-select>
    <el-input type="textarea" :value="23333333" />
    <div slot="footer">
        底部内容块
    </div>
  </o-window>
  <o-window :auto-update-z-index="false" :visible.sync="visible2" title="测试窗口2测试窗口2测试窗口2测试窗口2">
    <div v-if="render">
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        窗口内容填充<br>
        <div v-if="add">
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            窗口内容填充<br>
            <div v-if="add1">
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
                窗口内容填充<br>
            </div>
        </div>
    </div>
    <div slot="footer">
        底部内容块
    </div>
  </o-window>
  <o-window :height="600" :visible.sync="visible3" title="测试窗口3" :before-close="beforeClose">
    <div v-if="render">
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <span style="white-space: nowrap;">窗口内容填充-窗口内容填充-窗口内容填充-窗口内容填充</span><br>
        <el-button @click="download">下载</el-button>
    </div>
    <div slot="footer">
        底部内容块
    </div>
  </o-window>
</el-row>
<script>
export default {
    data(){
        return {
            visible1:false,
            visible2:false,
            visible3:false,
            render:false,
            add: false,
            add1: false,
            options: [{
                value: '选项1',
                label: '黄金糕'
            }, {
                value: '选项2',
                label: '双皮奶'
            }, {
                value: '选项3',
                label: '蚵仔煎'
            }, {
                value: '选项4',
                label: '龙须面'
            }, {
                value: '选项5',
                label: '北京烤鸭'
            }],
            value: '',
        }
    },
    computed:{
        
    },
    mounted(){

    },
    methods:{
        handleOpen() {
            this.render = false
            this.add = false
            this.add1 = false
            this.visible2 = !this.visible2
            setTimeout(() => {
                this.render = true
            }, 30)
            setTimeout(() => {
                this.add = true
            }, 3000)
            setTimeout(() => {
                this.add1 = true
            }, 3100)
        },
        handleOpen2() {
            this.render = false
            this.visible3 = !this.visible3
            setTimeout(() => {
                this.render = true
            }, 1000)
        },
        async beforeClose(){
            console.log('before close')
            await new Promise((resolve,reject)=>{
                setTimeout(resolve,3000)
            })
            console.log('before close')
        },
        download() {
            window.open("https://sdkstatic.onemt.co/gameshare/kctwn/registration/3bbdeb38ec5c033f94c973ef2f4fc099.otf");
        },
    }
}
</script>


```

:::

### props
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| visible     | 控制显示隐藏   | boolean  |   -            |    false    |
| width     | 弹窗宽度   | number  |   -            |    800   |
| height     | 弹窗高度   | number  |   -            |    undefined   |
| title     | 标题   | string  |   -            |    -    |
| max-width     | 最大宽度   | number  |   -            |    undefined   |
| max-height    | 最大高度   | number  |   -            |    undefined    |
| inner-screen    | 是否锁定在屏幕内   | boolean  |   -            |   true    |
| before-close    | 关闭前调用的方法   | function  |   -            |   -    |
| keepSize   | 是否保持拖拽后的尺寸   | boolean  |   -            |   false    |
| initialPosition   | 初始位置,eg:{x:100,y:150}   | object  |   -            |   undefined    |
| icons   | 右上角图标  | string[]  |   minus \| close            |   ['close']    |


### Events
| 参数      | 触发时机    | 回调参数      |
|---------- |-------- |---------- |
| open     |  打开时  | -  |
| opened     |  打开过度动画完成后  | -  |
| close     |  关闭时  | -  |
| opened     |  关闭过度动画完成后  | -  |



