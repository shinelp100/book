###1.安装npm

###2.设置phpStorm中JavaScript版本
    
    file-->setting-->Languages & Frameworks-->JavaScript(JavaScript version ES6)
    
###3.通过npm在您的项目中安装Babel CLI：
    
    npm install --save-dev babel-cli
     
###4. 设置phpStorm中Babel文件监视器
   
    file-->setting-->Preferences-->Tools-->File watchers 点击+按钮，从列表中选择Babel文件监视器。
    配置图片如下：
    
###5.安装Babel preset

    npm install babel-preset-env --save-dev  （在项目中安装）  
    
    + 注意：phpstorm会出现卡死
    解决方法：强制关闭phpstorm  然后进入这个项目选则node_modules右键设置：Mark directory as --> Excluded
    
###6.添加.babelrc文件

    {
      "presets": [
        ["env", {
          "targets": {
            "browsers": ["last 2 versions", "safari >= 7"]
          }
        }]
      ]
    }
    
    
[最后配上官网地址](https://blog.jetbrains.com/webstorm/2015/05/ecmascript-6-in-webstorm-transpiling/)        
