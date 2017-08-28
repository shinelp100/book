####phaser基本结构介绍（涉及我们编译的js）

```$xslt
var game = new Phaser.Game(800, 600, Phaser.AUTO, 'phaser-example', { preload: preload, create: create, update: update, render: render });
	要使用的渲染器：phaser.auto将自动检测，phaser.webgl，phaser.canvas或phaser.headless（不提供）。
	DOM元素融入其中，这游戏画布将注射。一个DOM ID（字符串）或元素本身。
	默认状态对象。一个对象组成的相位。状态函数（预加载，创建，更新，渲染）或空。
function preload() {}//加载对象、场景...资源

function create() {}//创建对象、场景...

function update() {}//对象或是场景变化时更新更新视图

function render() {}//渲染game.debug 这些相对视口固定的信息
```

####创建对象
```$xslt
对象有很多类型比如：graphics、image、sprite、tileSprite...
game.add.obj() 对应的设置对象的宽高、位置、纹理...
```
[可创建所有对象及参数设置](https://phaser.io/docs/2.6.2/Phaser.GameObjectFactory.html)


####设置舞台背景
```$xslt
game.stage.backgroundColor = "";
...

```
[舞台背景的属性和方法](https://phaser.io/docs/2.6.2/Phaser.Stage.html)

####对于你创建的对象属性和方法的修改和调用
```$xslt
ex:
    创建的sprite对象  我们可以修改inputEnabled
    默认情况下，游戏对象不会处理任何输入事件。
    通过将inputEnabled设置为true，将创建一个Phaser.InputHandler 对于这个游戏对象，它将开始处理点击/触摸事件等等
    
    obj.events.onInputDown.add(function);添加具体的事件
```
[对应对象查找表+属性](https://phaser.io/docs/2.6.2/index)
