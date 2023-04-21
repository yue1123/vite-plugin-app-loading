# vite-plugin-spa-loading

![npm](https://img.shields.io/npm/v/vite-plugin-spa-loading?style=flat-square)
![npm](https://img.shields.io/npm/dm/vite-plugin-spa-loading?style=flat-square)
![GitHub](https://img.shields.io/github/license/yue1123/vite-plugin-spa-loading?style=flat-square)

[简体中文](./README.zh.md)

Out of the box spa application first screen loading placeholder plugin, avoid long time white screen before app launch.

## 📦 Install

```shell
npm i vite-plugin-spa-loading -D

# yarn
yarn add vite-plugin-spa-loading -D

# pnpm
pnpm add vite-plugin-spa-loading -D
```

## 🦄 Usage

Add spaLoading plugin to vite.config.js / vite.config.ts and configure it:

```ts
// vite.config.js / vite.config.ts
import { spaLoading } from 'vite-plugin-spa-loading'

export default {
  plugins: [spaLoading()]
}
```

## Overview

### text loading placeholder

```ts
import { spaLoading } from 'vite-plugin-spa-loading'

export default {
  plugins: [
    spaLoading('text', {
      tipText: 'The loading text...'
    })
  ]
}
```

### svg loading placeholder

```ts
import { spaLoading } from 'vite-plugin-spa-loading'

export default {
  plugins: [
    spaLoading('svg', {
      path: 'xxx/loading.svg'
      // or
      // content: '<svg>....</svg>'
    })
  ]
}
```

### img loading placeholder

```ts
import { spaLoading } from 'vite-plugin-spa-loading'

export default {
  plugins: [
    spaLoading('img', {
      src: 'xxx/loading.gif'
    })
  ]
}
```

## API

### BaseOptions

| 属性名        | 类型     | 描述                                             | 默认值       |
| ------------- | -------- | ------------------------------------------------ | ------------ |
| rootElementId | string   | app 挂载元素的 ID                                | -            |
| devEnable     | boolean  | 是否开启开发环境                                 | false        |
| css           | string   | 自定义 CSS 样式                                  | -            |
| cssPath       | string   | 外部 CSS 文件路径                                | -            |
| tipText       | string   | 加载占位符的提示文本                             | "Loading..." |
| debounce      | number   | 防抖时长，避免在网络较好的情况下出现加载动画闪烁 | -            |
| error.tip     | string   | 错误提示文本                                     | -            |
| error.detail  | boolean  | 是否显示错误详情                                 | -            |
| error.handler | Function | 错误处理函数，接收一个字符串数组作为参数         | -            |

### Image

`Image` 接口继承自 `BaseOptions`，添加了以下属性：

| 属性名 | 类型   | 描述                         | 默认值 |
| ------ | ------ | ---------------------------- | ------ |
| src    | string | 图片文件路径或 base64 字符串 | -      |

### Svg

`Svg` 接口继承自 `BaseOptions`，添加了以下属性：

| 属性名  | 类型   | 描述           | 默认值 |
| ------- | ------ | -------------- | ------ |
| content | string | SVG 内容字符串 | -      |

或者

| 属性名 | 类型   | 描述         | 默认值 |
| ------ | ------ | ------------ | ------ |
| path   | string | SVG 文件路径 | -      |

## License

[MIT licenses](https://opensource.org/licenses/MIT)