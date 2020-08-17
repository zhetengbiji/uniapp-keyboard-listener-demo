# uniapp-keyboard-listener

uni-app 全局键盘事件监听。

支持App端和H5端，一般用于监听硬件设备（键盘、扫描枪）键盘事件。

## 使用方式

### NPM

```
npm i uniapp-keyboard-listener --save
```

```js
import keyboardListener from 'image-tools'
export default {
  components: {
    keyboardListener
  }
}
```

### 直接下载

```js
// 以下路径需根据项目实际情况填写
import keyboardListener from '../../components/keyboard-listener'
export default {
  components: {
    keyboardListener
  }
}
```

## 事件

事件对象基本和浏览器事件 [KeyboardEvent](https://developer.mozilla.org/zh-CN/docs/Web/API/KeyboardEvent) 一致

### keydown

监听按键按下事件

```html
<keyboard-listener @keydown="onKeydown"></keyboard-listener>
```

### keyup

按键松开事件

```html
<keyboard-listener @keyup="onKeyup"></keyboard-listener>
```

## 提示

* 移动端软键盘无法判断具体按键（仅可判断 Enter 等）
* 示例工程 [uniapp-keyboard-listener-demo](https://github.com/zhetengbiji/uniapp-keyboard-listener-demo/tree/master/test/uniapp-keyboard-listener-demo) 需要先安装 NPM 依赖。