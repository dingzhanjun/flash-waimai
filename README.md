# flash-waimai
- 一个简单的外卖系统，包括手机端，后台管理，api
- 基于spring boot和vue的前后端分离的外卖系统
- 包含手机端，后台管理功能
- 本项目主要供交流学习，不建议商用。
## 技术选型
- 核心框架：Spring Boot
- 数据库层：Spring data jpa/Spring data mongodb
- 数据库连接池：Druid
- 缓存：Ehcache
- 前端：Vue.js
- 数据库：mysql5.5以上,Mongodb建议4.0(不要使用4.2及其已上版本，否则有部分api需要自行调整)

## 模块
- flash-waimai-mobile 手机端站点
- flash-waimai-manage后台管理系统
- flash-waimai-api java接口服务
- flash-waimai-core 底层核心模块
- flash-waimai-generate 代码生成模块

## 快速开始
- 数据存储采用了mysql和mongodb，其中基础管理配置功能数据使用mysql，业务数据使用mongodb存储。
- 创建mysql数据库
```sql
    CREATE DATABASE IF NOT EXISTS waimai DEFAULT CHARSET utf8 COLLATE utf8_general_ci; 
    CREATE USER 'waimai'@'%' IDENTIFIED BY 'waiMAI@123';
    GRANT ALL privileges ON waimai.* TO 'waimai'@'%';
    flush privileges;
```
- mysql数据库创建好了之后，启动flash-waimai-api服务，会自动初始化数据，无需开发人员自己手动初始化数据
- 安装mongodb并创建数据库:flash-waimai
使用mongorestore命令  导入mongodb数据,由于测试数据量较大，打包放在了百度云盘：链接：https://pan.baidu.com/s/1lOvhN1-Y1M0-FZAwGHus7Q  提取码：4qz7 。下载后将文件解压到d:\\elm，如下命令导入数据：
                                              
```
mongorestore.exe -d flash-waimai d:\\elm
```
- 下载项目测试数据的图片（商家和食品图片）： 链接：https://pan.baidu.com/s/15uiA8hUCwdZv6Bycn1y_yg 提取码：cvas   ，将图片存放到t_sys_cfg表中system.file.upload.path配置的目录下
- 启动api服务：
    - 进入flash-waimai-api模块
    - 直接运行ApiApplication主类启动api服务
- 启动管理平台:
    - 进入flash-waimai-manage目录：
    - 运行 npm install --registry=https://registry.npmmirror.com
    - 运行npm run dev
    - 启动成功后访问 http://localhost:9528 ,登录，用户名密码:admin/admin
- 启动手机端:
    - 进入flash-waimai-mobile目录：    
    - 运行 npm install --registry=https://registry.npmmirror.com
    - 运行npm run dev
    - 启动成功后访问 http://localhost:8000

## 运行效果图
- 后台管理
![admin](doc/admin.gif)
- 手机端    
![mobile](doc/mobile.gif)

## 在线演示
- 查看演示系统请不要随意删除数据
- 后台管理：[http://waimai-admin.microapp.store](http://waimai-admin.microapp.store)
- 手机端:[http://waimai-mobile.microapp.store](http://waimai-mobile.microapp.store)

## 文档
[https://microapp.gitee.io/flash-waimai](https://microapp.gitee.io/flash-waimai)
## 开发进度
- flash-waimai-manage [初步完成]
- flash-waimai-mobile[完善中]

## 鸣谢
- 感谢[bailicangdu](https://github.com/bailicangdu),[enilu](https://github.com/enilu),本项目参考参考借鉴了[vue2-elm](https://github.com/bailicangdu/vue2-elm)，[web-flash](https://github.com/enilu/web-flash)，[vue2-manage](https://github.com/bailicangdu/vue2-manage)
- 该项目克隆并扩展自[web-flash](https://github.com/enilu/web-flash),所以开发的时候多看看web-flash的[在线文档](http://enilu.gitee.io/web-flash)
- 该项目不适用与商城系统解决方案，如果有商城系统需求，可以查看另外一个商城的开源系统[https://gitee.com/microapp/linjiashop](https://gitee.com/microapp/linjiashop)(支持H5,微信小程序,APP)

## 交流
- qq群仅为方便网友互相交流，作者基本不会在群里回复，如果需要跟作者提问题，可以通过项目主页提issue；qq群禁止发广告，发者立删;为了提高加群门槛，请先通过下面链接打赏后加项目作者qq，并将打赏截图发过去，作者将邀请你进群，[打赏链接](https://microapp.gitee.io/flash-waimai/donate.html),打赏金额随缘


