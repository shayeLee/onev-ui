## Audio

用于丰富页面多媒体。

### 基本用法


:::demo 

```html
<template>
        <div class="box">
          <o-audio format="amr" src="https://voice-chat.s3.eu-central-1.amazonaws.com/10000060115729469850507801848"></o-audio>
        </div>
</template>
<script>
        export default {
         data(){
             return {
                
             }
         },
         computed:{
             
         },
         methods: {
              onplaying(){
                   alert('开始播放')  
            }   
         },
         mounted(){
        
         }
        }
</script>
```
:::

### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| autoplay | 指定后，音频会马上自动开始播放，不会停下来等着数据载入结束。 | boolean | — | false |
|  buffered(readonly) | 你可以通过该属性获取已缓冲的资源的时间段信息。该属性包含一个 TimeRanges 对象。 | boolean | — | false |
|  controls | 如果设置了该属性，浏览器将提供一个包含声音，播放进度，播放暂停的控制面板，让用户可以控制音频的播放。 | boolean | — | true |
|  loop | 如果指定，将循环播放音频。 | boolean | — | false |
|  muted | 表示是否静音 | boolean | — | false |
|  src | 嵌入的音频的URL | string | — | - |
|  volume | 音频播放的音量 值从0.0 (无声) 到 1.0 (最大声). | number | — | 1 |
|  format | 文件格式 | string \| normal | 1 |

[属性参考](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio#%E5%B1%9E%E6%80%A7)

### event
[事件参考](https://developer.mozilla.org/zh-CN/docs/Web/Guide/Events/Media_events)
