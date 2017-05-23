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
    - 告诉 webpack 这个程序的目标环境是什么
    
- 模块解析(Module Resolution)
    - resolver 是一个库(library)，用于帮助找到模块的绝对路径。一个模块可以作为另一个模块的依赖模块，然后被后者引用
    
    
    
    
    

    
    
    
    
    
    
    
    
    
    
    
    
    
    
- webpack devServer
    + 1、安装npm install --save-dev  open-browser-webpack-plugin（打开浏览器页面插件） && npm install --save-dev webpack-dev-server（安装webpack-dev-server）
    + 2、配置package.json文件："server": "webpack-dev-server"
    + 3、配置webpack.config.js文件 配置配置项和 引入插件
    + 4、npm run server;  
    
    
- webpack Watch
    + 执行webpack --watch 实现文件的实时编译
    + 或是在webpack.config.js中添加watch:true,
    watchOptions: {
            ignored: /node_modules/,(忽略node_modules对于某些系统，监听大量文件系统会导致大量的 CPU 或内存占用。这个选项可以排除一些巨大的文件夹)
            poll: 1000 //每秒检查一次变动
        },
    
    
    
- context
    + 基础目录，绝对路径，用于从配置中解析入口起点(entry point)和 loader
    
- path.resolve
    + 这些选项能设置模块如何被解析。
    
- 打包后的文件（js 、css）自动添加到html中
    + npm install --save-dev html-webpack-plugin
    
    
    
    
    
    
    
- webpack 打包后代码解析
    + 上面编译出来的代码主要包含两个部分：Runtime，模块。上半部分就是Runtime，作用是保证模块顺序加载和运行。下半部分是我们的JS代码，包裹了一个函数，也就是模块
    ```
    (function(modules) {
            // Runtime
        })([
            // 模块数组
        ])
    ```
    
    
    
    
- webpack编译less文件报错（cannot find module "less"）
    + npm install --save-dev less-loader (安装less-loader)
    + npm install less less-loader （安装less 防止node不认识less文件）
    + npm install --save-dev file-loader 
    