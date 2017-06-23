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
    
    
    
- node安装说明
    + npm install可以一条命令同时安装多个包, 包之间用空格分隔. 包会被安装进node_modules目录中
    + --save-dev会把安装的包和版本号记录到package.json中的devDependencies对象中, 还有一个--save, 会记录到dependencies对象中, 它们的区别, 我们可以先简单的理解为打包工具和测试工具用到的包使用--save-dev存到devDependencies, 比如eslint, webpack.
    
    
- webpack 常用插件一键安装
    + npm install webpack webpack-dev-server html-webpack-plugin html-loader css-loader style-loader file-loader url-loader --save-dev
    
- webpack 支持es6（换ES2015/ES2016/ES2017到ES5, 是的, 不只ES6哦. ）
    + npm install babel-core babel-preset-env babel-loader --save-dev
    +　npm install babel-preset-es2015 --save-dev
    
- 配置favicon (webpack)



- 编译前清空dist目录
    + npm install rimraf --save-dev
    + package.json 
        ```
      {
        "scripts": {
          "build": "rimraf dist && webpack -p --env.config production"
        },
      }
        ```
        
        
- file-loader
    + file-loader的主要功能是：把源文件迁移到指定的目录（可以简单理解为从源文件目录迁移到build目录），并返回新文件的路径（简单拼接而成）。
    ```
    [ext]：文件的后缀名，示例为'jpg'。
    [name]：文件名本身，示例为'login-bg'。
    [path]：相对于当前执行webpack命令的目录的相对路径（不含文件名本身），示例为'src/public-resource/imgs/'。这个参数我感觉用处不大，除非你想把迁移后的文件放回源文件的目录或其子目录里。
    [hash]：源文件内容的hash，用于缓存解决方案。
    ```    
    
    
    
    
- 安装glob模块
    + $ npm install glob --save-dev
    + entry实际上是一个map对象，结构如下{filename:filepath}，那么我们可以根据文件名匹配，很容易构造自动扫描器：
    + npm 中有一个用于文件名匹配的 glob模块，通过glob很容易遍历出src/js目录下的所有js文件：
    


- webpack多入口文件处理
    + npm install webpack-multi-entry-resolve --save-dev
    
    
- *你也可以在一个配置文件中因为不同目的而多次使用同一个插件（Plugins）    



    