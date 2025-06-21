## Quill 富文本



### 默认用法

:::demo
```html
<div>
<o-quill v-model="content"></o-quill>

</div>
<script>
  export default {
      data() {
        return {
          content: `<p>       今天我们   将从吟游诗人留   下的一篇文献中，来探索一个游戏中英雄的神秘身世，这篇文献记录了吟游诗人与一位欧斯曼帝国的将领的偶遇，看看大家是否能从以下对话中，猜测出英雄的真实身份。<p/><p>xx}<p/><p>1、这是一名橙色品质的男性英雄<p/><p>2_cn.png}<p/><p>2、这是一名战争类型的英雄<p/><p>3、出征时，他能够让盾兵和矛兵的暴击率提升<p/><p>故事到这里就结束了，那么大家从上面的对话中，是否猜测出这名英雄的真实身份了呢？（是一名游戏中的英雄），大家可以在评论下方进行讨论并留下你认为的英雄名字，我们将从猜测正确的玩家中，随机抽取50名发放奖励。<p/>`,
          ImageExtend:{
            loading: true,  // 可选参cursorLocation数 是否显示上传进度和提示语
             name: 'file',  // 图片参数名
             size: 3,  // 可选参数 图片大小，单位为M，1M = 1024kb
             action: 'http://kohmgrbeta.community.onemt.cc/file/uploadImage',  // 服务器地址, 如果action为空，则采用base64插入图片
             // response 为一个函数用来获取服务器返回的具体图片地址
             // 例如服务器返回{code: 200; data:{ url: 'baidu.com'}}
             // 则 return res.data.url
             response: (res) => {
                 return 'http://sdkcoimagedebug.onemt.co/'+res.rspData[0]
             },
             headers: (xhr) => {},  // 可选参数 设置请求头部
             sizeError: () => {},  // 图片超过大小的回调
             start: () => {},  // 可选参数 自定义开始上传触发事件
             end: () => {},  // 可选参数 自定义上传结束触发的事件，无论成功或者失败
             error: () => {},  // 可选参数 上传失败触发的事件
             success: () => {},  // 可选参数  上传成功触发的事件
             change: (xhr, formData) => {} // 可选参数 选择图片触发，也可用来设置头部，但比headers多了一个参数，可设置formData
                    }
        };
      },
      methods: {
        
      }
    }
</script>
```
:::


### 社区话题

:::demo
```html
<div>
<o-quill v-model="content2"   topic="#"   @topic-handle="topicHandle"></o-quill>
</div>

<script>
const tableOptions = [];
const maxRows = 10;
const maxCols = 5;
for (let r = 1; r <= maxRows; r++) {
    for (let c = 1; c <= maxCols; c++) {
        tableOptions.push('newtable_' + r + '_' + c);
    }
}
  export default {
      data() {
        return {
          content2: '',
        };
      },
      methods: {
        topicHandle({Editor,cursorLocation,range}){
                    let innerText = '#23423'
                     let length = Editor.selection.savedRange.index
                     Editor.insertText(length,' ')
                     Editor.insertText(length+1,' ')
                     Editor.insertEmbed(cursorLocation+1, "link",{href:'http://www.baidu.com', innerText:innerText,id:'324',topic:true},'api');
                     Editor.setSelection(length + innerText.length + 2)
                }
      }
    }
</script>
```
:::


### 自定义参数

:::demo
```html
<div>
<o-quill v-model="content2"  :editor-toolbar="customToolbar"></o-quill>

</div>

<script>
const tableOptions = [];
const maxRows = 10;
const maxCols = 5;
for (let r = 1; r <= maxRows; r++) {
    for (let c = 1; c <= maxCols; c++) {
        tableOptions.push('newtable_' + r + '_' + c);
    }
}
  export default {
      data() {
        return {
          content2: '',
          customToolbar: [
            ["bold", "italic", "underline"],
            [{ list: "ordered" }, { list: "bullet" }],
            ['emoji'], 
            [{'direction': 'rtl'}],
            [{'size': ['12px','14px','16px','18px','20px','22px','24px','28px','30px']}],
            [{'header': [1, 2, 3, 4, 5, 6, false]}],
            [{'align': ['align','center','right','justify']}],
            [{'color': []}, {'background': []}], 
          ],
          
        };
      },
      methods: {
        
      }
    }
</script>
```
:::


### 自定义上传图片

:::demo
```html
<div>
<o-quill v-model="content3"  :topic-handle="topicHandle" use-custom-image-handler  @image-added="handleImageAdded" ></o-quill>

</div>
<script>
  export default {
      data() {
        return {
          content3: ' 131231',
        };
      },
      methods: {
        topicHandle(data){
          console.log(data)
        },
        handleImageAdded(file, Editor, cursorLocation, resetUploader){
          // An example of using FormData
          // NOTE: Your key could be different such as:
          // formData.append('file', file)

          var formData = new FormData();
          formData.append("upload-file", file);

          axios({
            url: "http://10.0.0.223:8185/ajax/upload/uploadFile",
            method: "POST",
            data: formData
          })
            .then(result => {
              let url = 'http://10.0.0.223:8185' + result.data.info.url; // Get url from response
              Editor.insertEmbed(cursorLocation, "image", url);
              resetUploader();
            })
            .catch(err => {
              console.log(err);
            });
        } 
      }
    }
</script>
```
:::
### 内容长度显示

:::demo
```html
<div>
<o-quill v-model="content3"  :content-limit="500"></o-quill>

</div>
<script>
  export default {
      data() {
        return {
          content3: ' 131231',
        };
      },
      methods: {
        topicHandle(data){
          console.log(data)
        },
        handleImageAdded(file, Editor, cursorLocation, resetUploader){
          // An example of using FormData
          // NOTE: Your key could be different such as:
          // formData.append('file', file)

          var formData = new FormData();
          formData.append("upload-file", file);

          axios({
            url: "http://10.0.0.223:8185/ajax/upload/uploadFile",
            method: "POST",
            data: formData
          })
            .then(result => {
              let url = 'http://10.0.0.223:8185' + result.data.info.url; // Get url from response
              Editor.insertEmbed(cursorLocation, "image", url);
              resetUploader();
            })
            .catch(err => {
              console.log(err);
            });
        } 
      }
    }
</script>
```
:::


### options 参数说明
默认配置
```html
{
theme: 'snow',
    boundary: document.body,
    modules: {
        //工具栏
        toolbar: [
            ['bold', 'italic', 'underline', 'strike'],
            ['blockquote', 'code-block'],
            [{'header': 1}, {'header': 2}],
            [{'list': 'ordered'}, {'list': 'bullet'}],
            [{'script': 'sub'}, {'script': 'super'}],
            [{'indent': '-1'}, {'indent': '+1'}],
            [{'direction': 'rtl'}],
            [{'size': ['small', false, 'large', 'huge']}],
            [{'header': [1, 2, 3, 4, 5, 6, false]}],
            [{'color': []}, {'background': []}],
            [{'font': []}],
            [{'align': []}],
            ['clean'],
            ['link', 'image', 'video']
        ],
        imageDrop: true,
        //图片控制大小
        imageResize: {
            displayStyles: {
                backgroundColor: 'black',
                border: 'none',
                color: 'white'
            },
            modules: [ 'Resize', 'DisplaySize', 'Toolbar' ]
        }
    },
    placeholder: 'Insert text here ...',
    readOnly: false
}
```
```
ImageExtend: {
                             loading: true,  // 可选参数 是否显示上传进度和提示语
                             name: 'img',  // 图片参数名
                             size: 3,  // 可选参数 图片大小，单位为M，1M = 1024kb
                             action: updateUrl,  // 服务器地址, 如果action为空，则采用base64插入图片
                             // response 为一个函数用来获取服务器返回的具体图片地址
                             // 例如服务器返回{code: 200; data:{ url: 'baidu.com'}}
                             // 则 return res.data.url
                             response: (res) => {
                                 return res.info
                             },
                             headers: (xhr) => {},  // 可选参数 设置请求头部
                             sizeError: () => {},  // 图片超过大小的回调
                             start: () => {},  // 可选参数 自定义开始上传触发事件
                             end: () => {},  // 可选参数 自定义上传结束触发的事件，无论成功或者失败
                             error: () => {},  // 可选参数 上传失败触发的事件
                             success: () => {},  // 可选参数  上传成功触发的事件
                             change: (xhr, formData) => {} // 可选参数 选择图片触发，也可用来设置头部，但比headers多了一个参数，可设置formData
                         },
```

# Props
[文档地址](https://www.vue2editor.com)
| Name                  | Type    | Default                                              | Description                                                                            |
| --------------------- | ------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------- |
| id                    | String  | quill-container                                      | Set the id (necessary if multiple editors in the same view)                            |
| v-model               | String  | -                                                    | Set v-model to the the content or data property you wish to bind it to                 |
| use-custom-image-handler | Boolean | false                                                | Handle image uploading instead of using default conversion to Base64                   |
| placeholder           | String  | -                                                    | Placeholder text for the editor                                                        |
| disabled              | Boolean | false                                                | Set to true to disable editor                                                          |
| custom-modules         | Array   | -                                                    | Declare Quill modules to register                                                      | Use a custom toolbar |
| editor-toolbar         | Array   | \*\* _Too long for table. See toolbar example below_ | Use a custom toolbar                                                                   |
| editor-options         | Object  | -                                                    | Offers object for merging into default config (add formats, custom Quill modules, ect) |
| content-limit           | number  | -                                                    | 显示当前文字长度，不包含标签内容，超过显示红色，不禁止输入 |

## Events

| Name             | Parameters                   | Description                                                                         |
| ---------------- | ---------------------------- | ----------------------------------------------------------------------------------- |
| focus            | quill                        | Emitted on `focus` event                                                            |
| blur             | quill                        | Emitted on `blur` event                                                             |
| selection-change | range, oldRange, source      | Emitted on Quill's `selection-change` event                                         |
| text-change      | delta, oldDelta, source      | Emitted on Quill's `text-change` event                                              |
| image-added       | file, Editor, cursorLocation | Emitted when `useCustomImageHandler` is true and photo is being added to the editor |
