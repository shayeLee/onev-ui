## GM 表单规范说明

GM 后台表单基于 window 组件的规范要求
:::demo

```html
<el-row>
  <div class="gallery-demo">
    <el-button @click="visible=!visible">
      开关弹窗1
    </el-button>
  </div>
  <o-window
    :height="800"
    :visible.sync="visible"
    :pending.sync="loading"
    title="活动配置"
    class="gm-form"
  >
    <el-form ref="form" :model="form" label-width="80px" size="small">
      <el-form-item label="活动名称">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="开始时间">
        <el-date-picker
          type="datetime"
          placeholder="选择日期"
          v-model="form.date1"
        ></el-date-picker>
      </el-form-item>
      <el-form-item label="单选控件">
        <o-multiselect
          v-model="form.region"
          :data="options"
          size="small"
        ></o-multiselect>
      </el-form-item>

      <el-form-item label="即时配送">
        <el-switch v-model="form.delivery"></el-switch>
      </el-form-item>
      <el-form-item label="王国列表">
        <el-button type="primary">主要按钮</el-button>
        <el-button type="success">成功按钮</el-button>
        <el-button type="info">信息按钮</el-button>
        <el-button type="warning">警告按钮</el-button>
        <el-button type="danger">危险按钮</el-button>
        <el-button>默认按钮</el-button>
      </el-form-item>
      <el-form-item label="选择王国">
        <o-multiselect
          v-model="form.value"
          multiple
          enable-interval-filter
          placeholder="请选择王国"
          :data="options"
          select-type="king"
        ></o-multiselect>
      </el-form-item>
      <el-form-item label="活动时间">
        <el-date-picker
          v-model="form.date_range"
          type="datetimerange"
          range-separator="至"
          start-placeholder="开始日期"
          end-placeholder="结束日期"
        >
        </el-date-picker>
      </el-form-item>
      <el-form-item label="活动性质">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="美食/餐厅线上活动" name="type"></el-checkbox>
          <el-checkbox label="地推活动" name="type"></el-checkbox>
          <el-checkbox label="线下主题活动" name="type"></el-checkbox>
          <el-checkbox label="单纯品牌曝光" name="type"></el-checkbox>
        </el-checkbox-group>
      </el-form-item>
      <el-form-item label="特殊资源">
        <el-radio-group v-model="form.resource">
          <el-radio label="线上品牌商赞助"></el-radio>
          <el-radio label="线下场地免费"></el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="活动形式">
        <el-input type="textarea" v-model="form.desc"></el-input>
      </el-form-item>
    </el-form>
    <div slot="footer">
      <el-button size="small" type="primary" @click="submit">确定</el-button>
      <el-button size="mini" class="mr-md">取消</el-button>
    </div>
  </o-window>
</el-row>
<script>
  export default {
    data() {
      return {
        visible: false,
        loading: false,
        form: {
          name: "",
          region: "",
          date1: "",
          date2: "",
          delivery: false,
          type: [],
          resource: "",
          desc: "",
          date_range: [],
          value: [2, 3],
          options: [],
        },
        options: [],
      };
    },
    methods: {
      submit() {
        this.loading = true;
        setTimeout(() => {
          // 定时器模拟异步接口请求
          this.loading = false;
        }, 2000);
      },
    },
    computed: {},
    mounted() {
      const options = [];
      for (let i = 1; i < 101; i++) {
        const disabled = i === 1 ? true : false;
        options.push({
          label: `王国${i}`,
          value: `${i}`,
          selected: false,
          disabled,
        });
      }
      this.options = options;
    },
  };
</script>
```

:::

表单规范说明--统一使用 window 窗口组件，在组件上加入 class="gm-form" 即可达到规范。<br>
<strong>头部</strong>：<br> 1.标题字体大小 18 号；<br> 2.标题高度 45px；<br>
<strong>内容</strong>：<br> 1.距离顶部高度、底部高度 40px,距离左右高度 45px；<br> 2.按钮大小均使用 small,按钮采用朴素按钮样式；<br> 3.上下字段间隔 20px，每个字段选择输入框为 217px；<br>
<strong>底部</strong>：<br> 1.按钮大小默认为 small，按钮样式按默认样式，且固定在右边；<br>
<strong>Loading</strong>：<br> 1.给`window`组件传递`pending`属性即可，为`true`时，`window`组件会进入 loading 状态，这个状态下所有的表单和按钮都无法操作，并且窗口无法被关闭
