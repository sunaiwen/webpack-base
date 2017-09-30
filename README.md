## 简介

一个基于[webpack](http://webpack.js.org)的开发脚手架，帮助快速构建工程。你可以用它来**开发一个web网站**。  


## 功能

考虑到开发工程时所需要的各种功能，本工具提供：

1. 基于webpack的强大模块化工程；
2. [babel](http://babeljs.io)实时编译，随时随地**ES2015 and beyond**；
3. 集成`webpack-dev-middleware`+`webpack-hot-middleware`，实现本地http服务，开发实时预览、热加载；
4. 样式文件独立提取打包；
5. 文件打包压缩；
6. 可选的sourcemap；
7. 集成mock与proxy功能；
...


## 命令

### 开发

```shell
npm run dev
```

### 打包

```shell
npm run build
```

文件将被打包到`dist`目录下。


## 配置

配置文件为`build/setting.js`，分`dev`与`build`两部分内容：

```javascript
{
  build: {
    vendor: [],
    publicPath: './',
    sourceMap: true
  },
  dev: {
    proxyTable: {},
    mockTable: {}
  }
}
```

### build

打包相关的配置：

选项 | 含义
---- | ----
vendor | 公共模块提炼打包，如`jQuery`、`lodash`等
publicPath | 资源的发布路径，如cdn
sourceMap | 是否生成sourceMap


### dev

开发相关的配置：

选项 | 含义
---- | ----
port | http服务端口号
proxyTable | 代理配置
mockTable | 假数据配置

proxyTable参考：[proxy-middleware](https://github.com/gonzalocasas/node-proxy-middleware)

mockTable参考：[expressjs](http://www.expressjs.com.cn/4x/api.html#app.use)


### 其他

除了`build/setting.js`之外，开发者还可以手动对webpack的配置进行修改，比如添加`loader`、`plugin`等等，配置文件为`build/config.js`。




