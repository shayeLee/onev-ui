## 结果弹窗

:::demo 
```html
<div>
  <el-button type="primary" @click="visible = true">打开弹窗</el-button>
  <o-window :visible.sync="visible" title="测试窗口1" :width="460" class="gm-result-window">
    窗口内容填充
    <br>
    窗口内容填充
        <br>
        窗口内容填充
            <br>
            窗口内容填充
                <br>
                窗口内容填充
                    <br>
                    窗口内容填充
                        <br>
                        窗口内容填充
                            <br>
    <div slot="footer" class="gm-result-window__footer">
        <el-button size="small" type="primary" @click="visible = false">确定</el-button>
    </div>
  </o-window>
</div>
<script>
  export default {
    data() {
      return {
        visible: false
      }
    }
  }
</script>
```
:::