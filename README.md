# rjh-ui 组件库

# 文档地址

# 快速开始

#### 1.安装组件库

```sh
    npm i rjh-ui
```
#### 2.引用组件库

#### 完整引入
在 main.js 中写入以下内容：
```js
// main.js 完整引入 
import Vue from 'vue';
import 'RjhUi/lib/theme-chalk/index.css';
import RjhUi from 'rjh-ui';
Vue.use(RjhUi);
```
##### 按需引入
 首先，安装 babel-plugin-component,借助该插件，我们可以只引入需要的组件，以达到减小项目体积的目的。
```sh
npm install babel-plugin-component -D
```
然后，将 .babelrc 或 babel.config.json 文件 修改,.babelrc举例子
```JS小程序
// .babelrc
{
  "presets": [["@babel/preset-env", { "modules": false }]],
  "plugins": [
    [
      "component",
      {
        "libraryName": "rjh-ui", 
        "styleLibraryName": "theme-chalk"
      }
    ]
  ] 
}

```
babel-plugin-component的作用为编译源码如下
```js
import { Button } form 'rjh-ui'
=> // 编译成下面这种
import Button from 'rjh-ui/lib/button.js'
require('rjh-ui/lib/theme-chalk/button.css')
```

```js
// main.js 按需引入 (组件，方法，指令3种)
import Vue from 'vue';
import { Button } from 'rjh-ui';
import 'rjh-ui/lib/theme-chalk/button.css';
Vue.use(Button) // <els-countUp/>
```
