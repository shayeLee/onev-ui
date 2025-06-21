## Youtube播放器

Youtube播放器

### 基本用法


:::demo 
```html
<template>
  <o-youtube-player :id="id"></o-youtube-player>
</template>
<script>
export default {
    data(){
        return {
            id:'M7lc1UVf-VE'
        }       
    }
}
</script>
```
:::

### Attributes
| 参数      | 说明          | 类型      | 可选值                           | 默认值  |
|---------- |-------------- |---------- |--------------------------------  |-------- |
| id     | youtube视频id           | string | — | M7lc1UVf-VE |
| width     | 播放器宽度           | number | — | 640 |
| height     | 播放器宽度           | number | — | 360 |
| playerVars     | 播放器参数           | object | [参照](https://developers.google.com/youtube/player_parameters?hl=zh-cn#Parameters) | {rel:0} |

### Events
| 事件名称      | 说明    | 回调参数      |
|---------|--------|---------|
| ready | 该函数指示当视频播放器就绪时就应开始播放 | event |
| state-change | 指示播放器正在播放、已暂停、已完成等等 | event |
