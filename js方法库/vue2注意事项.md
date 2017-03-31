###解决在Vue项目中时常因为代码缩进导致页面报错的问题
    方法一：了解eslint-loader规则，严格按照规范书写代码（这是废话）
    
    方法二：关闭eslint
    
    如果实在普通的webpack项目中我们只需要打开webpack.config.js文件，然后去除ESlint在文件中的配置代码就可以了；
    
    如果是在vue项目中，我们需要打开项目根目录下的build文件夹并且打开该文件夹下的webpack.base.conf.js文件，然后去除ESlint在文件中的配置代码就可以了。
   
[原文链接](http://blog.csdn.net/zhu1500527791/article/details/53445277)    