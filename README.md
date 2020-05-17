# 纵向滚动组件

![example](https://github.com/CitizenChaos/notice-bar/blob/master/src/assets/example.gif)

## 使用说明

```shell
npm i notice-bar -S
```

```js
import noticeBar from 'notice-bar'
export default {
  components: {
    noticeBar,
  },
}
```

```html
<notice-bar />
```

## 属性说明

|     参数      |     说明     |  类型  | 默认值 |
| :-----------: | :----------: | :----: | :----: |
| noticeBarList |   消息数组   | Array  |   []   |
|     speed     | 速度（毫秒） | Number |  2000  |
|    height     |  高度（px）  | Number |   40   |
|  background   |    背景色    | String |  #fff  |
|     color     |   字体颜色   | String |  #000  |
