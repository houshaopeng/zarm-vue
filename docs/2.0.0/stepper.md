<script>
export default {
  data() {
    return {
      stepper1: 0,
      stepper2: 2,
      stepper3: 0,
      stepper4: 0,
      stepper5: 0,
      stepper6: 0,
      stepper7: 0,
      stepper8: 0,
      stepper9: 0,
      stepper10: 0,
    }
  },
  methods: {
    handleChange(event) {
      console.log(event);
    },
    handleInputChange(v) {
      console.log(v);
    }
  },
};
</script>

## 步进器 Stepper

:::demo 基本
```html
      <za-cell title="普通">
        <za-stepper slot='description' v-model='stepper1'></za-stepper>
      </za-cell>
      <za-cell title="设置默认值">
        <za-stepper slot='description' v-model='stepper2'></za-stepper>
      </za-cell>
      <za-cell title="设置上下限">
        <za-stepper slot='description' v-model='stepper3' :min='-3' :max='3'></za-stepper>
      </za-cell>
      <za-cell title="设置步长">
        <za-stepper slot='description' v-model='stepper4' :step='0.5'></za-stepper>
      </za-cell>
      <za-cell title="禁用状态">
        <za-stepper slot='description' v-model='stepper5' disabled></za-stepper>
      </za-cell>
```
:::

:::demo 多形状
```html
      <za-cell title="默认">
        <za-stepper slot='description' v-model='stepper6' theme="default"></za-stepper>
      </za-cell>
      <za-cell title="圆角">
        <za-stepper slot='description' v-model='stepper7' shape="radius"></za-stepper>
      </za-cell>
      <za-cell title="圆型">
        <za-stepper slot='description' v-model='stepper8' shape="circle"></za-stepper>
      </za-cell>
```
:::

:::demo 回调事件
```html
    <za-cell title="获取evnet事件">
      <za-stepper slot='description' v-model='stepper9' @change='handleChange'></za-stepper>
    </za-cell>
    <za-cell title="获取变化的值">
      <za-stepper slot='description'  v-model='stepper10' @inputChange='handleInputChange'></za-stepper>
    </za-cell>
```
:::


### API

#### Stepper Attributes

| 属性 | 类型 | 默认值 | 可选值／参数 | 说明 |
| :--- | :--- | :--- | :--- | :--- |
| prefixCls | string | za-stepper | | 类名前缀,自定义组件样式 |
| theme | string | 'primary' | 'default', 'primary', 'info', 'success', 'warning', 'error' | 主题 |
| shape | string | | 'radius', 'circle' | 形状 |
| v-model | number | | | 绑定值 |
| disabled | bool | false | | 是否禁用 |
| min | number | | | 最小值 |
| max | number | | | 最大值 |
| step | number | 1 | | 步长 |

#### Stepper Events
| 事件名称 | 说明 | 回调参数 |
| :--- | :--- | :--- |
| change | 点击加减后触发的事件 | event 事件对象 |
| inputChange | 点击加减后返回变化的值 | number |