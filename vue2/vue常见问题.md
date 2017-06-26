###vue中出现变量闪烁问题
    <style type="text/css">
          [v-cloak] { display: none }
    </style>
    <div v-cloak>{{message}}</div>
    
    
###axios跨域访问js端配置
    axios({
        method:'post',
        url:'请求地址',
        data:{
            param:'参数'
        },
          headers: {
                'Content-Type': 'application/x-www-form-urlencoded',//添加header声明 防止出现跨域
          }
    }).then(function(res){
        return res.data;
    });
[axios官网github](https://github.com/mzabriskie/axios)