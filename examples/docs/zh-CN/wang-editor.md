## wang-editor

富文本

### 输入

:::demo
```html
<el-row>
    <o-wang-editor v-model="text3" :tools="tools" paste-ignore-style @extend="extend" :uploadHandler="uploadHandler"/>
</el-row>
<script>
    export default {
        data() {
            return {
                text3: '<p>撒娇啦放假啦解放啦component lists rendered\r换行 \r\n 测试\r测试测试测试测试测试测试<p/>',
                tools: [
                    'bold',
                    'fontSize',
                    'italic',
                    'underline',
                    'strikeThrough',
                    'indent',
                    'lineHeight',
                    'foreColor',
                    'backColor',
                    'list',
                    'justify',
                    'emoticon',
                    'splitLine',
                    'undo',
                    'redo',
                    'table',
                    'copyHTML'
                ]
            }
        },
        computed: {},
        mounted() {

        },
        methods: {
            uploadHandler(file, cb) {
                return new Promise((resolve, reject) => {
                    const reader = new FileReader()
                    setTimeout(() => {
                        reader.readAsDataURL(file);
                        const str = window.btoa(file)
                        reader.onload = () => {
                            cb(reader.result, file.name)
                            resolve()
                        };
                    }, 3000)
                })
            },
            extend(editor) {
                editor.cmd.do('insertHTML', '<color=0000FF><url=5|www.baidu.com>百度</url></color>');
            }
        }
    }
</script>
```
:::

### 隐藏全屏按钮

:::demo 
```html

<el-row>
    <o-wang-editor :show-full-screen="false" v-model="text3" :tools="tools" paste-ignore-style @extend="extend" :uploadHandler="uploadHandler" />
</el-row>
<script>
    export default {
        data() {
            return {
                text3: '<p>撒娇啦放假啦解放啦component lists rendered\r换行 \r\n 测试\r测试测试测试测试测试测试<p/>',
                tools: [
                    'bold',
                    'fontSize',
                    'italic',
                ]
            }
        },
        computed: {},
        mounted() {

        },
        methods: {
            uploadHandler(file, cb) {
                return new Promise((resolve, reject) => {
                    const reader = new FileReader()
                    setTimeout(() => {
                        reader.readAsDataURL(file);
                        const str = window.btoa(file)
                        reader.onload = () => {
                            cb(reader.result, file.name)
                            resolve()
                        };
                    }, 3000)
                })
            },
            extend(editor) {
                editor.cmd.do('insertHTML', '<color=0000FF><url=5|www.baidu.com>百度</url></color>');
            }
        }
    }
</script>
```
:::

### props

| 参数      | 说明    | 类型      | 可选值       | 默认值   |
|---------- |-------- |---------- |-------------  |-------- |
| value     |   初始值（可用v-model绑定） | string  |   -          |    -    |
| uploadHandler     |   图片上传回调 | (file:File,cb:Function)=>Promise\<void\>  <br>上传file之后调用 cb(url,text) 在编辑器中插入图片  |   -          |    ()=>{}    |
| show-rtl     |   显示反向 |   |      Boolean       |    false    |

### Events

| 参数      | 触发时机    | 回调参数      |
|---------- |-------- |---------- |
| input     |  It would be emitted when editor fully load  | -  |
| change     |  It would be emitted when content changed  | -  |
| focus     |  It would be emitted when format change by cursor position  | -  |
| blur      |  It would be emitted when editor get focus  | -  |
