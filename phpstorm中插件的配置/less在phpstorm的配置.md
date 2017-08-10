###less的全局安装

在服务器端最容易的安装方式就是通过 npm （node.js 的包管理器），方法如下：
```
$ lessc styles.less
 ```
 
###命令行用法

安装 Less 后，就可以在命令行上调用 Less 编译器了，如下：
```
$ lessc styles.less
```

这将输出编译之后的 CSS 代码到你指定的文件下：
```
$ lessc styles.less > styles.css
```


###安装less插件之 watcher-lessc

监听你指定的.less文件 或 一个文件夹（实现less的时时编译）

安装```npm install -g watcher-lessc```
指令选项
```
Options:
   --input, -i      Specify input file to watch/compile.               [required]
   --paths, -p      Specify search paths for @import directives.    [default: []]
   --compress, -c   Minify CSS output.                                           
   --filename, -f   Specify a filename, for better error messages. [default: "style.less"]
   --directory, -d  Specify input directory to watch.                            
   --output, -o     Specify output file path.                          [required]
   --help, -h       Show this message                   
```
指定.less文件指令
```
 watcher-lessc -i less/index.less -o css/inde.css
```
指定文件夹下.less文件指令
```
 watcher-lessc -i less/index.less -o css/inde.css -d ./less
```


###安装less插件之 less-plugin-functions

less缺少自定义函数，这个插件可以实现函数的自定义及返回值

安装```npm install -g less-plugin-functions```

编译指令```lessc --functions file.less```

输出指令```lessc --functions --clean-css(less输出的压缩) less/index.less css/index.css```

下面函数在less中是不编译的，EX：Demo Function
```
.function {
    .foo(@x) {
        return: @x * 2;
    }
}
```

###配置phpstrom中less自编译

phpstrom-->file-->setting-->Tools-->File Watcher-->右边蓝色的加号点开添加less文件-->配置选项

```
programe:C:\Users\伟\AppData\Roaming\npm\lessc.cmd
arguments:--no-color
          --functions(自定义函数插件)  
          --group-css-media-queries（媒体查询插件）
          --clean-css="advanced"（文件压缩插件）
          (添加安装的自定义插件)
          $FileName$
output path to refresh :$FileParentDir$/css/$FileNameWithoutExtension$.min.css: $FileParentDir$/css/$FileNameWithoutExtension$.css.map(这样配置后会在你的less文件夹对应的目录下生成css文件并且命名为.min的文件)          
```


###对于less的基础插件base.less 我们可以添加自定义的函数和方法去丰富他

EX:
```
//自定义变量如下
@blue:blue;

//计算字体大小
.fs(@size) {
  font-size: unit(@size / 75, rem);
}

//自定义函数用于计算px-->rem
.function {
  .rem(@x) {
    return: @x / 75rem;
  }
}
//自定义的媒体查询
.fs(@size) {
	font-size: 0;

	.loop(@counter) when (@counter > 0) {
		.loop ((@counter - 1));
		@mediaminwidth: extract(@screens, @counter);
		@media screen and (min-width: unit(@mediaminwidth, px)) {
			& {
				font-size: unit(ceil(@size * @mediaminwidth / 750), px);
			}
		}
	}

	.loop(length(@screens));
}
```
引入到你的less文件中：```@import "base.less""```


