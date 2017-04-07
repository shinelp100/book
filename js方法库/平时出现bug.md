###平时遇到的bug
   
   // iPhone7 中遇到的无痕浏览的sessionStrage、localstrage的兼容性问题
   ```
   if (typeof sessionStorage === 'object') {
              try {//catch语句中包含要执行的语句，当try语句中抛出错误时。也就是，你想让try语句中的内容成功， 如果没成功，你想控制接下来发生的事情，这时你可以在catch语句中实现
                  sessionStorage.setItem("key","value");
              } catch (e) {
                  Storage.prototype._setItem = Storage.prototype.setItem;
                  Storage.prototype.setItem = function() {};
              }
          }
   ```
   
   
###iscroll控制页面不滑动

```
    function eventTarget(event) {
        event.preventDefault();
    };
    $('body').bind('touchmove',eventTarget,false);
    $('body').unbind('touchmove');
    
    var initScroll = function () {
        var myScroll;
        intervalTime = setInterval(function () {
            var resultContentH = $("#giftBox ul").height();
            if (resultContentH > 0) {  //判断数据加载完成的条件
                clearInterval(intervalTime);
                myScroll = new iScroll('giftBox',{
                    vScrollbar:false
                });
            }
        }, 1);
    }
```



###获取页面所有的节点及其数量

    document.getElementsByTagName('*')
    document.getElementsByTagName('*').length