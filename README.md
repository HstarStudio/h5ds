# **简介** 

- H5DS (HTML5 Design software) 这是一款基于WEB的 H5制作工具。让不会写代码的人也能轻松快速上手制作H5页面。
- H5DS 官方 Git (https://gitee.com/676015863/H5DS) ，简体中文 UTF8 版本，其他版本请自行转码
- h5ds 官方站：http://www.h5ds.com

![img](build/assets/images/demo.png)

# **声明**

您可以下载本站代码，但未经许可 **禁止** 在本产品的整体或任何部分基础上以发展任何派生版本、修改版本或第三方版本用于 **重新分发** ,您可以下载源码进行学习或者用于企业推广运营使用而无需支付任何费用，在未获得成都飞酷网络的书面授权之前，不能将该工具内嵌到其他项目中，也不能将该工具提供给自身的客户或者第三方客户使用，您若有违反规定，成都飞酷网络科技有限公司有权随时中止或终止您对成都飞酷网络产品的使用资格并保留追究相关法律责任的权利

# **相关网站**
 
- h5ds 官方站：http://www.h5ds.com

# **技术交流群**

[QQ群 549856478](https://jq.qq.com/?_wv=1027&k=5I0kPBX)

# **友情提示**

若有BUG，请及时issues我们，会第一时间做修改！

# **安装使用说明**

运行环境 node v6.x mysql v5.6

1. 新建数据库h5ds，导入数据 h5ds.sql，进入目录 `server-site/src/config.js` 修改数据库配置
2. 进行目录 `core` 执行 `npm i`, `npm run dev` 来启动 h5ds JS 开发打包
3. 进入目录 `server-site` 执行 `npm i`, `npm run dev` 启动服务端站点
4. 浏览器输入：http://localhost:8090 即可访问

实现原理：

1. 在 `core` 目录中，执行 `npm run dev` 将会利用 `webpack` 把相关资源打包到 `core/dist` 目录下，并监控源代码变更，自动重新打包。
2. 在 `server-site` 中执行 `npm run dev` 会将所有服务端代码拷贝到 `server-site/dist` 目录下，并利用 `gulp` 在 `server-site/dist` 下启动服务，同时会把 `core/dist` 下的资源拷贝到 `server-site/dist/assets` 下，作为一个项目进行运行。


# 使用Docker镜像

```bash
# 通过环境变量设置DB信息和监听端口
DB_HOST # 数据库地址
DB_PORT # 数据库端口
DB_NAME # 数据库名称
DB_USER # 数据库账户名
DB_PASSWORD # 数据库密码
PORT # 程序监听端口

# 根据镜像启动容器
docker run --name h5ds  -p 8090:8090 -e DB_HOST=localhost -e DB_PORT=3306 -e DB_NAME=h5ds -e DB_USER=root -e DB_PASSWORD=123456 -e PORT=8090 hstarorg/h5ds:0.0.1
```


# **更新说明**

#### 2017-11-06

1. 修改了切换弹窗，浮动，正常页面时候的对象变更BUG
2. 添加了PC页面的支持。切换幻灯片效果
3. 换了二维码生成插件，支持更多参数设置

#### 2017-11-03

1. 修改了UC，IOS, X5内核的动画兼容性问题
2. 调整了目录结构，做到了完全前后端分离
3. 添加了postcss 做css的代码兼容处理
4. 新建了dev/app目录，存放app所需js，且对JS进行了模块化处理
5. 请更新后，npm install 重新安装依赖，再启动项目

#### 2017-10-18

1. github 和 oschina 数据同步
2. 修改了PC端页面的兼容问题

#### 2017-10-14 更新记录

1. 修改了page的继承方式
2. 添加了弹窗功能 
3. 添加了浮动层功能 
4. 添加了多种事件支持 
5. 添加了组的多选功能 
6. 扩展了SVG，MAP功能，需要付费开通 
7. 加入了sequelize 
8. 重新组织了服务端的代码 
9. 编辑器的HTML模板全部采用模块化载入，不继续在webpack中配置 
10. 修改了很多地方的BUG
11. 添加了长页支持

#### 2017-09-07 更新记录

1. 修改了复制粘贴的BUG。
2. 添加了多交互的支持

#### 2017-09-06 更新记录

1. 小动了下架构，新增PageClass 类，用于被其他类继承。
2. 添加了自定义弹窗功能
3. 添加了自定义浮动层功能
4. 添加了显示隐藏的交互
5. 添加了页面自定义ID的功能
