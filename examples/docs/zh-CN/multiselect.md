## Multiselect 多选选择器

### 基础用法一（单选）

:::demo

```html

<div>
    <o-multiselect
            v-model="value"
            :data="options"
            hide-number-search-switch
            @change="handleChange"
    ></o-multiselect>
    <el-button size="small" @click="clear">清除选项</el-button>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [
                    {
                        label: `option 1`,
                        value: `1`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: `2`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: `3`,
                        selected: false,
                        disabled: true,
                    },
                ],
            };
        },
        methods: {
            handleChange(val) {
                // console.log(">>>>>>>>>>>>>>>>>>>>>", val);
            },
            clear() {
                this.value = 0;
            },
        },
    };
</script>
```

:::

### 基础用法二（多选）

:::demo

```html

<div>
    <o-multiselect multiple show-limit="10" v-model="value" :data="options"></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [{"value":74,"label":"平圣姬"},{"value":76,"label":"罗芳"},{"value":81,"label":"杨淦"},{"value":82,"label":"何方静"},{"value":83,"label":"邹丽云"},{"value":86,"label":"游振军"},{"value":88,"label":"房秋红"},{"value":99,"label":"孟会顶"},{"value":101,"label":"周婧"},{"value":108,"label":"陈朝用"},{"value":110,"label":"张小凤"},{"value":112,"label":"汤清"},{"value":113,"label":"裴甜"},{"value":114,"label":"李豆"},{"value":118,"label":"Thomas Malone"},{"value":119,"label":"常峰"},{"value":123,"label":"许倩1"},{"value":140,"label":"林子成"},{"value":144,"label":"谭雪岭"},{"value":145,"label":"任小刚"},{"value":146,"label":"陈锐锐"},{"value":149,"label":"洪书秀"},{"value":152,"label":"李晨翔"},{"value":154,"label":"赖龙威"},{"value":158,"label":"林鸿飞"},{"value":159,"label":"马艾敏"},{"value":161,"label":"郑成"},{"value":162,"label":"林航"},{"value":164,"label":"林湘耀"},{"value":168,"label":"高倩倩"},{"value":169,"label":"殷春桃"},{"value":174,"label":"余娇"},{"value":175,"label":"涂夏辉"},{"value":179,"label":"黄辉"},{"value":182,"label":"梁瑞福"},{"value":188,"label":"郑伟"},{"value":190,"label":"林辉"},{"value":191,"label":"陈慧琴"},{"value":195,"label":"刘神利"},{"value":196,"label":"李杰"},{"value":197,"label":"毛灵灵"},{"value":198,"label":"林超然"},{"value":199,"label":"林绍东"},{"value":204,"label":"郑黉宾"},{"value":300,"label":"系统"},{"value":301,"label":"叶潇凯"},{"value":305,"label":"杨柳清"},{"value":306,"label":"向玥"},{"value":314,"label":"王松根"},{"value":315,"label":"杨淦"},{"value":316,"label":"李强强"},{"value":320,"label":"谢子钰"},{"value":323,"label":"章志伟"},{"value":324,"label":"林金聪"},{"value":325,"label":"何奇恩"},{"value":326,"label":"郑智洲"},{"value":327,"label":"邓铃烽"},{"value":330,"label":"杨军"},{"value":331,"label":"张铭捷"},{"value":335,"label":"陈林儿"},{"value":336,"label":"陈宸"},{"value":339,"label":"庄子南"},{"value":341,"label":"连钰雯"},{"value":342,"label":"李清"},{"value":343,"label":"李莹"},{"value":345,"label":"吴贤青"},{"value":353,"label":"林娟"},{"value":357,"label":"林毅"},{"value":360,"label":"郑宏伟"},{"value":363,"label":"钟媛琳"},{"value":364,"label":"吴晓燕"},{"value":365,"label":"牛文庆"},{"value":368,"label":"陈祥"},{"value":369,"label":"胡可超"},{"value":370,"label":"苏晓斌"},{"value":371,"label":"杜德华"},{"value":372,"label":"王芳芳"},{"value":374,"label":"陈雄"},{"value":375,"label":"尧舜哲"},{"value":377,"label":"翁文辉"},{"value":378,"label":"张丽"},{"value":379,"label":"黄文平"},{"value":381,"label":"陈熙"},{"value":383,"label":"刘用锵"},{"value":384,"label":"史梦雪"},{"value":387,"label":"倪萍倩"},{"value":388,"label":"彭丽"},{"value":389,"label":"陈旭东"},{"value":393,"label":"杨淑敏"},{"value":395,"label":"施嘉华"},{"value":396,"label":"苏辉清"},{"value":398,"label":"张晨君"},{"value":401,"label":"范志凯"},{"value":402,"label":"张强斌"},{"value":403,"label":"何雨漩"},{"value":404,"label":"林同辉"},{"value":406,"label":"刘鑫怡"},{"value":407,"label":"林宇"},{"value":409,"label":"刘百花"},{"value":411,"label":"郑新丽"},{"value":413,"label":"许海防"},{"value":414,"label":"黄汉臣"},{"value":416,"label":"林登健"},{"value":417,"label":"林永洪"},{"value":419,"label":"陈以鸿"},{"value":420,"label":"王士丹"},{"value":423,"label":"郑舒颖"},{"value":424,"label":"郑贵亮"},{"value":425,"label":"李凯鑫"},{"value":428,"label":"余斌"},{"value":429,"label":"何铃平"},{"value":430,"label":"范文文"},{"value":431,"label":"张金秀"},{"value":433,"label":"蒋华亮"},{"value":439,"label":"陈立坚"},{"value":440,"label":"李享悦"},{"value":442,"label":"包思霞"},{"value":448,"label":"林辉河"},{"value":454,"label":"刘玉鹏"},{"value":456,"label":"林学威"},{"value":461,"label":"许民"},{"value":462,"label":"胡可成"},{"value":463,"label":"陈胡斌"},{"value":464,"label":"曾意馨"},{"value":472,"label":"韦春慧"},{"value":475,"label":"戴群权"},{"value":801,"label":"黄萃"},{"value":802,"label":"李光源"},{"value":803,"label":"连亦芳"},{"value":804,"label":"陈靖航"},{"value":805,"label":"林天枢"},{"value":806,"label":"陈晓萱"},{"value":808,"label":"冯双来"},{"value":809,"label":"陈林"},{"value":810,"label":"高澄清"},{"value":811,"label":"杨晓燕"},{"value":812,"label":"张榕"},{"value":815,"label":"陈聃聃"},{"value":817,"label":"刘孟颖"},{"value":818,"label":"侯鸣宇"},{"value":819,"label":"马孝"},{"value":821,"label":"黄鑫"},{"value":823,"label":"叶金荣"},{"value":825,"label":"张帆"},{"value":826,"label":"陈静康"},{"value":827,"label":"董浩"},{"value":829,"label":"阙鹏强"},{"value":830,"label":"陈振枝"},{"value":832,"label":"陈思远"},{"value":833,"label":"张孝榕"},{"value":834,"label":"黄道钧"},{"value":835,"label":"买豪森"},{"value":836,"label":"张巧逢"},{"value":837,"label":"赖燊灿"},{"value":838,"label":"上官源森"},{"value":839,"label":"王志敏"},{"value":841,"label":"林擎"},{"value":842,"label":"郑昆彬"},{"value":844,"label":"刘佳"},{"value":845,"label":"叶孝廷"},{"value":847,"label":"薛磊"},{"value":848,"label":"张延秀"},{"value":852,"label":"赵晨颖"},{"value":853,"label":"陈秦禾"},{"value":855,"label":"陈佳明"},{"value":856,"label":"谢世雄"},{"value":857,"label":"赵鑫"},{"value":858,"label":"施余颖"},{"value":859,"label":"吴贞龙"},{"value":860,"label":"阮禾"},{"value":861,"label":"向绪慧"},{"value":866,"label":"顾君成"},{"value":869,"label":"刘涵昕"},{"value":872,"label":"张凯荣"},{"value":876,"label":"林秋婷"},{"value":885,"label":"刘佳慧"},{"value":886,"label":"林哲隆"},{"value":888,"label":"陈雨婷"},{"value":900,"label":"徐传建"},{"value":906,"label":"周峻"},{"value":916,"label":"李梓涵"},{"value":917,"label":"金镂石"},{"value":918,"label":"张鑫"},{"value":919,"label":"连淼"},{"value":920,"label":"杨涛"},{"value":921,"label":"余小芬"},{"value":922,"label":"乔彤"},{"value":923,"label":"韩其委"},{"value":924,"label":"黄淦"},{"value":925,"label":"林语佳"},{"value":926,"label":"肖进衍"},{"value":927,"label":"杜静雅"},{"value":928,"label":"阮晓雯"},{"value":929,"label":"郑舒颖"},{"value":930,"label":"gmtest"},{"value":931,"label":"张旭"},{"value":932,"label":"李娇娇"},{"value":933,"label":"李金华"},{"value":934,"label":"石晋阳"},{"value":935,"label":"高艺斌"},{"value":936,"label":"郑雪梅"},{"value":937,"label":"张少聪"},{"value":938,"label":"NOURELDEN SALEH ALI HAMOUDA"},{"value":939,"label":"丁汉辰"},{"value":940,"label":"李泽"},{"value":941,"label":"刘思忆"},{"value":942,"label":"姚志伟"},{"value":943,"label":"施烨子"},{"value":944,"label":"陈南杰"},{"value":945,"label":"李林峰"},{"value":946,"label":"刘金桥"},{"value":947,"label":"SERAG MANSOOR ABDULRAHMAN ALI"},{"value":948,"label":"张法权"},{"value":949,"label":"李虎"},{"value":950,"label":"王荣贵"},{"value":951,"label":"马魁宇"},{"value":952,"label":"刘星宇"},{"value":953,"label":"马胜南"},{"value":954,"label":"张琦"},{"value":955,"label":"曹晨景"},{"value":956,"label":"杨天翱"},{"value":957,"label":"赵启鹏"},{"value":958,"label":"徐玉京"},{"value":959,"label":"杨博宁"},{"value":960,"label":"施江麟"},{"value":961,"label":"王宏远"},{"value":962,"label":"吴雪冬"},{"value":963,"label":"郑一凡"},{"value":964,"label":"闫鹏"},{"value":965,"label":"qatest"},{"value":966,"label":"陈希"},{"value":967,"label":"gmtest"},{"value":968,"label":"陈清婷"},{"value":969,"label":"仵凡"},{"value":970,"label":"杨金火"},{"value":971,"label":"吴学强"},{"value":972,"label":"陈狄"},{"value":973,"label":"衣凯新"},{"value":974,"label":"李迎锋"},{"value":975,"label":"黄修灵"},{"value":976,"label":"高小迪"},{"value":977,"label":"李虎生"},{"value":978,"label":"何山伟"},{"value":979,"label":"沐帆"},{"value":980,"label":"杨鑫"},{"value":981,"label":"庄玉敏"},{"value":982,"label":"李家成"},{"value":983,"label":"肖岚"},{"value":984,"label":"赵康弟"},{"value":985,"label":"陈荣辉"},{"value":986,"label":"冯桂芝"},{"value":987,"label":"王姗"},{"value":988,"label":"郭茂宗"},{"value":989,"label":"赵长淳"},{"value":990,"label":"张小煊"},{"value":991,"label":"周胜硕"},{"value":992,"label":"王欣然"},{"value":993,"label":"林宝强"},{"value":994,"label":"万昱辰"},{"value":995,"label":"李鋆洳"},{"value":996,"label":"陈燕蓉"},{"value":997,"label":"吴岚春"}],
            };
        },
    };
</script>
```

:::
### 选择数量限制

:::demo

```html

<div>
    <o-multiselect multiple :select-limit="3" v-model="value" :data="options"></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [{"value":74,"label":"平圣姬"},{"value":76,"label":"罗芳"},{"value":81,"label":"杨淦"},{"value":82,"label":"何方静"},{"value":83,"label":"邹丽云"},{"value":86,"label":"游振军"},{"value":88,"label":"房秋红"},{"value":99,"label":"孟会顶"},{"value":101,"label":"周婧"},{"value":108,"label":"陈朝用"},{"value":110,"label":"张小凤"},{"value":112,"label":"汤清"},{"value":113,"label":"裴甜"},{"value":114,"label":"李豆"},{"value":118,"label":"Thomas Malone"},{"value":119,"label":"常峰"},{"value":123,"label":"许倩1"},{"value":140,"label":"林子成"},{"value":144,"label":"谭雪岭"},{"value":145,"label":"任小刚"},{"value":146,"label":"陈锐锐"},{"value":149,"label":"洪书秀"},{"value":152,"label":"李晨翔"},{"value":154,"label":"赖龙威"},{"value":158,"label":"林鸿飞"},{"value":159,"label":"马艾敏"},{"value":161,"label":"郑成"},{"value":162,"label":"林航"},{"value":164,"label":"林湘耀"},{"value":168,"label":"高倩倩"},{"value":169,"label":"殷春桃"},{"value":174,"label":"余娇"},{"value":175,"label":"涂夏辉"},{"value":179,"label":"黄辉"},{"value":182,"label":"梁瑞福"},{"value":188,"label":"郑伟"},{"value":190,"label":"林辉"},{"value":191,"label":"陈慧琴"},{"value":195,"label":"刘神利"},{"value":196,"label":"李杰"},{"value":197,"label":"毛灵灵"},{"value":198,"label":"林超然"},{"value":199,"label":"林绍东"},{"value":204,"label":"郑黉宾"},{"value":300,"label":"系统"},{"value":301,"label":"叶潇凯"},{"value":305,"label":"杨柳清"},{"value":306,"label":"向玥"},{"value":314,"label":"王松根"},{"value":315,"label":"杨淦"},{"value":316,"label":"李强强"},{"value":320,"label":"谢子钰"},{"value":323,"label":"章志伟"},{"value":324,"label":"林金聪"},{"value":325,"label":"何奇恩"},{"value":326,"label":"郑智洲"},{"value":327,"label":"邓铃烽"},{"value":330,"label":"杨军"},{"value":331,"label":"张铭捷"},{"value":335,"label":"陈林儿"},{"value":336,"label":"陈宸"},{"value":339,"label":"庄子南"},{"value":341,"label":"连钰雯"},{"value":342,"label":"李清"},{"value":343,"label":"李莹"},{"value":345,"label":"吴贤青"},{"value":353,"label":"林娟"},{"value":357,"label":"林毅"},{"value":360,"label":"郑宏伟"},{"value":363,"label":"钟媛琳"},{"value":364,"label":"吴晓燕"},{"value":365,"label":"牛文庆"},{"value":368,"label":"陈祥"},{"value":369,"label":"胡可超"},{"value":370,"label":"苏晓斌"},{"value":371,"label":"杜德华"},{"value":372,"label":"王芳芳"},{"value":374,"label":"陈雄"},{"value":375,"label":"尧舜哲"},{"value":377,"label":"翁文辉"},{"value":378,"label":"张丽"},{"value":379,"label":"黄文平"},{"value":381,"label":"陈熙"},{"value":383,"label":"刘用锵"},{"value":384,"label":"史梦雪"},{"value":387,"label":"倪萍倩"},{"value":388,"label":"彭丽"},{"value":389,"label":"陈旭东"},{"value":393,"label":"杨淑敏"},{"value":395,"label":"施嘉华"},{"value":396,"label":"苏辉清"},{"value":398,"label":"张晨君"},{"value":401,"label":"范志凯"},{"value":402,"label":"张强斌"},{"value":403,"label":"何雨漩"},{"value":404,"label":"林同辉"},{"value":406,"label":"刘鑫怡"},{"value":407,"label":"林宇"},{"value":409,"label":"刘百花"},{"value":411,"label":"郑新丽"},{"value":413,"label":"许海防"},{"value":414,"label":"黄汉臣"},{"value":416,"label":"林登健"},{"value":417,"label":"林永洪"},{"value":419,"label":"陈以鸿"},{"value":420,"label":"王士丹"},{"value":423,"label":"郑舒颖"},{"value":424,"label":"郑贵亮"},{"value":425,"label":"李凯鑫"},{"value":428,"label":"余斌"},{"value":429,"label":"何铃平"},{"value":430,"label":"范文文"},{"value":431,"label":"张金秀"},{"value":433,"label":"蒋华亮"},{"value":439,"label":"陈立坚"},{"value":440,"label":"李享悦"},{"value":442,"label":"包思霞"},{"value":448,"label":"林辉河"},{"value":454,"label":"刘玉鹏"},{"value":456,"label":"林学威"},{"value":461,"label":"许民"},{"value":462,"label":"胡可成"},{"value":463,"label":"陈胡斌"},{"value":464,"label":"曾意馨"},{"value":472,"label":"韦春慧"},{"value":475,"label":"戴群权"},{"value":801,"label":"黄萃"},{"value":802,"label":"李光源"},{"value":803,"label":"连亦芳"},{"value":804,"label":"陈靖航"},{"value":805,"label":"林天枢"},{"value":806,"label":"陈晓萱"},{"value":808,"label":"冯双来"},{"value":809,"label":"陈林"},{"value":810,"label":"高澄清"},{"value":811,"label":"杨晓燕"},{"value":812,"label":"张榕"},{"value":815,"label":"陈聃聃"},{"value":817,"label":"刘孟颖"},{"value":818,"label":"侯鸣宇"},{"value":819,"label":"马孝"},{"value":821,"label":"黄鑫"},{"value":823,"label":"叶金荣"},{"value":825,"label":"张帆"},{"value":826,"label":"陈静康"},{"value":827,"label":"董浩"},{"value":829,"label":"阙鹏强"},{"value":830,"label":"陈振枝"},{"value":832,"label":"陈思远"},{"value":833,"label":"张孝榕"},{"value":834,"label":"黄道钧"},{"value":835,"label":"买豪森"},{"value":836,"label":"张巧逢"},{"value":837,"label":"赖燊灿"},{"value":838,"label":"上官源森"},{"value":839,"label":"王志敏"},{"value":841,"label":"林擎"},{"value":842,"label":"郑昆彬"},{"value":844,"label":"刘佳"},{"value":845,"label":"叶孝廷"},{"value":847,"label":"薛磊"},{"value":848,"label":"张延秀"},{"value":852,"label":"赵晨颖"},{"value":853,"label":"陈秦禾"},{"value":855,"label":"陈佳明"},{"value":856,"label":"谢世雄"},{"value":857,"label":"赵鑫"},{"value":858,"label":"施余颖"},{"value":859,"label":"吴贞龙"},{"value":860,"label":"阮禾"},{"value":861,"label":"向绪慧"},{"value":866,"label":"顾君成"},{"value":869,"label":"刘涵昕"},{"value":872,"label":"张凯荣"},{"value":876,"label":"林秋婷"},{"value":885,"label":"刘佳慧"},{"value":886,"label":"林哲隆"},{"value":888,"label":"陈雨婷"},{"value":900,"label":"徐传建"},{"value":906,"label":"周峻"},{"value":916,"label":"李梓涵"},{"value":917,"label":"金镂石"},{"value":918,"label":"张鑫"},{"value":919,"label":"连淼"},{"value":920,"label":"杨涛"},{"value":921,"label":"余小芬"},{"value":922,"label":"乔彤"},{"value":923,"label":"韩其委"},{"value":924,"label":"黄淦"},{"value":925,"label":"林语佳"},{"value":926,"label":"肖进衍"},{"value":927,"label":"杜静雅"},{"value":928,"label":"阮晓雯"},{"value":929,"label":"郑舒颖"},{"value":930,"label":"gmtest"},{"value":931,"label":"张旭"},{"value":932,"label":"李娇娇"},{"value":933,"label":"李金华"},{"value":934,"label":"石晋阳"},{"value":935,"label":"高艺斌"},{"value":936,"label":"郑雪梅"},{"value":937,"label":"张少聪"},{"value":938,"label":"NOURELDEN SALEH ALI HAMOUDA"},{"value":939,"label":"丁汉辰"},{"value":940,"label":"李泽"},{"value":941,"label":"刘思忆"},{"value":942,"label":"姚志伟"},{"value":943,"label":"施烨子"},{"value":944,"label":"陈南杰"},{"value":945,"label":"李林峰"},{"value":946,"label":"刘金桥"},{"value":947,"label":"SERAG MANSOOR ABDULRAHMAN ALI"},{"value":948,"label":"张法权"},{"value":949,"label":"李虎"},{"value":950,"label":"王荣贵"},{"value":951,"label":"马魁宇"},{"value":952,"label":"刘星宇"},{"value":953,"label":"马胜南"},{"value":954,"label":"张琦"},{"value":955,"label":"曹晨景"},{"value":956,"label":"杨天翱"},{"value":957,"label":"赵启鹏"},{"value":958,"label":"徐玉京"},{"value":959,"label":"杨博宁"},{"value":960,"label":"施江麟"},{"value":961,"label":"王宏远"},{"value":962,"label":"吴雪冬"},{"value":963,"label":"郑一凡"},{"value":964,"label":"闫鹏"},{"value":965,"label":"qatest"},{"value":966,"label":"陈希"},{"value":967,"label":"gmtest"},{"value":968,"label":"陈清婷"},{"value":969,"label":"仵凡"},{"value":970,"label":"杨金火"},{"value":971,"label":"吴学强"},{"value":972,"label":"陈狄"},{"value":973,"label":"衣凯新"},{"value":974,"label":"李迎锋"},{"value":975,"label":"黄修灵"},{"value":976,"label":"高小迪"},{"value":977,"label":"李虎生"},{"value":978,"label":"何山伟"},{"value":979,"label":"沐帆"},{"value":980,"label":"杨鑫"},{"value":981,"label":"庄玉敏"},{"value":982,"label":"李家成"},{"value":983,"label":"肖岚"},{"value":984,"label":"赵康弟"},{"value":985,"label":"陈荣辉"},{"value":986,"label":"冯桂芝"},{"value":987,"label":"王姗"},{"value":988,"label":"郭茂宗"},{"value":989,"label":"赵长淳"},{"value":990,"label":"张小煊"},{"value":991,"label":"周胜硕"},{"value":992,"label":"王欣然"},{"value":993,"label":"林宝强"},{"value":994,"label":"万昱辰"},{"value":995,"label":"李鋆洳"},{"value":996,"label":"陈燕蓉"},{"value":997,"label":"吴岚春"}],
            };
        },
    };
</script>
```

:::

### 表单验证

:::demo

```html

<el-form ref="form" size="small" :model="formData">
    <el-form-item prop="value" :rules="rule">
        <o-multiselect
            v-model="formData.value"
            multiple
            :data="options"
        ></o-multiselect>
    </el-form-item>
    <el-form-item>
        <el-button type="primary" @click="reset">重置</el-button>
    </el-form-item>
</el-form>

<script>
    export default {
        data() {
            return {
                options: [
                    {
                        label: `option 1`,
                        value: 0,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: 1,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: 2,
                        selected: false,
                        disabled: true,
                    },
                ],
                formData: {
                    value: ""
                },
                rule: [
                    { required: true, message: '请选择', trigger: 'blur' },
                ],
            };
        },
        methods: {
            reset() {
                this.$refs.form.resetFields();
            }
        }
    };
</script>
```

:::

### GM 后台王国控件

:::demo

```html

<div>
    <o-multiselect
            :width="200"
            v-model="value"
            multiple
            enable-interval-filter
            placeholder="请选择王国"
            :data="options"
            select-type="king"
            default-topping
            @change="handleVueChange"
            @clear="handleClear"
    ></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: [2, 3],
                disabled: false,
                options: [],
            };
        },
        methods: {
            handleVueChange(values) {
                console.log('values:', values);
            },
            handleClear() {
                console.log('clear');
            }
        },
        created() {
            /* const options = [];
            for (let i = 1; i < 1001; i++) {
                const disabled = i === 1 ? true : false;
                options.push({
                    label: `王国${i}[第三阶段]`,
                    value: `${i}`,
                    selected: false,
                    disabled,
                });
            }
            this.options = options; */
            this.options = [{"value":1,"label":"王国1[第3阶段]","openTimeStamp":1682035897},{"value":2,"label":"王国2[第3阶段]","openTimeStamp":1687150762},{"value":3,"label":"王国3[第3阶段]","openTimeStamp":1687273744},{"value":4,"label":"王国4[第3阶段]","openTimeStamp":1687450757},{"value":5,"label":"王国5[第3阶段]","openTimeStamp":1687593743},{"value":6,"label":"王国6[第3阶段]","openTimeStamp":1687738823},{"value":7,"label":"王国7[第3阶段]","openTimeStamp":1687917552},{"value":8,"label":"王国8[第3阶段]","openTimeStamp":1688065627},{"value":9,"label":"王国9[第3阶段]","openTimeStamp":1688179575},{"value":10,"label":"王国10[第3阶段]","openTimeStamp":1688313039},{"value":11,"label":"王国11[第3阶段]","openTimeStamp":1688399842},{"value":12,"label":"王国12[第3阶段]","openTimeStamp":1688517325},{"value":13,"label":"王国13[第3阶段]","openTimeStamp":1688606918},{"value":14,"label":"王国14[第3阶段]","openTimeStamp":1688775206},{"value":15,"label":"王国15[第3阶段]","openTimeStamp":1688956992},{"value":16,"label":"王国16[第3阶段]","openTimeStamp":1689206745},{"value":17,"label":"王国17[第3阶段]","openTimeStamp":1689552229},{"value":18,"label":"王国18[第3阶段]","openTimeStamp":1689920414},{"value":19,"label":"王国19[第3阶段]","openTimeStamp":1690246806},{"value":20,"label":"王国20[第3阶段]","openTimeStamp":1690560955},{"value":21,"label":"王国21[第3阶段]","openTimeStamp":1697419221},{"value":22,"label":"王国22[第3阶段]","openTimeStamp":1697763943},{"value":23,"label":"王国23[第3阶段]","openTimeStamp":1698109348},{"value":24,"label":"王国24[第3阶段]","openTimeStamp":1698454882},{"value":25,"label":"王国25[第3阶段]","openTimeStamp":1698801118},{"value":26,"label":"王国26[第3阶段]","openTimeStamp":1699146785},{"value":27,"label":"王国27[第3阶段]","openTimeStamp":1699491748},{"value":28,"label":"王国28[第3阶段]","openTimeStamp":1699837929},{"value":29,"label":"王国29[第3阶段]","openTimeStamp":1700183163},{"value":30,"label":"王国30[第3阶段]","openTimeStamp":1700528518},{"value":31,"label":"王国31[第3阶段]","openTimeStamp":1700875077},{"value":32,"label":"王国32[第3阶段]","openTimeStamp":1701219922},{"value":33,"label":"王国33[第3阶段]","openTimeStamp":1701565680},{"value":34,"label":"王国34[第3阶段]","openTimeStamp":1701911813},{"value":35,"label":"王国35[第3阶段]","openTimeStamp":1702265988},{"value":36,"label":"王国36[第3阶段]","openTimeStamp":1702602241},{"value":37,"label":"王国37[第3阶段]","openTimeStamp":1702950008},{"value":38,"label":"王国38[第3阶段]","openTimeStamp":1703296821},{"value":39,"label":"王国39[第3阶段]","openTimeStamp":1703640348},{"value":40,"label":"王国40[第3阶段]","openTimeStamp":1703988740},{"value":41,"label":"王国41[第3阶段]","openTimeStamp":1704334559},{"value":42,"label":"王国42[第3阶段]","openTimeStamp":1704679721},{"value":43,"label":"王国43[第3阶段]","openTimeStamp":1705024995},{"value":44,"label":"王国44[第3阶段]","openTimeStamp":1705370499},{"value":45,"label":"王国45[第3阶段]","openTimeStamp":1705716053},{"value":46,"label":"王国46[第3阶段]","openTimeStamp":1706062129},{"value":47,"label":"王国47[第3阶段]","openTimeStamp":1706407298},{"value":48,"label":"王国48[第3阶段]","openTimeStamp":1706771916},{"value":49,"label":"王国49[第2阶段]","openTimeStamp":1710925568}]
        },
        mounted() {
            setTimeout(() => {
                this.options[1].disabled = true;
                this.options = this.options.slice();
            }, 2000);
        },
    };
</script>
```

:::

### 多选隐藏全选按钮

:::demo

```html

<div>
    <o-multiselect
            multiple
            v-model="value"
            :enable-select-all="false"
            :data="options"
    ></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [
                    {
                        label: `option 1`,
                        value: `onemt-1`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: `onemt-2`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: `onemt-3`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 4`,
                        value: `onemt-4`,
                        selected: false,
                        disabled: false,
                    },
                ],
            };
        },
    };
</script>
```

:::

### 多选隐藏反选按钮

:::demo

```html

<div>
    <o-multiselect
            multiple
            v-model="value"
            :enable-inverted-select="false"
            :data="options"
    ></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [
                    {
                        label: `option 1`,
                        value: `onemt-1`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: `onemt-2`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: `onemt-3`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 4`,
                        value: `onemt-4`,
                        selected: false,
                        disabled: false,
                    },
                ],
            };
        },
    };
</script>
```

:::

### 禁用/启用

:::demo

```html

<div>
    <o-multiselect
            multiple
            v-model="value"
            :data="options"
            :disabled="disabled"
    ></o-multiselect>
    <el-switch
            style="margin-left: 6px;"
            v-model="disabled"
            active-color="#ff4949"
            inactive-color="#13ce66"
    >
    </el-switch>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                disabled: false,
                options: [],
            };
        },
        mounted() {
            setTimeout(() => {
                this.options = [
                    {
                        label: `option 1`,
                        value: `onemt-1`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: `onemt-2`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: `onemt-3`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 4`,
                        value: `onemt-4`,
                        selected: false,
                        disabled: false,
                    },
                ];
            }, 1500);
        },
    };
</script>
```

:::

### 不显示清除按钮

:::demo

```html

<div>
    <o-multiselect
            multiple
            v-model="value"
            :data="options"
            :clearable="false"
    ></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [],
            };
        },
        mounted() {
            setTimeout(() => {
                this.options = [
                    {
                        label: `option 1`,
                        value: `onemt-1`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: `onemt-2`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: `onemt-3`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 4`,
                        value: `onemt-4`,
                        selected: false,
                        disabled: false,
                    },
                ];
            }, 1500);
        },
    };
</script>
```

:::

### 设置宽高

:::demo

```html

<div>
    <o-multiselect
            multiple
            v-model="value"
            :data="options"
            :width="120"
            :height="44"
    ></o-multiselect>
</div>

<script>
    export default {
        data() {
            return {
                value: "",
                options: [],
            };
        },
        mounted() {
            setTimeout(() => {
                this.options = [
                    {
                        label: `option 1`,
                        value: `onemt-1`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 2`,
                        value: `onemt-2`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 3`,
                        value: `onemt-3`,
                        selected: false,
                        disabled: false,
                    },
                    {
                        label: `option 4`,
                        value: `onemt-4`,
                        selected: false,
                        disabled: false,
                    },
                ];
            }, 1500);
        },
    };
</script>
```

:::

### GM 反选

:::demo

```html

<div>
    <o-multiselect
            :width="200"
            v-model="value"
            multiple
            :data="options"
    ></o-multiselect>
    <el-button size="small" @click="getValue">取值</el-button>
</div>

<script>
    export default {
        data() {
            return {
                value: [],
                disabled: false,
                options: [],
            };
        },
        methods: {
            getValue() {
                this.$nextTick(function () {
                    alert(this.value.toString());
                });
            },
        },
        created() {
            this.options = [{"value": 80000132, "label": "神兵天降-49.99 0[80000132]$49.99"}, {
                "value": 80000133,
                "label": "神兵天降-99.99 0[80000133]$99.99"
            }, {"value": 80000134, "label": "粮食补给-0.99 0[80000134]$0.99"}, {
                "value": 80000135,
                "label": "粮食补给-4.99 0[80000135]$4.99"
            }, {"value": 80000136, "label": "粮食补给-9.99 0[80000136]$9.99"}, {
                "value": 80000137,
                "label": "粮食补给-19.99 0[80000137]$19.99"
            }, {"value": 80000138, "label": "粮食补给-49.99 0[80000138]$49.99"}, {
                "value": 80000139,
                "label": "粮食补给-99.99 0[80000139]$99.99"
            }, {"value": 80000140, "label": "木材补给-0.99 0[80000140]$0.99"}, {
                "value": 80000141,
                "label": "木材补给-4.99 0[80000141]$4.99"
            }, {"value": 80000142, "label": "木材补给-9.99 0[80000142]$9.99"}, {
                "value": 80000143,
                "label": "木材补给-19.99 0[80000143]$19.99"
            }, {"value": 80000144, "label": "木材补给-49.99 0[80000144]$49.99"}, {
                "value": 80000145,
                "label": "木材补给-99.99 0[80000145]$99.99"
            }, {"value": 80000146, "label": "铁矿补给-0.99 0[80000146]$0.99"}, {
                "value": 80000147,
                "label": "铁矿补给-4.99 0[80000147]$4.99"
            }, {"value": 80000148, "label": "铁矿补给-9.99 0[80000148]$9.99"}, {
                "value": 80000149,
                "label": "铁矿补给-19.99 0[80000149]$19.99"
            }, {"value": 80000150, "label": "铁矿补给-49.99 0[80000150]$49.99"}, {
                "value": 80000151,
                "label": "铁矿补给-99.99 0[80000151]$99.99"
            }, {"value": 80000152, "label": "燃油补给-0.99 0[80000152]$0.99"}, {
                "value": 80000153,
                "label": "燃油补给-4.99 0[80000153]$4.99"
            }, {"value": 80000154, "label": "燃油补给-9.99 0[80000154]$9.99"}, {
                "value": 80000155,
                "label": "燃油补给-19.99 0[80000155]$19.99"
            }, {"value": 80000156, "label": "燃油补给-49.99 0[80000156]$49.99"}, {
                "value": 80000157,
                "label": "燃油补给-99.99 0[80000157]$99.99"
            }, {"value": 10010001, "label": "VIP0 尊享礼包-0.99 0[10010001]$0.99"}, {
                "value": 10010002,
                "label": "VIP1 尊享礼包-0.99 0[10010002]$0.99"
            }, {"value": 10010003, "label": "VIP2 尊享礼包-1.99 0[10010003]$1.99"}, {
                "value": 10010004,
                "label": "VIP3 尊享礼包-2.99 0[10010004]$2.99"
            }, {"value": 10010005, "label": "VIP4 尊享礼包-2.99 0[10010005]$2.99"}, {
                "value": 10010006,
                "label": "VIP5 尊享礼包-4.99 0[10010006]$4.99"
            }, {"value": 10010007, "label": "VIP6 尊享礼包-9.99 0[10010007]$9.99"}, {
                "value": 10010008,
                "label": "VIP7 尊享礼包-9.99 0[10010008]$9.99"
            }, {"value": 10010009, "label": "VIP8 尊享礼包-19.99 0[10010009]$19.99"}, {
                "value": 10010010,
                "label": "VIP9 尊享礼包-49.99 0[10010010]$49.99"
            }, {"value": 10010011, "label": "VIP10 尊享礼包-99.99 0[10010011]$99.99"}, {
                "value": 10010012,
                "label": "VIP11 尊享礼包-99.99 0[10010012]$99.99"
            }, {"value": 10010013, "label": "VIP12 尊享礼包-99.99 0[10010013]$99.99"}, {
                "value": 10010014,
                "label": "VIP13 尊享礼包-99.99 0[10010014]$99.99"
            }, {"value": 10010015, "label": "VIP14 尊享礼包-99.99 0[10010015]$99.99"}, {
                "value": 10010016,
                "label": "VIP15 尊享礼包-99.99 0[10010016]$99.99"
            }, {"value": 10010017, "label": "VIP16 尊享礼包-99.99 0[10010017]$99.99"}, {
                "value": 10010018,
                "label": "VIP17 尊享礼包-99.99 0[10010018]$99.99"
            }, {"value": 10010019, "label": "VIP18 尊享礼包-99.99 0[10010019]$99.99"}, {
                "value": 10050001,
                "label": "首充礼包-0.99 0[10050001]$0.99"
            }, {"value": 10050002, "label": "续充礼包-4.99 0[10050002]$4.99"}, {
                "value": 10050003,
                "label": "续充礼包-9.99 0[10050003]$9.99"
            }, {"value": 10050004, "label": "续充礼包-19.99 0[10050004]$19.99"}, {
                "value": 10050005,
                "label": "续充礼包-49.99 0[10050005]$49.99"
            }, {"value": 10050006, "label": "续充礼包-99.99 0[10050006]$99.99"}, {
                "value": 40000001,
                "label": "成长基金-4.99 0[40000001]$4.99"
            }, {"value": 50000001, "label": "每日特惠-流亡者0.99 0[50000001]$0.99"}, {
                "value": 50000002,
                "label": "每日特惠-加速1.99 0[50000002]$0.99"
            }, {"value": 50000003, "label": "每日特惠-资源0.99 0[50000003]$0.99"}, {
                "value": 60000001,
                "label": "基地升级包1-0.99 0[60000001]$0.99"
            }, {"value": 60000002, "label": "基地升级包2-4.99 0[60000002]$4.99"}, {
                "value": 60000003,
                "label": "基地升级包3-9.99 0[60000003]$9.99"
            }, {"value": 60000004, "label": "基地升级包4-19.99 0[60000004]$19.99"}, {
                "value": 60000005,
                "label": "基地特供-49.99 0[60000005]$49.99"
            }, {"value": 60000006, "label": "基地专享-99.99 0[60000006]$99.99"}, {
                "value": 60000007,
                "label": "建筑奇迹-99.99 0[60000007]$99.99"
            }, {"value": 60000014, "label": "战场经验-0.99 0[60000014]$0.99"}, {
                "value": 60000015,
                "label": "战场经验-4.99 0[60000015]$4.99"
            }, {"value": 60000016, "label": "战场经验-9.99 0[60000016]$9.99"}, {
                "value": 60000017,
                "label": "战场经验-19.99 0[60000017]$19.99"
            }, {"value": 60000018, "label": "战场经验-49.99 0[60000018]$49.99"}, {
                "value": 60000019,
                "label": "战场经验-99.99 0[60000019]$99.99"
            }, {"value": 10000001, "label": "少量马克币-0.99 0[10000001]$0.99"}, {
                "value": 10000002,
                "label": "一堆马克币-4.99 0[10000002]$4.99"
            }, {"value": 10000003, "label": "一小桶马克币-9.99 0[10000003]$9.99"}, {
                "value": 10000004,
                "label": "一大盒马克币-19.99 0[10000004]$19.99"
            }, {"value": 10000005, "label": "一箱马克币-49.99 0[10000005]$49.99"}, {
                "value": 10000006,
                "label": "大量马克币-99.99 0[10000006]$99.99"
            }, {"value": 10010041, "label": "VIP0 尊享礼包-0.99 0[10010041]$0.99"}, {
                "value": 10010042,
                "label": "VIP1 尊享礼包-4.99 0[10010042]$4.99"
            }, {"value": 10010043, "label": "VIP2 尊享礼包-4.99 0[10010043]$4.99"}, {
                "value": 10010044,
                "label": "VIP3 尊享礼包-9.99 0[10010044]$9.99"
            }, {"value": 10010045, "label": "VIP4 尊享礼包-19.99 0[10010045]$19.99"}, {
                "value": 10010046,
                "label": "VIP5 尊享礼包-49.99 0[10010046]$49.99"
            }, {"value": 10010047, "label": "VIP6 尊享礼包-49.99 0[10010047]$49.99"}, {
                "value": 10010048,
                "label": "VIP7 尊享礼包-99.99 0[10010048]$99.99"
            }, {"value": 10010049, "label": "VIP8 尊享礼包-99.99 0[10010049]$99.99"}, {
                "value": 10010050,
                "label": "VIP9 尊享礼包-99.99 0[10010050]$99.99"
            }, {"value": 10010051, "label": "VIP10 尊享礼包-9.99 0[10010051]$9.99"}, {
                "value": 10010052,
                "label": "VIP11 尊享礼包-19.99 0[10010052]$19.99"
            }, {"value": 10010053, "label": "VIP12 尊享礼包-49.99 0[10010053]$49.99"}, {
                "value": 10010054,
                "label": "VIP13 尊享礼包-99.99 0[10010054]$99.99"
            }, {"value": 10010055, "label": "VIP14 尊享礼包-99.99 0[10010055]$99.99"}, {
                "value": 10010056,
                "label": "VIP15 尊享礼包-99.99 0[10010056]$99.99"
            }, {"value": 10010057, "label": "VIP16 尊享礼包-99.99 0[10010057]$99.99"}, {
                "value": 10010058,
                "label": "VIP17 尊享礼包-99.99 0[10010058]$99.99"
            }, {"value": 10010059, "label": "VIP18 尊享礼包-99.99 0[10010059]$99.99"}, {
                "value": 10050011,
                "label": "首充礼包-0.99 0[10050011]$0.99"
            }, {"value": 10050012, "label": "续充礼包-4.99 0[10050012]$4.99"}, {
                "value": 10050013,
                "label": "续充礼包-9.99 0[10050013]$9.99"
            }, {"value": 10050014, "label": "续充礼包-19.99 0[10050014]$19.99"}, {
                "value": 10050015,
                "label": "续充礼包-49.99 0[10050015]$49.99"
            }, {"value": 10050016, "label": "续充礼包-99.99 0[10050016]$99.99"}, {
                "value": 20000001,
                "label": "大兴土木-0.99 0[20000001]$0.99"
            }, {"value": 20000002, "label": "大兴土木-4.99 0[20000002]$4.99"}, {
                "value": 20000003,
                "label": "大兴土木-9.99 0[20000003]$9.99"
            }, {"value": 20000004, "label": "大兴土木-19.99 0[20000004]$19.99"}, {
                "value": 20000005,
                "label": "大兴土木-49.99 0[20000005]$49.99"
            }, {"value": 20000006, "label": "大兴土木-99.99 0[20000006]$99.99"}, {
                "value": 20000007,
                "label": "资源储备-0.99 0[20000007]$0.99"
            }, {"value": 20000008, "label": "资源储备-4.99 0[20000008]$4.99"}, {
                "value": 20000009,
                "label": "资源储备-9.99 0[20000009]$9.99"
            }, {"value": 20000010, "label": "资源储备-19.99 0[20000010]$19.99"}, {
                "value": 20000011,
                "label": "资源储备-49.99 0[20000011]$49.99"
            }, {"value": 20000012, "label": "资源储备-99.99 0[20000012]$99.99"}, {
                "value": 20000022,
                "label": "极速城建-9.99 0[20000022]$9.99"
            }, {"value": 20000023, "label": "极速城建-19.99 0[20000023]$19.99"}, {
                "value": 20000024,
                "label": "极速城建-49.99 0[20000024]$49.99"
            }, {"value": 20000025, "label": "极速城建-99.99 0[20000025]$99.99"}, {
                "value": 20000031,
                "label": "强化科技-4.99 0[20000031]$4.99"
            }, {"value": 20000032, "label": "强化科技-9.99 0[20000032]$9.99"}, {
                "value": 20000033,
                "label": "强化科技-19.99 0[20000033]$19.99"
            }, {"value": 20000034, "label": "强化科技-49.99 0[20000034]$49.99"}, {
                "value": 20000035,
                "label": "强化科技-99.99 0[20000035]$99.99"
            }, {"value": 20000041, "label": "壮大军队-4.99 0[20000041]$4.99"}, {
                "value": 20000042,
                "label": "壮大军队-9.99 0[20000042]$9.99"
            }, {"value": 20000043, "label": "壮大军队-19.99 0[20000043]$19.99"}, {
                "value": 20000044,
                "label": "壮大军队-49.99 0[20000044]$49.99"
            }, {"value": 20000045, "label": "壮大军队-99.99 0[20000045]$99.99"}, {
                "value": 20000051,
                "label": "超值资源-4.99 0[20000051]$4.99"
            }, {"value": 20000052, "label": "超值资源-9.99 0[20000052]$9.99"}, {
                "value": 20000053,
                "label": "超值资源-19.99 0[20000053]$19.99"
            }, {"value": 20000054, "label": "超值资源-49.99 0[20000054]$49.99"}, {
                "value": 20000055,
                "label": "超值资源-99.99 0[20000055]$99.99"
            }, {"value": 20000061, "label": "传奇流亡者-4.99 0[20000061]$4.99"}, {
                "value": 20000062,
                "label": "传奇流亡者-9.99 0[20000062]$9.99"
            }, {"value": 20000063, "label": "传奇流亡者-19.99 0[20000063]$19.99"}, {
                "value": 20000064,
                "label": "传奇流亡者-49.99 0[20000064]$49.99"
            }, {"value": 20000065, "label": "传奇流亡者-99.99 0[20000065]$99.99"}, {
                "value": 21000001,
                "label": "城市发展-0.99 0[21000001]$0.99"
            }, {"value": 21000002, "label": "城市发展-4.99 0[21000002]$4.99"}, {
                "value": 21000003,
                "label": "城市发展-9.99 0[21000003]$9.99"
            }, {"value": 21000004, "label": "城市发展-19.99 0[21000004]$19.99"}, {
                "value": 21000005,
                "label": "城市发展-49.99 0[21000005]$49.99"
            }, {"value": 21000006, "label": "城市发展-99.99 0[21000006]$99.99"}, {
                "value": 21000007,
                "label": "资源补给包-0.99 0[21000007]$0.99"
            }, {"value": 21000008, "label": "资源补给包-4.99 0[21000008]$4.99"}, {
                "value": 21000009,
                "label": "资源补给包-9.99 0[21000009]$9.99"
            }, {"value": 21000010, "label": "资源补给包-19.99 0[21000010]$19.99"}, {
                "value": 21000011,
                "label": "资源补给包-49.99 0[21000011]$49.99"
            }, {"value": 21000012, "label": "资源补给包-99.99 0[21000012]$99.99"}, {
                "value": 30000001,
                "label": "至尊月卡-4.99 0[30000001]$4.99"
            }, {"value": 30000002, "label": "流亡者黄金月卡-19.99 0[30000002]$19.99"}, {
                "value": 30000003,
                "label": "尊享加速周卡-4.99 0[30000003]$4.99"
            }, {"value": 40000002, "label": "成长基金-19.99 0[40000002]$19.99"}, {
                "value": 50000004,
                "label": "每日特惠1-0.99 0[50000004]$0.99"
            }, {"value": 50000005, "label": "每日特惠2-1.99 0[50000005]$1.99"}, {
                "value": 50000006,
                "label": "每日特惠3-4.99 0[50000006]$4.99"
            }, {"value": 60000008, "label": "精英育成-凯特琳-0.99 0[60000008]$0.99"}, {
                "value": 60000009,
                "label": "精英育成-凯特琳-4.99 0[60000009]$4.99"
            }, {"value": 60000010, "label": "精英育成-凯特琳-9.99 0[60000010]$9.99"}, {
                "value": 60000011,
                "label": "精英育成-凯特琳-19.99 0[60000011]$19.99"
            }, {"value": 60000012, "label": "精英育成-凯特琳-49.99 0[60000012]$49.99"}, {
                "value": 60000013,
                "label": "精英育成-凯特琳-99.99 0[60000013]$99.99"
            }, {"value": 60000020, "label": "精英育成-香浓-0.99 0[60000020]$0.99"}, {
                "value": 60000021,
                "label": "精英育成-香浓-4.99 0[60000021]$4.99"
            }, {"value": 60000022, "label": "精英育成-香浓-9.99 0[60000022]$9.99"}, {
                "value": 60000023,
                "label": "精英育成-香浓-19.99 0[60000023]$19.99"
            }, {"value": 60000024, "label": "精英育成-香浓-49.99 0[60000024]$49.99"}, {
                "value": 60000025,
                "label": "精英育成-香浓-99.99 0[60000025]$99.99"
            }, {"value": 60000026, "label": "精英育成-梅森-0.99 0[60000026]$0.99"}, {
                "value": 60000027,
                "label": "精英育成-梅森-4.99 0[60000027]$4.99"
            }, {"value": 60000028, "label": "精英育成-梅森-9.99 0[60000028]$9.99"}, {
                "value": 60000029,
                "label": "精英育成-梅森-19.99 0[60000029]$19.99"
            }, {"value": 60000030, "label": "精英育成-梅森-49.99 0[60000030]$49.99"}, {
                "value": 60000031,
                "label": "精英育成-梅森-99.99 0[60000031]$99.99"
            }, {"value": 60000032, "label": "精英育成-诺亚-0.99 0[60000032]$0.99"}, {
                "value": 60000033,
                "label": "精英育成-诺亚-4.99 0[60000033]$4.99"
            }, {"value": 60000034, "label": "精英育成-诺亚-9.99 0[60000034]$9.99"}, {
                "value": 60000035,
                "label": "精英育成-诺亚-19.99 0[60000035]$19.99"
            }, {"value": 60000036, "label": "精英育成-诺亚-49.99 0[60000036]$49.99"}, {
                "value": 60000037,
                "label": "精英育成-诺亚-99.99 0[60000037]$99.99"
            }, {"value": 60000038, "label": "精英育成-亚历克斯-0.99 0[60000038]$0.99"}, {
                "value": 60000039,
                "label": "精英育成-亚历克斯-4.99 0[60000039]$4.99"
            }, {"value": 60000040, "label": "精英育成-亚历克斯-9.99 0[60000040]$9.99"}, {
                "value": 60000041,
                "label": "精英育成-亚历克斯-19.99 0[60000041]$19.99"
            }, {"value": 60000042, "label": "精英育成-亚历克斯-49.99 0[60000042]$49.99"}, {
                "value": 60000043,
                "label": "精英育成-亚历克斯-99.99 0[60000043]$99.99"
            }, {"value": 60000044, "label": "精英育成-死神-0.99 0[60000044]$0.99"}, {
                "value": 60000045,
                "label": "精英育成-死神-4.99 0[60000045]$4.99"
            }, {"value": 60000046, "label": "精英育成-死神-9.99 0[60000046]$9.99"}, {
                "value": 60000047,
                "label": "精英育成-死神-19.99 0[60000047]$19.99"
            }, {"value": 60000048, "label": "精英育成-死神-49.99 0[60000048]$49.99"}, {
                "value": 60000049,
                "label": "精英育成-死神-99.99 0[60000049]$99.99"
            }, {"value": 60000050, "label": "精英育成-夏娃-0.99 0[60000050]$0.99"}, {
                "value": 60000051,
                "label": "精英育成-夏娃-4.99 0[60000051]$4.99"
            }, {"value": 60000052, "label": "精英育成-夏娃-9.99 0[60000052]$9.99"}, {
                "value": 60000053,
                "label": "精英育成-夏娃-19.99 0[60000053]$19.99"
            }, {"value": 60000054, "label": "精英育成-夏娃-49.99 0[60000054]$49.99"}, {
                "value": 60000055,
                "label": "精英育成-夏娃-99.99 0[60000055]$99.99"
            }, {"value": 60000056, "label": "精英育成-拉拉-0.99 0[60000056]$0.99"}, {
                "value": 60000057,
                "label": "精英育成-拉拉-4.99 0[60000057]$4.99"
            }, {"value": 60000058, "label": "精英育成-拉拉-9.99 0[60000058]$9.99"}, {
                "value": 60000059,
                "label": "精英育成-拉拉-19.99 0[60000059]$19.99"
            }, {"value": 60000060, "label": "精英育成-拉拉-49.99 0[60000060]$49.99"}, {
                "value": 60000061,
                "label": "精英育成-拉拉-99.99 0[60000061]$99.99"
            }, {"value": 60000062, "label": "精英育成-乔纳森-0.99 0[60000062]$0.99"}, {
                "value": 60000063,
                "label": "精英育成-乔纳森-4.99 0[60000063]$4.99"
            }, {"value": 60000064, "label": "精英育成-乔纳森-9.99 0[60000064]$9.99"}, {
                "value": 60000065,
                "label": "精英育成-乔纳森-19.99 0[60000065]$19.99"
            }, {"value": 60000066, "label": "精英育成-乔纳森-49.99 0[60000066]$49.99"}, {
                "value": 60000067,
                "label": "精英育成-乔纳森-99.99 0[60000067]$99.99"
            }, {"value": 60000068, "label": "城建加速包-0.99 0[60000068]$0.99"}, {
                "value": 60000069,
                "label": "城建加速包-4.99 0[60000069]$4.99"
            }, {"value": 60000070, "label": "城建加速包-9.99 0[60000070]$9.99"}, {
                "value": 60000071,
                "label": "城建加速包-19.99 0[60000071]$19.99"
            }, {"value": 60000072, "label": "城建加速包-49.99 0[60000072]$49.99"}, {
                "value": 60000073,
                "label": "城建加速包-99.99 0[60000073]$99.99"
            }, {"value": 60000074, "label": "科研加速包-0.99 0[60000074]$0.99"}, {
                "value": 60000075,
                "label": "科研加速包-4.99 0[60000075]$4.99"
            }, {"value": 60000076, "label": "科研加速包-9.99 0[60000076]$9.99"}, {
                "value": 60000077,
                "label": "科研加速包-19.99 0[60000077]$19.99"
            }, {"value": 60000078, "label": "科研加速包-49.99 0[60000078]$49.99"}, {
                "value": 60000079,
                "label": "科研加速包-99.99 0[60000079]$99.99"
            }, {"value": 60000080, "label": "训练加速包-0.99 0[60000080]$0.99"}, {
                "value": 60000081,
                "label": "训练加速包-4.99 0[60000081]$4.99"
            }, {"value": 60000082, "label": "训练加速包-9.99 0[60000082]$9.99"}, {
                "value": 60000083,
                "label": "训练加速包-19.99 0[60000083]$19.99"
            }, {"value": 60000084, "label": "训练加速包-49.99 0[60000084]$49.99"}, {
                "value": 60000085,
                "label": "训练加速包-99.99 0[60000085]$99.99"
            }, {"value": 60000086, "label": "治疗加速包-0.99 0[60000086]$0.99"}, {
                "value": 60000087,
                "label": "治疗加速包-4.99 0[60000087]$4.99"
            }, {"value": 60000088, "label": "治疗加速包-9.99 0[60000088]$9.99"}, {
                "value": 60000089,
                "label": "治疗加速包-19.99 0[60000089]$19.99"
            }, {"value": 60000090, "label": "治疗加速包-49.99 0[60000090]$49.99"}, {
                "value": 60000091,
                "label": "治疗加速包-99.99 0[60000091]$99.99"
            }, {"value": 60000101, "label": "7级极速城建-4.99 0[60000101]$4.99"}, {
                "value": 60000102,
                "label": "8级极速城建-4.99 0[60000102]$4.99"
            }, {"value": 60000103, "label": "10级极速城建-4.99 0[60000103]$4.99"}, {
                "value": 60000104,
                "label": "12级极速城建-9.99 0[60000104]$9.99"
            }, {"value": 60000105, "label": "16级极速城建-19.99 0[60000105]$19.99"}, {
                "value": 60000106,
                "label": "19级极速城建-49.99 0[60000106]$49.99"
            }, {"value": 60000107, "label": "21级极速城建-99.99 0[60000107]$99.99"}, {
                "value": 60000108,
                "label": "23级极速城建-99.99 0[60000108]$99.99"
            }, {"value": 60000109, "label": "25级极速城建-99.99 0[60000109]$99.99"}, {
                "value": 60000110,
                "label": "28级极速城建-99.99 0[60000110]$99.99"
            }, {"value": 70000001, "label": "第二建造队列礼包-4.99 0[70000001]$4.99"}, {
                "value": 80000001,
                "label": "茁壮成长-0.99 0[80000001]$0.99"
            }, {"value": 80000002, "label": "茁壮成长-4.99 0[80000002]$4.99"}, {
                "value": 80000003,
                "label": "茁壮成长-9.99 0[80000003]$9.99"
            }, {"value": 80000004, "label": "茁壮成长-19.99 0[80000004]$19.99"}, {
                "value": 80000005,
                "label": "茁壮成长-49.99 0[80000005]$49.99"
            }, {"value": 80000006, "label": "茁壮成长-99.99 0[80000006]$99.99"}, {
                "value": 90000001,
                "label": "获取能量源 战令-19.99 0[90000001]$19.99"
            }, {"value": 91000001, "label": "获取补给包-4.99 0[91000001]$4.99"}, {
                "value": 92000001,
                "label": "幸运转盘超值礼包Ⅰ-4.99 0[92000001]$4.99"
            }, {"value": 92000002, "label": "幸运转盘超值礼包Ⅱ-9.99 0[92000002]$9.99"}, {
                "value": 92000003,
                "label": "幸运转盘超值礼包Ⅲ-19.99 0[92000003]$19.99"
            }, {"value": 92000004, "label": "幸运转盘超值礼包Ⅳ-49.99 0[92000004]$49.99"}, {
                "value": 92000005,
                "label": "幸运转盘超值礼包Ⅴ-99.99 0[92000005]$99.99"
            }, {"value": 92000011, "label": "夏娃沃森限购礼包-9.99 0[92000011]$9.99"}, {
                "value": 92000012,
                "label": "夏娃沃森限购礼包-19.99 0[92000012]$19.99"
            }, {"value": 92000013, "label": "夏娃沃森限购礼包-49.99 0[92000013]$49.99"}, {
                "value": 92000014,
                "label": "夏娃沃森限购礼包-99.99 0[92000014]$99.99"
            }, {"value": 93000001, "label": "加速城建-4.99 0[93000001]$4.99"}, {
                "value": 93000002,
                "label": "加速城建-9.99 0[93000002]$9.99"
            }, {"value": 93000003, "label": "加速城建-19.99 0[93000003]$19.99"}, {
                "value": 93000004,
                "label": "加速城建-49.99 0[93000004]$49.99"
            }, {"value": 93000005, "label": "加速城建-99.99 0[93000005]$99.99"}, {
                "value": 93000011,
                "label": "死神MKI限购礼包-9.99 0[93000011]$9.99"
            }, {"value": 93000012, "label": "死神MKI限购礼包-19.99 0[93000012]$19.99"}, {
                "value": 93000013,
                "label": "死神MKI限购礼包-49.99 0[93000013]$49.99"
            }, {"value": 93000014, "label": "死神MKI限购礼包-99.99 0[93000014]$99.99"}, {
                "value": 93000021,
                "label": "部队先锋-4.99 0[93000021]$4.99"
            }, {"value": 93000022, "label": "部队先锋-9.99 0[93000022]$9.99"}, {
                "value": 93000023,
                "label": "部队先锋-19.99 0[93000023]$19.99"
            }, {"value": 93000024, "label": "部队先锋-49.99 0[93000024]$49.99"}, {
                "value": 93000025,
                "label": "部队先锋-99.99 0[93000025]$99.99"
            }];
        },
    };
</script>
```

:::

### Multiselect Attribute

| 参数                    | 说明                    | 类型    | 可选值                          | 默认值  |
| ---------------------- | ---------------------- | ------- | ------------------------------ | ------ |
| value / v-model        | 绑定的值                | any      | --                            | --     |
| placeholder            | 占位提示文字             | string  | --                             | 请选择  |
| data                   | 选项数据                | array    | --                            | --      |
| multiple               | 多选开关                | boolean  | true / false                  | false   |
| show-limit             | 已选择选项显示数量限制     | string  | number                         | 3       |
| select-limit           | 选择数量限制             | string   | number                        | Infinity |
| width | 输入框宽度 | number | -- | fit-content |
| size                   | 选择器尺寸             | string  | default / medium / small / mini | default |
| select-type            | 业务类型               | string  | king                            | normal  |
| disabled               | 是否禁用               | boolean | true / false                    | false   |
| place-as-top           | 是否显示置顶已选按钮   | boolean | true / false                    | false   |
| enable-select-all      | 是否显示全选按钮       | boolean | true / false                    | true    |
| enable-inverted-select | 是否显示反选按钮 | boolean | true / false | true |  

### Multiselect Events

| 事件名称 | 说明             | 回调参数      |
| -------- | ---------------- | ------------- |
| change   | 控件值改变时触发 | val: 控件的值 |
