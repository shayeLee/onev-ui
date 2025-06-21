## Gallery 图片浏览器
图片浏览组件

### 基础用法


:::demo 

```html
<el-row>
  <div class="gallery-demo">
    <img @click="index=imgIndex" v-for="(i,imgIndex) in imgs" :src="i" alt="" style="width: 100px">
  </div>
  <o-gallery :options="options" :images="_imgs" :index.sync="index"/>
</el-row>
<script>
export default {
    data(){
        return {
            index:null,
            imgs:[
                require('../../assets/images/1.99.jpg'),
                require('../../assets/images/compo-2.png'),
                require('../../assets/images/compo-3.png'),
                require('../../assets/images/compo-3.png'),
                require('../../assets/images/compo-3.png'),
                require('../../assets/images/compo-3.png'),
                require('../../assets/images/compo-3.png'),
                require('../../assets/images/compo-3.png'),
                require('../../assets/images/compo-3.png'),
            ],
            options:{
              closeOnSlideClick:false,
                // The tag name, Id, element or querySelector of the indicator container:
                indicatorContainer: '.indicator',
                // The class for the active indicator:
                activeIndicatorClass: 'active',
                // The list object property (or data attribute) with the thumbnail URL,
                // used as alternative to a thumbnail child element:
                thumbnailProperty: 'thumbnail',
                // Defines if the gallery indicators should display a thumbnail:
                thumbnailIndicators: true,
                
            }
        }
    },
    computed:{
        _imgs(){
            return [...this.imgs].map(i=>({
                        thumbnail:i,
                        title: 'asdasdsa',
                        href: i,
                        //type: 'image/jpeg',
                        description:'asdasd'
                    }))
        }
    },
    mounted(){
    }
}
</script>


```

:::

### Attributes
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| images     | 图片资源   | Array<String\|Object>  |   -            |    []    |
| index     | 当前的图片序号，可用.sync绑定   | number  |   -            |    -    |
| close     | 关闭图标是否显示   | Boolean  |  true/false         |   true |
| options     | blueimp Gallery库参数，参照[文档](https://github.com/blueimp/Gallery#options)   | number  |   -            |    -    |

### 图片为对象时字段说明
| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| thumbnail     | 缩略图   | String  |   -            |    -    |
| title     | 左上角标题   | String  |   -            |    -    |
| description     | 左上角描述   | String  |   -            |    -    |
| href     | 图片地址   | String  |   -            |    -    |

### Events
| 参数      | 触发时机    | 回调参数      |
|---------- |-------- |---------- |
| onopen     |  gallery初始化时  | ({index:number,slide:dom})  |
| onopened     | gallery完成初始化   | ({index:number,slide:dom})   |
| onslide     |  开始滑动  | ({index:number,slide:dom})   |
| onslideend     |  滑动完成  | ({index:number,slide:dom})   |
| onslidecomplete     |  图片加载完毕  | ({index:number,slide:dom})   |
| onclose     |  弹窗关闭前 | ({index:number,slide:dom})   |
| onclosed     |  弹窗关闭后  | ({index:number,slide:dom})   |
| slide-click     |  图片被点击  | 点中的图片序号  |


