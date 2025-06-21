## Markdown 富文本


基础使用。

:::demo
```html
<template>
<div>
  <OMarkdown v-model="markdown" ref="markdown" :options="options"/>
</div>
</template>

<style>
  body {
    margin: 0;
  }
</style>

<script>
  export default {
    data() {
        let self = this
      return {
        markdown:'基础用法',
        options:{
            upload:{
               max: 10 * 1024 * 1024,
               url: 'xxxxxxx',
               token: 'token',
               filename: name => name.replace(/[^(a-zA-Z0-9\u4e00-\u9fa5\.)]/g, '').
                 replace(/[\?\\/:|<>\*\[\]\(\)\$%\{\}@~]/g, '').
                 replace('/\\s/g', ''),
            },
            
            
        }
      };
    },
    mounted(){
       
    }
  };
</script>
```
:::

自定义上传文件。

:::demo
```html
<template>
<div>
  <OMarkdown v-model="markdown" ref="markdown1" :options="options"/>
</div>
</template>

<style>
  body {
    margin: 0;
  }
</style>

<script>
  export default {
    data() {
        let self = this
      return {
        markdown:'自定义上传文件',
        options:{
            customUpload(files,){
                
            },
            upload:{
                customHandler(files,vditor){
                   var xhr = new XMLHttpRequest();
                   xhr.onreadystatechange = function( ) { 
                       if (xhr.readyState === 4) {
                           if (xhr.status === 200) {
                               //自定义处理
                               vditor.insertValue('![templatebanner.png](https://img.hacpai.com/file/2019/09/templatebanner-fd88ba16.png)')
                           }                                   
                       } 
                   };
                    var fd = new FormData();
                               fd.append("file", files[0]);
                   xhr.open('post', 'http://apidebug.devops.onemt.co/docs/file/upload/740ad8da2550a0c01ceec4214e4f8c08',true);            
                   xhr.setRequestHeader('Authorization','jwt eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZGVudGl0eSI6NjQ5LCJpYXQiOjE1Njk0ODc2MjUsIm5iZiI6MTU2OTQ4NzYyNSwiZXhwIjoxNTY5NjYwNDI1fQ.4J8cxTP1yxeNBUIxr2-2Xr3m6xAlscxa1LPbEEr8yVM')
                   xhr.send(fd);
                }
            },
            
            
        }
      };
    },
    mounted(){
       
    }
  };
</script>
```
:::


### Screenshot

![demo](https://user-images.githubusercontent.com/970828/65253329-070fd480-db2d-11e9-896a-807392723485.png)

![render](https://user-images.githubusercontent.com/970828/64341072-30ebd600-d01a-11e9-8e8a-b30c24364b58.png)

## API

### options

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| cache |  是否使用 localStorage 进行缓存 |  true |
| height |  编辑器总高度 |  'auto' |
| width |  编辑器总宽度，支持 % |  'auto' |
| placeholder |  输入区域为空时的提示 |  '' |
| lang |  多语言：en_US, zh_CN |  'zh_CN' |
| counter |  计数器 |  0 |
| input |  输入后触发 (value: string, previewElement?: HTMLElement): void |  - |
| focus |  聚焦后触发 (value: string): void |  - |
| blur |  失焦后触发 (value: string): void |  - |
| esc |  esc 按下后触发 (value: string): void |  - |
| ctrlEnter |  ⌘/ctrl+enter 按下后触发 (value: string): void |  - |
| select |  编辑器中选中文字后触发 (value: string): void |  - |
| tab |  tab 键操作字符串，支持 `\t` 及任意字符串 |  - |

### options.toolbar

* 工具栏，可使用 name 进行简写：`toolbar: ['emoji', 'br', 'bold', '|', 'line']`。默认值参见 [src/ts/util/Options.ts](https://hacpai.com/forward?goto=https%3A%2F%2Fgithub.com%2Fb3log%2Fvditor%2Fblob%2Fmaster%2Fsrc%2Fts%2Futil%2FOptions.ts)
* name 可枚举为：`emoji`, `headings`, `bold`, `italic`, `strike`, `|`, `line`, `quote`, `list`, `ordered-list`, `check`, `code`, `inline-code`, `undo`, `redo`, `upload`, `link`, `table`, `record`, `both`, `preview`, `fullscreen`, `info`, `help`, `br`
* 当 `name` 不在枚举中时，可以添加自定义按钮，格式如下：
  

`{
      hotkey: '⌘-⇧-f',
      name: 'format',
      tipPosition: 'ne',
      tip: 'format',
      icon: '<svg version="1.1" xmlns="http://www.w3.org/2000/svg" width="768" height="768" viewBox="0 0 768 768"><path d="M342 426v-84h426v84h-426zM342 256v-86h426v86h-426zM0 0h768v86h-768v-86zM342 598v-86h426v86h-426zM0 214l170 170-170 170v-340zM0 768v-86h768v86h-768z"></path></svg>',
      click: () => {
          alert('custom toolbar')
      },
}` 

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| name |  唯一标示 |  - |
| icon |  svg 图标 |  - |
| tip |  提示 |  - |
| tipPosition |  提示位置：ne, nw |  - |
| hotkey |  快捷键，支持 ⌘/ctrl-key 或 ⌘/ctrl-⇧/shif-key 格式的配置 |  - |
| suffix |  插入编辑器中的后缀 |  - |
| prefix |  插入编辑器中的前缀 |  - |
| click |  自定义按钮点击时触发的事件 ():viod |  - |

### options.preview

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| delay |  预览 debounce 毫秒间隔 |  1000 |
| mode |  显示模式：'both', 'editor', 'preview' |  'both' |
| parse |  预览回调 (element: HTMLElement): void |  - |
| url |  md 解析请求 |  - |

### options.preview.hljs

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| enable |  是否启用代码高亮 |  true |
| style |  可选值参见 [Chroma](https://hacpai.com/forward?goto=https%3A%2F%2Fxyproto.github.io%2Fsplash%2Fdocs%2Flonger%2Fall.html) |  'github' |

### options.hint

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| delay |  提示 debounce 毫秒间隔 |  200 |
| emoji |  默认表情，可从 [lute/emoji_map](https://hacpai.com/forward?goto=https%3A%2F%2Fgithub.com%2Fb3log%2Flute%2Fblob%2Fmaster%2Femoji_map.go) 中选取，也可自定义 |  { '+1': '👍', '-1': '👎', 'heart': '❤️', 'cold_sweat': '😰' } |
| emojiTail |  常用表情提示 |  - |
| emojiPath |  表情图片地址 |  [https://cdn.jsdelivr.net/npm/vditor/src/assets/emoji](https://hacpai.com/forward?goto=https%3A%2F%2Fcdn.jsdelivr.net%2Fnpm%2Fvditor%2Fsrc%2Fassets%2Femoji) |
| at |  @用户回调，(value: string): Array，需同步返回数组[{value: '', html: ''}] |  - |

### options.upload

* ⚠️ filename 需和 `options.uploads.filename` 保持一致，否则将导致[编辑器中出现多个链接](https://hacpai.com/article/1549638745630/comment/1566355551698?r=Vanessa)
* 后端返回的数据结构不一致时，可使用 `format` 进行转换。文件上传的数据结构如下：

// POST data
xhr.send(formData);  // formData = FormData.append("file[]", File)
// return data
{
    "msg": "",
    "code": 0,
    "data": {
        "errFiles": ['filename', 'filename2'],
        "succMap": {
            "filename3": "filepath3",
            "filename3": "filepath3"
        }
    }
}
  

`// POST data xhr.send(formData);  // formData = FormData.append("file[]", File) // return data {
    "msg": "",
    "code": 0,
    "data": {
        "errFiles": ['filename', 'filename2'],
        "succMap": {
            "filename3": "filepath3",
            "filename3": "filepath3"
        }
    }
}` 

* 为了防止站外图片失效，`linkToImgUrl` 可将剪贴板中的站外图片地址传到服务器端进行保存处理，其数据结构如下：

// POST data
xhr.send(JSON.stringify({url: src})); // src 为站外图片地址
// return data
{
    msg: '',
    code: 0,
    data : {
        originalURL: '',
        url: ''
    }
}
  

`// POST data xhr.send(JSON.stringify({url: src})); // src 为站外图片地址 // return data {
    msg: '',
    code: 0,
    data : {
        originalURL: '',
        url: ''
    }
}` 

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| url |  上传 url，查看[规范](https://hacpai.com/forward?goto=https%3A%2F%2Fgithub.com%2Fb3log%2Fvditor%2Fissues%2F2) |  '' |
| max |  上传文件最大 Byte |  10 * 1024 * 1024 |
| linkToImgUrl |  剪切板中包含图片地址时，使用此 url 重新上传 |  '' |
| success |  上传成功回调 (editor: HTMLPreElement, msg: string): void |  - |
| error |  上传失败回调 (msg: string): void |  - |
| token |  CORS 上传验证，头为 X-Upload-Token |  - |
| filename |  文件名安全处理 (name: string): string |  name => name.replace(/\W/g, '') |
| accept |  文件上传类型，同 [input accept](https://hacpai.com/forward?goto=https%3A%2F%2Fwww.w3schools.com%2Ftags%2Fatt_input_accept.asp) |  - |
| validate |  校验，成功时返回 true 否则返回错误信息 (files: File[]) => string | boolean |  - |
| handler |  自定义上传，当发生错误时返回错误信息 (files: File[]) => string | null |  - |
| format |  对服务端返回的数据进行转换，以满足内置的数据结构 (files: File[], responseText: string): string |  - |

### options.resize

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| enable |  是否支持大小拖拽 |  false |
| position |  拖拽栏位置：top, bottom |  'bottom' |
| after |  拖拽结束的回调 (height: number): void |  - |

### options.classes

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| preview |  预览元素上的 className |  '' |

### options.hotkey

|  |  说明 |  默认值 |
| --- |  --- |  --- |
| deleteLine |  删除光标所在行或选中的行 |  ⌘-Backspace |
| duplicate |  复制当前行或选中的内容 |  ⌘-d |

### methods

|  |  说明 |
| --- |  --- |
| getValue() |  获取编辑器内容 |
| getHTML() |  获取预览区内容。该方法需使用[异步编程](https://hacpai.com/article/1546828434083?r=Vanessa#toc_h3_1) |
| insertValue(value: string) |  在焦点处插入内容 |
| focus() |  聚焦到编辑器 |
| blur() |  让编辑器失焦 |
| disabled() |  禁用编辑器 |
| enable() |  解除编辑器禁用 |
| setSelection(start: number, end: number) |  选中从 start 开始到 end 结束的字符串 |
| getSelection():string |  返回选中的字符串 |
| setValue(value: string) |  设置编辑器内容 |
| renderPreview(value?: string) |  设置预览区域内容 |
| getCursorPosition():{top: number, left: number} |  获取焦点位置 |
| deleteValue() |  删除选中内容 |
| updateValue(value: string) |  更新选中内容 |
| isUploading() |  上传是否还在进行中 |
| clearCache() |  清除缓存 |
| disabledCache() |  禁用缓存 |
| enableCache() |  启用缓存 |
| html2md(value: string) |  HTML 转 md。该方法需使用[异步编程](https://hacpai.com/article/1546828434083?r=Vanessa#toc_h3_1) |
| tip(text:string, time:number) |  消息提示。time 为 0 将一直显示 |
| setPreviewMode(mode: string) |  设置预览模式。mode: 'both', 'editor', 'preview' |

### static methods

* 不需要进行编辑操作时，仅需引入 [`method.min.js`](https://hacpai.com/forward?goto=https%3A%2F%2Fcdn.jsdelivr.net%2Fnpm%2Fvditor%2Fdist%2F) 后如下直接调用

Vditor.mermaidRender(document)
  

`Vditor.mermaidRender(document)` 

import VditorPreview from 'vditor/dist/method.min'
VditorPreview.mermaidRender(document)
  

`import VditorPreview from 'vditor/dist/method.min'
VditorPreview.mermaidRender(document)` 

* 需要对页面中的 Markdown 进行渲染时可直接调用 `preview` 方法，参数如下：

element: HTMLTextAreaElement    // 为保证 Markdown 的完整性，请将其包裹在 textarea 或 pre 中
options?: IPreviewOptions {
    hljsStyle?: string;    // 高亮样式，默认为 'atom-one-light'
    enableHighlight?: boolean;    // 是否需要代码高亮，默认为 true
    customEmoji?: { [key: string]: string };    // 自定义 emoji，默认为 {}
    lang?: (keyof II18nLang);    // 语言，默认为 'zh_CN'
    emojiPath?: string;    // 表情图片路径
}
  

`element: HTMLTextAreaElement    // 为保证 Markdown 的完整性，请将其包裹在 textarea 或 pre 中 options?: IPreviewOptions {
    hljsStyle?: string;    // 高亮样式，默认为 'atom-one-light'     enableHighlight?: boolean;    // 是否需要代码高亮，默认为 true     customEmoji?: { [key: string]: string };    // 自定义 emoji，默认为 {}     lang?: (keyof II18nLang);    // 语言，默认为 'zh_CN'     emojiPath?: string;    // 表情图片路径 }` 

* ⚠️`method.min.js` 和 `index.min.js` 不可同时引入

|  |  说明 |
| --- |  --- |
| mathRender(element: HTMLElement) |  转换 element 中的文本为数学公式 |
| mermaidRender(element: HTMLElement) |  转换 element 中的文本为流程图/时序图/甘特图 |
| codeRender(element: HTMLElement, lang: (keyof II18nLang) = "zh_CN") |  为 element 中的代码块添加复制按钮 |
| chartRender(element: (HTMLElement | Document) = document) |  图表渲染 |
| abcRender(element: (HTMLElement | Document) = document) |  五线谱渲染 |
| md2html(mdText: string, options?: IPreviewOptions): string |  Markdown 文本转换为 HTML，该方法需使用[异步编程](https://hacpai.com/article/1546828434083?r=Vanessa#toc_h3_1) |
| preview(element: HTMLTextAreaElement, options?: IPreviewOptions) |  页面 Markdown 文章渲染 |
| highlightRender(hljsStyle: string, enableHighlight: boolean, element?: HTMLElement | Document) |  为 element 中的代码块进行高亮渲染 |
| mediaRender(element: HTMLElement) |  为[特定链接](https://hacpai.com/forward?goto=https%3A%2F%2Fgithub.com%2Fb3log%2Fvditor%2Fissues%2F117)分别渲染为视频、音频、嵌入的 iframe |
| mathRenderByLute(element: HTMLElement) |  对使用 Lute 渲染的数学公式进行渲染 |

### CSS

在 DOM 元素上添加 `class="vditor-reset"` 属性可对内容进行更为友好的展示。

