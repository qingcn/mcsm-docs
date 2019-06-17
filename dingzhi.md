## 使用 Docker
我们支持 Docker 软件 我们使用 Docker 来进行虚拟化部署，纵使您的机器上没有 Java 任何环境，只需一个 Docker 就能轻松开启 Minecraft 服务器。

另外使用 `Docker` 也能保证您的宿主机安全性和稳定性，对 Linux 客户而言相信使用起来会更好。

如何使用？打开软件界面，单击 创建 Docker 镜像，随后在参数面板设置 `Docker` 配置 即可。

**如需使用 `Docker` ，请确保您的 Linux 系统拥有 `Docker` 环境，并且启动服务。**

我们设计得十分简单，但是如果您依然担心您不会操作，可以参考以下相关信息：

具体使用方法: [单击此处跳转](https://github.com/Suwings/MCSManager/blob/gh-pages/Question_1.md "单击此处跳转")

安装 Docker:[ 单击此处跳转](https://github.com/Suwings/MCSManager/blob/gh-pages/Question_2.md " 单击此处跳转") 

------------


## 项目目录结构
> 注意: 并不是所有目录的文件我们都建议你进行更改！

| 目录名  |  详情/解释 |
| ------------ | ------------ |
| property.js  |   控制面板配置文件|
| core/logo.txt  | 控制台输出 logo 文字  |
|  public/ |  前端所有代码，资源目录，前后端分离，使用 ws 和 ajax 通讯 |
| public/login/  |  纯 UI 逻辑登陆页面 |
| public/template/  |  前端业务模板，每个模板拥有着一个生命周期，开始与结束。 |
|  public/onlinefs_public/ | 文件在线管理模块前端所有代码  |
|  public/common/js/meum.js |   控制面板左侧菜单列表|
|  public/common/js/login.js | 通用登录流程逻辑，可重复利用在各类 HTML 登录模板  |
| server/server_core  |  Minecraft 服务端核心目录，包括服务端文件，配置，Mod，以及插件 |
|  server/x.json |  Minecraft 服务器面板配置文件 |
|  users/x.json | 控制面板用户配置文件  |
| route/  | 控制器，HTTP 请求业务逻辑层（可二次扩展）  |
|  route/websocket/ |  控制器，Webscoket 请求业务逻辑层（可二次扩展） |
|  core/Process/ |  Minecraft Server 类实现 |
| core/User/  | User 类实现  |
| core/DataModel.js   | 数据持久化模型，几乎是所有的配置的 I/O 模型  |
|  model/ | 数据持久化模型，几乎是所有的配置的 I/O 模型  |
| helper/   |  业务逻辑辅助层，用于辅助和重复利用业务逻辑 |
| ftpd/  |  FTP 独立模块，其中 ftpserver.js 已经实现了抽象 |
|  ftpServerInterface | 接口  |
| onlinefs/   | 文件管理独立模块 (Suwings/IndependentFileManager)  |


------------


##配置文件

我们的配置文件是程序目录下的 `property.js` 文件，它会在你第一次运行的时候，自动生成。

> 注意！原旧版本的 McserverConfig.json 文件完全弃用。

> 现在，所有配置将全部归纳于此文件。

> 此文件不会与 github 版本冲突，更新时也不会自动覆盖


------------



## 自定义设计

如果你是内部使用或学习用途，你可以对前端以及后端进行任何修改，包括版权声明。

> 注意！当你进行版本更新的时候，可能会覆盖掉你的自定义修改部分。

> 当然，并不是所有文件都需要覆盖一遍，也不一定非得使用新版本。

------------


## Property 文件

> 反向代理之前，你可以但不是必须阅读 `property.js` 文件

> 里面有各类的设置，包括 gzip压缩，端口和ip绑定等等。


------------



## 反向代理 与 SSL


尽管默认没有 Https ，您可能在公共网络下不太放心，但是我们不传递明文的密码，可以保证你的账号的密码是难以泄露的。

具体密码传递过程可参考 [单击这里跳转](https://github.com/Suwings/MCSManager/wiki/%E7%99%BB%E5%BD%95%E5%AF%86%E7%A0%81%E4%BC%A0%E9%80%92%E8%BF%87%E7%A8%8B%E5%9B%BE)


------------


## 用户权限系统

> 尤其注意的是，为了更加简化面板权限系统，我们只分为两种账号。

> `管理账号` 凡是以 # 字符开头的用户，均为管理账号，列如 `#master` `#admin` `#test`

> `普通账号` 不以 # 字符开头的用户，列如 `test` `usernameww` `xxx`

> 普通账号能够管理的服务器只能由管理账号来进行设定，管理账号可以管理任何服务器，并且能管理所有用户。

> 具体使用，我想你只需要运行就知道，设计的十分简单。