# yapi-plugin-cas-ah
cas登录插件，由于每家公司不一样登录，验证等接口的传参，返回参数等都会有所不同，所以大家根据自身情况去修改。
配置方法如下：

第一步： 在生成的配置文件config.json中加入如下配置：

```
"plugins": [
  {
    "name": "cas-ah",
    "options": {
      "type": "cas",
      "loginServer": "http://sso.example.com/sso/login",
      "authServer" : "https://sso.example.com/sso/serviceValidate",
      "emailPostfix": "@163.com",
    }
  }
]
```
这里面的配置项含义如下：

- type 登陆类型，目前只支持cas登陆
- loginServer 点击登陆按钮式需要跳转的url，用户通过该页面登录以后会向服务器发送一个ticket
- emailPostfix 登陆邮箱后缀
- authServer 服务端在获取ticket之后，可以通过这个url来获取用户的详细信息

第二步：在config.json 这层目录下运行 yapi plugin --name yapi-plugin-cas-ah 重新下载插件

第三步： 重启服务器
