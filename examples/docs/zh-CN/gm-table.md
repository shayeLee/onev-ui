## GM 内容页展示规范说明

:::demo

```html
<div class="gm-table" style="width: 820px;">
  <div class="gm-table-box ">
    <el-form
      :model="ruleForm"
      ref="ruleForm"
      :inline="true"
      inline
      class="demo-ruleForm"
    >
      <el-form-item label="请输入名字">
        <el-input
          v-model="ruleForm['name']"
          size="small"
          style="width: 200px"
        ></el-input>
      </el-form-item>

      <el-form-item label="单选框控件">
        <o-multiselect
          v-model="ruleForm['member1']"
          :data="options"
        ></o-multiselect>
      </el-form-item>
      <el-form-item label="多选框控件">
        <o-multiselect
          multiple
          v-model="ruleForm['member2']"
          :data="options"
        ></o-multiselect>
      </el-form-item>
      <el-form-item label="王国控件">
        <o-multiselect
          v-model="ruleForm['member3']"
          multiple
          enable-interval-filter
          placeholder="请选择王国"
          :data="options"
          select-type="king"
        ></o-multiselect>
      </el-form-item>

      <el-form-item label="请选择时间">
        <el-date-picker
          size="small"
          v-model="ruleForm['startTime']"
          type="datetime"
          value-format="yyyy-MM-dd HH:mm:ss"
          placeholder="选择日期时间"
          align="right"
          :picker-options="pickerOptions"
        >
        </el-date-picker>
        -
        <el-date-picker
          size="small"
          v-model="ruleForm['endTime']"
          type="datetime"
          value-format="yyyy-MM-dd HH:mm:ss"
          placeholder="选择日期时间"
          align="right"
          :picker-options="pickerOptions"
        >
        </el-date-picker>
      </el-form-item>

      <el-form-item>
        <el-button type="primary" size="small" @click="getData">查询</el-button>
        <el-button type="primary" size="small" @click="getDataOld"
          >老页面查询</el-button
        >
      </el-form-item>
    </el-form>
  </div>
  <div class="gm-table-remarks">
    备注：礼包数据每12小时进行缓存更新，如果出现查询不到最新数据的情况，可点击右上角【个人信息】下的【配置获取刷新】获取最新数据
  </div>

  <el-table
    id="table"
    v-loading="loading"
    border
    stripe
    :data="tableData"
    show-sticker
    wrapper-move
    sticker-wrapper="body"
    class="o-gm-table"
  >
    <div class="gm-table-box" slot="sticker-header">
      <el-form
        :model="ruleForm"
        ref="ruleForm"
        :inline="true"
        inline
        class="demo-ruleForm"
      >
        <el-form-item label="请输入名字">
          <el-input
            v-model="ruleForm['name']"
            size="small"
            style="width: 200px"
          ></el-input>
        </el-form-item>

        <el-form-item label="单选框控件">
          <o-multiselect
            v-model="ruleForm['member1']"
            :data="options"
          ></o-multiselect>
        </el-form-item>
        <el-form-item label="多选框控件">
          <o-multiselect
            multiple
            v-model="ruleForm['member2']"
            :data="options"
          ></o-multiselect>
        </el-form-item>
        <el-form-item label="王国控件">
          <o-multiselect
            v-model="ruleForm['member3']"
            multiple
            enable-interval-filter
            placeholder="请选择王国"
            :data="options"
            select-type="king"
          ></o-multiselect>
        </el-form-item>

        <el-form-item label="请选择时间">
          <el-date-picker
            size="small"
            v-model="ruleForm['startTime']"
            type="datetime"
            value-format="yyyy-MM-dd HH:mm:ss"
            placeholder="选择日期时间"
            align="right"
            :picker-options="pickerOptions"
          >
          </el-date-picker>
          -
          <el-date-picker
            size="small"
            v-model="ruleForm['endTime']"
            type="datetime"
            value-format="yyyy-MM-dd HH:mm:ss"
            placeholder="选择日期时间"
            align="right"
            :picker-options="pickerOptions"
          >
          </el-date-picker>
        </el-form-item>

        <el-form-item>
          <el-button type="primary" size="small">查询</el-button>
          <el-button type="primary" size="small">重置</el-button>
          <el-button type="primary" size="small">新增模板</el-button>
          <el-button type="primary" size="small">删除</el-button>
        </el-form-item>
      </el-form>
    </div>
    <el-table-column width="120" prop="date" sortable label="日期">
    </el-table-column>
    <el-table-column prop="name" sortable label="姓名"> </el-table-column>
    <el-table-column width="200" prop="address" sortable label="详细地址">
    </el-table-column>
    <el-table-column width="200" prop="address" sortable label="详细地址">
    </el-table-column>
    <el-table-column width="200" prop="address" sortable label="详细地址">
    </el-table-column>
    <el-table-column width="200" prop="address" sortable label="详细地址">
    </el-table-column>
    <el-table-column width="200" prop="address" sortable label="详细地址">
    </el-table-column>
    <el-table-column
      fixed="right"
      width="200"
      label="操作"
      align="center"
      sortable
    >
      <template slot-scope="scope">
        <div>
          <el-button plain type="primary" size="small">查看</el-button>
          <el-button plain type="primary" size="small">操作</el-button>
        </div>
      </template>
    </el-table-column>
  </el-table>
  <div class="gm-table-pagination">
    <el-pagination
      :current-page="currentPage4"
      :page-sizes="[20, 50, 100, 200]"
      :page-size="20"
      layout="total, sizes, prev, pager, next, jumper"
      :total="400"
      @size-change="handleSizeChange"
      @current-change="handleCurrentChange"
    >
    </el-pagination>
  </div>
</div>
<script>
  const $ = require("jquery");

  export default {
    data() {
      return {
        visible: false,
        loading: false,
        ruleForm: {
          name: "",
          endTime: "",
          startTime: "",
          member1: "",
          member2: "",
          member3: "",
        },
        pickerOptions: {
          shortcuts: [
            {
              text: "今天",
              onClick(picker) {
                picker.$emit("pick", new Date());
              },
            },
            {
              text: "昨天",
              onClick(picker) {
                const date = new Date();
                date.setTime(date.getTime() - 3600 * 1000 * 24);
                picker.$emit("pick", date);
              },
            },
            {
              text: "一星期前",
              onClick(picker) {
                const date = new Date();
                date.setTime(date.getTime() - 3600 * 1000 * 24 * 7);
                picker.$emit("pick", date);
              },
            },
          ],
        },
        tableData: [],
        currentPage4: 1,
        options: [],
      };
    },
    methods: {
      getData() {
        this.loading = true;
        setTimeout(() => {
          // 用定时器回调来模拟异步接口请求
          this.loading = false;
        }, 3000);
      },
      getDataOld() {
        const targetElm = $("#table");
        const loadingHTML = `<div class="om-loading-mask">
          <div class="el-loading-spinner">
            <svg class="circular" viewBox="25 25 50 50">
              <circle class="path" cx="50" cy="50" r="20" fill="none" />
            </svg>
          </div>
        </div>`;
        targetElm.append(loadingHTML);
        setTimeout(() => {
          // 用定时器回调来模拟异步接口请求
          $(".om-loading-mask").remove();
        }, 3000);
      },
      handleSizeChange(size) {
        this.getData()
      },  
      handleCurrentChange(page) {
        this.getData()
      }  
    },
    computed: {},
    mounted() {
      for (let i = 0; i < 16; i++) {
        this.options.push({
          label: `option 3`,
          value: `3`,
          selected: false,
          disabled: false,
        });
        this.tableData.push({
          date: "2016-05-02",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄",
          phone: "1520501452222",
          email: "845623555@qq.com",
        });
      }
    },
  };
</script>
```

:::

内容页规范说明--统一在最外成加入 **class="gm-table"** 即可达到规范。<br>

## css 规范（不需要手动设置）

<strong>头部</strong>：<br> 1.默认边距 20px；<br> 3.头部距离 table20px,当有备注时，备注高度 35px<br>
<strong>内容</strong>：<br> 1.表格行高 45px,表头底色#f5f5f5,线宽颜色#f2f2f2；<br> 2.单元格内容居中，宽度自适应;<br>
<strong>底部翻页</strong>：<br> 1.页码默认内容页居中,默认展示 20 条,选择项：{20；50；100；200}；

## 属性规范（需要手动设置）：

1.头部按钮使用默认按钮样式，使用 small 样式；<br> 2.表格内的按钮使用朴素（plain）按钮；<br>

## 添加粘性头部（需要手动设置）：

1.复制&lt;el-form&gt;内所有的内容至&lt;el-table&gt;中;<br> 2.在&lt;el-table&gt;中添加以下两个属性：<br>
show-sticker(是否显示粘性头部)<br>
sticker-wrapper="body"( 粘性元素的滚动父级，也可为类名例如：.gm-table)<br> 3.最后添加 &lt;div slot="sticker-header"&gt;&lt;/div&gt;至&lt;el-table&gt;结尾处<br>

## Loading

任何会更改表格数据的操作过程中，都需要展示 loading
