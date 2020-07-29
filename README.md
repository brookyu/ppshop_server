### PP商城，开源商城（服务端）

+ 基于开源项目NideShop重建，精简了一些功能的同时完善了一些功能，并重新设计了UI
+ 测试数据来自上述开源项目
+ 服务端api基于Ｎode.js+ThinkJS+MySQL

### 目前基于PP商城的已经上线的几款微信小程序商城
<img width="200" src="https://img.mybei.cn/mini_qr.jpg"/>

<img width="200" src="https://img.mybei.cn/WechatIMG1.png"/>


### 本项目需要配合  
微信小程序项目：GitHub: https://github.com/peizhou/ppshop-miniprogram  
管理后台项目：GitHub: https://github.com/peizhou/ppshop-admin


### 本地开发环境配置
+ 克隆项目到本地
```
git clone https://github.com/peizhou/ppshop-server
```
+ 创建数据库hiolabsDB并导入项目根目录下的init.sql  
推荐使用软件Navicat创建和管理数据库，也可以用以下命令创建：
```
CREATE SCHEMA `hiolabsDB` DEFAULT CHARACTER SET utf8mb4 ;
```
> 注意数据库字符编码为utf8mb4 
+ 更改数据库配置
  src/common/config/database.js
```
const mysql = require('think-model-mysql');

module.exports = {
    handle: mysql,
    database: 'hiolabsDB',
    prefix: 'hiolabs_',
    encoding: 'utf8mb4',
    host: '127.0.0.1',
    port: '3306',
    user: 'root',
    password: '123123', //你的密码
    dateStrings: true
};
```

+ 填写微信登录和微信支付配置和其他设置，比如七牛，阿里云快递等等

src/common/config/config.js
```
// default config
module.exports = {
  default_module: 'api',
  weixin: {
    appid: '', // 小程序 appid
    secret: '', // 小程序密钥
    mch_id: '', // 商户帐号ID
    partner_key: '', // 微信支付密钥
    notify_url: '' // 微信异步通知，例：https://www.example.com/api/pay/notify
  }
};
```

+ 安装依赖并启动
```
npm install
npm start


或者
debug:

node development.js

release:

node production.js

```
启动后，本地访问 http://127.0.0.1:8360/

### 上线需要以下准备工作： 
+ 一个微信服务公众号  
+ 阿里云服务器  
+ 注册小程序  
+ 完成认证的七牛  
+ 完成API安全设置的微信商户，并绑定好小程序id（支付）  
+ 知你客服  
+ 阿里云物流api  
+ 备案后的域名  
+ 如果卖食品，还需要《食品经营许可证》  


### 功能列表
+ 首页：搜索、Banner、公告、分类Icons、分类商品列表
+ 详情页：加入购物车、立即购买、选择规格
+ 搜索页：排序
+ 分类页：分页加载商品
+ 我的页面：订单（待付款，待发货，待收货），足迹，收货地址

### 项目截图
请参考微信小程序项目：https://github.com/peizhou/ppshop-miniprogram

### 最近更新 
- 新增生成分享图的功能  
在src/common/config/config.js需要设置好已经开通https的七牛bucket的参数
<img width="200" src="https://img.mybei.cn/wx9a9aa2c93a76d729.o6zAJs7jzc0bQEwXjBm3q8QkbgrQ.Hru44NjZKOXQb943dd2052d8b5ccdadd13483ebd9d0a.png"/>

- 项目地址  
服务端： https://github.com/peizhou/ppshop_server  
后台管理：https://github.com/peizhou/ppshop-admin  
微信小程序：https://github.com/peizhou/ppshop-miniprogram  

- 本项目会持续更新和维护，喜欢别忘了 Star，有问题可通过微信, 谢谢您的关注。
<img width="200" src="https://img.mybei.cn/contact.jpeg"/>




