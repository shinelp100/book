###webPack基础
- webpack作用：分离资源，实现缓存资源和并行加载资源
```
分离第三方库
```
####webpack概念
四个核心概念：入口(entry)、输出(output)、loader、插件(plugins)。

- 入口(entry)
```
webpack 将创建所有应用程序的依赖关系图表(dependency graph)。图表的起点被称之为入口起点(entry point)。入口起点告诉 webpack 从哪里开始，并遵循着依赖关系图表知道要打包什么。可以将您应用程序的入口起点认为是根上下文(contextual root)或 app 第一个启动文件。
```

- 输出(output)
```
将所有的资源(assets)归拢在一起后，还需要告诉 webpack 在哪里打包应用程序。webpack 的 output 属性描述了如何处理归拢在一起的代码(bundled code)。
```

- 加载器(loader)
```
webpack 的目标是，让 webpack 聚焦于项目中的所有资源(asset)，而浏览器不需要关注考虑这些（这并不意味着资源(asset)都必须打包在一起）。webpack 把每个文件(.css, .html, .scss, .jpg, etc.) 都作为模块处理。然而 webpack 只理解 JavaScript。
```
-  在更高层面，webpack 的配置有两个目标。
+  识别出(identify)应该被对应的 loader 进行转换(transform)的那些文件
+  由于进行过文件转换，所以能够将被转换的文件添加到依赖图表（并且最终添加到 bundle 中）(use 属性)


- 构建目标(Targets)
