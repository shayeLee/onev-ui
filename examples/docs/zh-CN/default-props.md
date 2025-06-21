## 全局组件props定义



### 使用 


```javascript
import OnevUi from 'onev-ui';
import Vue from 'vue'
Vue.use(OnevUi,{
  defaultProps:{
    ElButton:{
      type:'primary'
    },
    ElInput:{
      size:'mini'
    }  
  }
})
```
