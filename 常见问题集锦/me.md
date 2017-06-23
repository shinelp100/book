###获取页面加载完成后出发callback
```
   document.onreadystatechange = dosomething
   function dosomething(){
    if(document.readyState == 'complete'){
        callback();
      }
   }
```

.clearfix:after {  
    content: "";  
    display: block;  
    clear: both;  
    visibility: hidden;  
    font-size: 0;  
    height: 0;  
}  

overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 3;


//数字字母不折行问题（默认认为他们是一个单词 一个整体）
word-wrap: break-word;


    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;



<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0,minimum-scale=1.0, user-scalable=0">

-webkit-tap-highlight-color：transparent

window.location.href = window.location.href +"?v="+ Math.random()*10;微信刷新页面


/*对于弹框的fixed定位问题兼容写法*/
        .pomp {
            width:**;
            height:**;
            position: fixed;
            top:50%;
            left:50%;
            transform: translate(-50% ,-50%);
            -webkit-transform: translate(-50% ,-50%);
            -moz-transform: translate(-50% ,-50%);
        }

//微信后加类时间戳
if(location.href.indexOf('?') == -1){
                window.location.href = window.location.href +"?v="+ Math.random()*10;
            } else {
                window.location.href = window.location.href +"&v="+ Math.random()*10;
            }

//php代码在head中插入想要的
<?php $this->beginBlock('blockhead') ?>

<meta name="viewport" content="initial-scale=1, maximum-scale=1, minimum-scale=1, user-scalable=no">
<?php $this->endBlock() ?>


this.investment=this.investment.replace(/\D/g,"");


viewPoint高度：vh（  $(‘div’).height( $(window).height()  ）/宽度：vm


页面不缓存
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Cache-Control" content="no-cache">
<meta http-equiv="Expires" content="-1">


手机横竖屏
    window.onorientationchange = function(){
    switch(window.orientation){
    case -90:
    case 90:
    alert("横屏:" + window.orientation);
    case 0:
    case 180:
    alert("竖屏:" + window.orientation);
    break;
    }
    }


####检查字符串替换value值
    function changeURLArg(url,arg,arg_val){
            var pattern=arg+'=([^&]*)';
            var replaceText=arg+'='+arg_val;
            if(url.match(pattern)){
                var tmp='/('+ arg+'=)([^&]*)/gi';
                tmp=url.replace(eval(tmp),replaceText);
                return tmp;
            }else{
                if(url.match('[\?]')){
                    return url+'&'+replaceText;
                }else{
                    return url+'?'+replaceText;
                }
            }
            return url+'\n'+arg+'\n'+arg_val;
        }

####竖屏时使用的样式
    @media all and (orientation:portrait) {
    .css{}
    }

####横屏时使用的样式
    @media all and (orientation:landscape) {
    .css{}
    }

<!-- 选择照片 -->
<input type=file accept="image/*">
<!-- 选择视频 -->
<input type=file accept="video/*">




改变地址栏不刷新页面：location.href.hash = "#sdfsd"  但是影响浏览器自带的返回效果



####解决placeholder在webkit中的不居中问题
    input::-webkit-input-placeholder { /* WebKit browsers */
      line-height: 1.5em;
    }


####判断浏览器客户端是否支持video标签
    
    var hasVideo = !!(document.createElement('video').canPlayType);
    
    console.log(hasVideo);

    
####判断浏览器客户端是否已安装flash插件
   
     var i_flash;
        
    if (navigator.plugins) {
            
    for (var i = 0; i < navigator.plugins.length; i++) {
                
        if (navigator.plugins[i].name.toLowerCase().indexOf("shockwave flash") >= 0) {
                   
        i_flash = true;
                }
      
          }
    
        }
      
      console.log(i_flash)


-webkit-appearance：none/statusbar  去除radio原有的样式


$clamp(myHeader, {clamp: 3});


####图片加载出错显示领一张图片 
    <img src="http://yongqing.is-programmer.com/posts/image.gif" onerror='this.src="http://yongqing.isprogrammer.com/posts/default.gif"' />


####控制返回按钮（改变地址栏状态）
    window.history.replaceState(null,null,'register-step-one.html');

####文本框只能输入文字
    onkeypress="if ((event.keyCode<48 || event.keyCode>57)) event.returnValue=false"


####文本框placeholder  颜色大小控制
    .popMiddle input::-webkit-input-placeholder { /* WebKit browsers */
        color:    #999;
    }


####文本框精致复制粘贴
    oncopy="return false;" oncut="return false;"
    onpaste="return false" 



iPhone 对于新添加的元素绑定点击事件 无效 
解决方案 ： 给新添加的元素添加cursor：pointer属性

高斯模糊 css filter: blur(3px);

git remote -v 查看远程clone分支名



微信页面修改字体大小影响页面 通过css属性：-webkit-text-size-adjust: 100%；


phpstrom 常用快捷键：
ctr+F4 关闭当前tab

phpstrom的撤销快捷键是Ctrl+Z

反撤销快捷键是：Ctrl+Shift+Z



关闭微信内置浏览器打开的页面：WeixinJSBridge.invoke('closeWindow');



####监听css3 animation 动画结束的事件：

    开始事件: webkitAnimationStart
    结束事件:  webkitAnimationEnd
    重复运动事件: webkitAnimationIteration
