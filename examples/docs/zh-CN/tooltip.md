## Tooltip 文字提示

常用于展示鼠标 hover 时的提示信息。

### 基础用法

在这里我们提供 9 种不同方向的展示方式，可以通过以下完整示例来理解，选择你要的效果。

:::demo 使用`content`属性来决定`hover`时的提示信息。由`placement`属性决定展示效果：`placement`属性值为：`方向-对齐位置`；四个方向：`top`、`left`、`right`、`bottom`；三种对齐位置：`start`, `end`，默认为空。如`placement="left-end"`，则提示信息出现在目标元素的左侧，且提示信息的底部与目标元素的底部对齐。

```html
<div class="box">
  <div class="top">
    <el-tooltip class="item" effect="dark" placement="top-start">
      <template slot="content">
        1. 本次《機甲變變變》事前登錄抽獎活動（「抽獎活動」）的開始/結束日期（「活動期」）2025年6月13日至2025年7月2日。 本抽獎活動的主辦方是悟空數位行銷（「主辦方」）。通過參加抽獎活動，每個參與者將無條件接受並同意遵守這些官方規則及主辦方的決定，這些決定為最終決定並在各個方面均具有約束力。主辦方負責參與者的收集、提交或處理以及抽獎活動的整體管理。參與者應將其與抽獎活動有關的任何問題、意見或問題與主辦方聯繫。在活動期間，可以通過電子郵件發送至主辦方電子郵件信箱地址[monstergo1113@gmail.com]與主辦方聯繫。

        2. 資格：本抽獎活動向所有合格地點的自然人開放，您需為合法居民並根據當地法律被歸類為成年人（「參與者」或「您」）。主辦方及其子公司、關聯公司、分銷商、零售商、銷售代表、高級管理人員、董事和職員以及參與抽獎活動管理或履行的任何實體，均無資格參加本次抽獎活動或贏得獎勵。前述這些人的直系親屬也無資格參加本次抽獎活動或贏得獎勵。 本抽獎活動受所有可適用的法律法規約束，若法律禁止或限制時無效。

        3. 獎項：
        大獎：四名（4）獲獎者將各獲得一部[iPhone 16 (256GB)]（大約零售價或其相近值(ARV)：1100 美元）
        大獎：十名（10）獲獎者將各獲得一個[Airpods Pro(第三代）] （大約零售價或其相近值(ARV)：250 美元）
        大獎：十名（10）獲獎者將獲得以下其中一種[App Store 和 iTunes 禮品卡，Google Play 禮品卡，MYCARD儲值卡]（大約零售價或其相近值(ARV)：50 美元）
        獎品不能轉讓、兌換現金或替換。獎項的大約零售價代表主辦方的誠信和決心。該決定為最終決定，具有約束力，且無法申訴。如果獎品的實際價值小於規定的大約零售價，則差額將不以現金獎勵。主辦方不對任何獎項的外觀、安全性或性能作出任何陳述或保證。主辦方將不會更換任何丟失或被盜的獎品。 此抽獎活動向符合資格的地點的合法居民開放，並且僅將獎品授予和/或交付予符合資格的地點。所有適用的稅費、附加費均由獲獎者自行承擔。不遵守官方規則將被沒收獎品。
      </template>
      <el-button>上左</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" content="Top Center 提示文字" placement="top">
      <el-button>上边</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" content="Top Right 提示文字" placement="top-end">
      <el-button>上右</el-button>
    </el-tooltip>
  </div>
  <div class="left">
    <el-tooltip class="item" effect="dark" content="Left Top 提示文字" placement="left-start">
      <el-button>左上</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" placement="left" max-width="50vw" max-height="50vh">
      <template slot="content">
        https://p.applov.in/playablePreview?create=1&qr=112847381247982374&a=playablePreviewplayablePreviewplayablePreviewplayablePreview
        1. 本次《機甲變變變》事前登錄抽獎活動（「抽獎活動」）的開始/結束日期（「活動期」）2025年6月13日至2025年7月2日。 本抽獎活動的主辦方是悟空數位行銷（「主辦方」）。通過參加抽獎活動，每個參與者將無條件接受並同意遵守這些官方規則及主辦方的決定，這些決定為最終決定並在各個方面均具有約束力。主辦方負責參與者的收集、提交或處理以及抽獎活動的整體管理。參與者應將其與抽獎活動有關的任何問題、意見或問題與主辦方聯繫。在活動期間，可以通過電子郵件發送至主辦方電子郵件信箱地址[monstergo1113@gmail.com]與主辦方聯繫。

        2. 資格：本抽獎活動向所有合格地點的自然人開放，您需為合法居民並根據當地法律被歸類為成年人（「參與者」或「您」）。主辦方及其子公司、關聯公司、分銷商、零售商、銷售代表、高級管理人員、董事和職員以及參與抽獎活動管理或履行的任何實體，均無資格參加本次抽獎活動或贏得獎勵。前述這些人的直系親屬也無資格參加本次抽獎活動或贏得獎勵。 本抽獎活動受所有可適用的法律法規約束，若法律禁止或限制時無效。

        3. 獎項：
        大獎：四名（4）獲獎者將各獲得一部[iPhone 16 (256GB)]（大約零售價或其相近值(ARV)：1100 美元）
        大獎：十名（10）獲獎者將各獲得一個[Airpods Pro(第三代）] （大約零售價或其相近值(ARV)：250 美元）
        大獎：十名（10）獲獎者將獲得以下其中一種[App Store 和 iTunes 禮品卡，Google Play 禮品卡，MYCARD儲值卡]（大約零售價或其相近值(ARV)：50 美元）
        獎品不能轉讓、兌換現金或替換。獎項的大約零售價代表主辦方的誠信和決心。該決定為最終決定，具有約束力，且無法申訴。如果獎品的實際價值小於規定的大約零售價，則差額將不以現金獎勵。主辦方不對任何獎項的外觀、安全性或性能作出任何陳述或保證。主辦方將不會更換任何丟失或被盜的獎品。 此抽獎活動向符合資格的地點的合法居民開放，並且僅將獎品授予和/或交付予符合資格的地點。所有適用的稅費、附加費均由獲獎者自行承擔。不遵守官方規則將被沒收獎品。
        4. 通過以下兩個方法皆可獲得參與資格（若同時完成以下兩個步驟，將提高您的中獎概率）：
        1）在此活動頁跳轉至蘋果或谷歌商店完成商店預約
        2）於活動期間在此活動頁使用您的手機號碼完成《機甲變變變》預約，同時完成好友邀請註冊流程。允許每人以一個手機號碼參與抽獎活動。個人或組織送出的自動程式或類似程式將被取消參賽資格。網路入口必須由參與者直接進入。參與者通過使用多個/不同的手機號碼、身分、註冊、登入名或任何其他方法來取得超過指定數量的參賽資格，任何該類嘗試都將使參賽資格無效，且該參與者可能會被取消參賽資格。授予任何獎項的最終資格必須經過官方資格驗證。主辦方明確告知的時區時間將是本次抽獎活動的官方計時器。

        5. 獲獎者選擇：抽獎活動的獲獎者將從整個活動期內收到的所有合格參與者中隨機抽取。 隨機抽獎將由主辦方進行。獲勝的機率將取決於活動期間確認的合格參與者人數。

        6. 獲獎者通知：抽獎後大約在通知時間框架內，通過事前登錄過程中使用的手機號碼通知獲獎者。潛在獲勝者必須在通知的接受時間內按照主辦方的指示操作以接受獎品。 如果主辦方在首次通知後的五（5）個自然日內無法與[任何]潛在獲獎者聯繫，或有任何獎品或獎品通知顯示無法送達被退回，或[任何]潛在獲獎者拒絕了他的獎品或不遵守抽獎規則和要求，則該獎品將被沒收，此獎項作廢。一旦沒收獎品，將不予賠償。 潛在獲獎者可能需要簽署並回傳資格證明、責任豁免書及資訊公佈同意書（統稱為「獎品獲取文件」）。除主辦方外，不允許替代或轉移獎品。

        7. 隱私：主辦方將根據其隱私權政策收集網路上活動參與者個人資料，請點擊此處主辦方的隱私權政策。通過參加抽獎活動，參與者視同同意主辦方收集和使用其個人資料，並同意已經閱讀並接受了主辦方的隱權政策。此外，參與抽獎活動即表示您授予主辦方與其他抽獎活動實體分享您的手機號碼和任何其他個人身份資訊的權限，以進行管理和兌現獎金，包括在公開的獲獎者名單中使用以公佈獲獎資訊。

        8. 責任限制：通過參加本次抽獎活動，參與者和獲勝者同意豁免並使得主辦方及其廣告和促銷機構及其母公司、子公司、關聯公司、合作夥伴、代表、代理商、繼任者、受讓人、雇 員、官員和董事（統稱「豁免實體」），對與以下情況有關的損失、傷害、損害、成本或費用 （包括但不限於財產損失、人身傷害和/或死亡）承擔全部責任：準備抽獎或參與抽獎，擁有、接受和/或使用獎品或參與任何抽獎相關的活動，以及基於宣傳、誹謗或侵犯隱私和商品交付的任何索賠。
      </template>
      <el-button>左边</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" content="Left Bottom 提示文字" placement="left-end">
      <el-button>左下</el-button>
    </el-tooltip>
  </div>

  <div class="right">
    <el-tooltip class="item" effect="dark" content="Right Top 提示文字" placement="right-start">
      <el-button>右上</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" content="Right Center 提示文字" placement="right">
      <el-button>右边</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="light" placement="right-end">
      <template slot="content">
        1. 本次《機甲變變變》事前登錄抽獎活動（「抽獎活動」）的開始/結束日期（「活動期」）2025年6月13日至2025年7月2日。 本抽獎活動的主辦方是悟空數位行銷（「主辦方」）。通過參加抽獎活動，每個參與者將無條件接受並同意遵守這些官方規則及主辦方的決定，這些決定為最終決定並在各個方面均具有約束力。主辦方負責參與者的收集、提交或處理以及抽獎活動的整體管理。參與者應將其與抽獎活動有關的任何問題、意見或問題與主辦方聯繫。在活動期間，可以通過電子郵件發送至主辦方電子郵件信箱地址[monstergo1113@gmail.com]與主辦方聯繫。

        2. 資格：本抽獎活動向所有合格地點的自然人開放，您需為合法居民並根據當地法律被歸類為成年人（「參與者」或「您」）。主辦方及其子公司、關聯公司、分銷商、零售商、銷售代表、高級管理人員、董事和職員以及參與抽獎活動管理或履行的任何實體，均無資格參加本次抽獎活動或贏得獎勵。前述這些人的直系親屬也無資格參加本次抽獎活動或贏得獎勵。 本抽獎活動受所有可適用的法律法規約束，若法律禁止或限制時無效。

        3. 獎項：
        大獎：四名（4）獲獎者將各獲得一部[iPhone 16 (256GB)]（大約零售價或其相近值(ARV)：1100 美元）
        大獎：十名（10）獲獎者將各獲得一個[Airpods Pro(第三代）] （大約零售價或其相近值(ARV)：250 美元）
        大獎：十名（10）獲獎者將獲得以下其中一種[App Store 和 iTunes 禮品卡，Google Play 禮品卡，MYCARD儲值卡]（大約零售價或其相近值(ARV)：50 美元）
        獎品不能轉讓、兌換現金或替換。獎項的大約零售價代表主辦方的誠信和決心。該決定為最終決定，具有約束力，且無法申訴。如果獎品的實際價值小於規定的大約零售價，則差額將不以現金獎勵。主辦方不對任何獎項的外觀、安全性或性能作出任何陳述或保證。主辦方將不會更換任何丟失或被盜的獎品。 此抽獎活動向符合資格的地點的合法居民開放，並且僅將獎品授予和/或交付予符合資格的地點。所有適用的稅費、附加費均由獲獎者自行承擔。不遵守官方規則將被沒收獎品。
      </template>
      <el-button>右下</el-button>
    </el-tooltip>
  </div>
  <div class="bottom">
    <el-tooltip class="item" effect="dark" content="Bottom Left 提示文字" placement="bottom-start">
      <el-button>下左</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" content="Bottom Center 提示文字" placement="bottom">
      <el-button>下边</el-button>
    </el-tooltip>
    <el-tooltip class="item" effect="dark" content="Bottom Right 提示文字" placement="bottom-end">
      <el-button>下右</el-button>
    </el-tooltip>
  </div>
</div>

<style>
  .box {
    width: 400px;

    .top {
      text-align: center;
    }

    .left {
      float: left;
      width: 60px;
    }

    .right {
      float: right;
      width: 60px;
    }

    .bottom {
      clear: both;
      text-align: center;
    }

    .item {
      margin: 4px;
    }

    .left .el-tooltip__popper,
    .right .el-tooltip__popper {
      padding: 8px 10px;
    }
  }
</style>
```
:::

### 主题

Tooltip 组件提供了两个不同的主题：`dark`和`light`。


:::demo 通过设置`effect`属性来改变主题，默认为`dark`。
```html
<el-tooltip content="Top center" placement="top">
  <el-button>Dark</el-button>
</el-tooltip>
<el-tooltip content="Bottom center" placement="bottom" effect="light">
  <el-button>Light</el-button>
</el-tooltip>
```
:::

### 更多 Content

展示多行文本或者是设置文本内容的格式

:::demo 用具名 slot 分发`content`，替代`tooltip`中的`content`属性。
```html
<el-tooltip placement="top">
  <div slot="content">多行信息<br/>第二行信息</div>
  <el-button>Top center</el-button>
</el-tooltip>
```
:::

### 高级扩展

除了这些基本设置外，还有一些属性可以让使用者更好的定制自己的效果：

`transition` 属性可以定制显隐的动画效果，默认为`fade-in-linear`。
如果需要关闭 `tooltip` 功能，`disabled` 属性可以满足这个需求，它接受一个`Boolean`，设置为`true`即可。

事实上，这是基于 [Vue-popper](https://github.com/element-component/vue-popper) 的扩展，你可以自定义任意 Vue-popper 中允许定义的字段。
当然 Tooltip 组件实际上十分强大，文末的API文档会做一一说明。

:::demo
```html
<template>
  <el-tooltip :disabled="disabled" content="点击关闭 tooltip 功能" placement="bottom" effect="light">
    <el-button @click="disabled = !disabled">点击{{disabled ? '开启' : '关闭'}} tooltip 功能</el-button>
  </el-tooltip>
</template>
<script>
  export default {
    data() {
      return {
        disabled: false
      };
    }
  };
</script>
```
:::

:::tip
tooltip 内不支持 `router-link` 组件，请使用 `vm.$router.push` 代替。

tooltip 内不支持 disabled form 元素，参考[MDN](https://developer.mozilla.org/en-US/docs/Web/Events/mouseenter)，请在 disabled form 元素外层添加一层包裹元素。
:::

### Attributes
| 参数               | 说明                                                     | 类型              | 可选值      | 默认值 |
|--------------------|----------------------------------------------------------|-------------------|-------------|--------|
|  effect        |  默认提供的主题  | String            | dark/light | dark  |
|  content        |  显示的内容，也可以通过 `slot#content` 传入 DOM  | String            | — | — |
|  placement        |  Tooltip 的出现位置  | String           |  top/top-start/top-end/bottom/bottom-start/bottom-end/left/left-start/left-end/right/right-start/right-end |  bottom |
|  value / v-model |  状态是否可见  | Boolean           | — |  false |
|  disabled       |  Tooltip 是否可用  | Boolean           | — |  false |
|  offset        |  出现位置的偏移量  | Number           | — |  0 |
|  transition     |  定义渐变动画      | String             | — | el-fade-in-linear |
|  visible-arrow   |  是否显示 Tooltip 箭头，更多参数可见[Vue-popper](https://github.com/element-component/vue-popper) | Boolean | — | true |
|  popper-options        | [popper.js](https://popper.js.org/documentation.html) 的参数 | Object            | 参考 [popper.js](https://popper.js.org/documentation.html) 文档 | { boundariesElement: 'body', gpuAcceleration: false } |
| open-delay | 延迟出现，单位毫秒 | Number | — | 0 |
| manual | 手动控制模式，设置为 true 后，mouseenter 和 mouseleave 事件将不会生效 | Boolean | — | false |
| popper-class | 为 Tooltip 的 popper 添加类名 | String | — | — |
| enterable | 鼠标是否可进入到 tooltip 中 | Boolean | — | true |
| hide-after | Tooltip 出现后自动隐藏延时，单位毫秒，为 0 则不会自动隐藏 | number | — | 0 |
| tabindex   | Tooltip 组件的 [tabindex](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex) | number | — | 0 |
