###引用（reference）引用实际是指向对象实际位置的指针
```    
    引用指向永远只能是一个具体的对象，而不能使另一个引用
    EX：
        var items = new Array('one','two','three');
        var myItems = items;
        items = new Array('four','five');
        //现在items和myItems现在的指向已经发生改变；
        //items指向Array('four','five')；
        //myItems指向Array('one','two','three')；
        alert(items != myItems)
```   

###图形验证码
```
{
  "code": 0,//0成功，1失败
  "msg": "成功",
  "src": "https://www.wangcaigu.com/",
  "uuid": "dkjlcisdlasfkk=ldjasljfkd#"
}

```
###短信验证码

对应的请求参数：mobile，imgCode，uuid
```
{
  "code": 0,//0成功，1图形验证码过期失败，2其他失败
  "msg": "成功"
}
```

###完成注册

对应的请求参数：mobile，msgCode，password，src
```
{
  "code": 0,//0成功，1用户已存在失败，2登录未成功失败，3其他失败
  "msg": "成功",
}
```
###绑定邀请码
对应的请求参数：inviteCode
```
{
  "code": 0,//0成功，1失败
  "msg": "成功",
}
```