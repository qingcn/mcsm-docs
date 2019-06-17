## FTP 服务
-----------
FTP 模块采用被动传输模式，传输命令默认使用 `10022`(可更改) 端口；

传输数据需要一个端口段，默认是 `20010` - `20100`；

为确保 FTP 服务正常使用，请配置好您的防火墙设置，对这些端口范围进行开放。

> 当然，我们提供了在线文件管理功能，您大可不必完全使用 FTP。
## 反向代理 与 SSL
-----------

尽管默认没有 Https ，您可能在公共网络下不太放心，但是我们不传递明文的密码，可以保证你的账号的密码是难以泄露的。

具体密码传递过程可参考 [单击这里跳转](https://github.com/Suwings/MCSManager/wiki/%E7%99%BB%E5%BD%95%E5%AF%86%E7%A0%81%E4%BC%A0%E9%80%92%E8%BF%87%E7%A8%8B%E5%9B%BE)
-----------
## 实现 HTTPS 与 WSS

打开前端 URL 定位文件 `public/common/URL.js`, 将 http 与 ws 改成 https 与 wss；

可保证前端所有请求均为 https 和 wss
> 此文件不会与 github 版本冲突，更新时也不会覆盖，请放心修改。
-----------
## 反向代理

后端请通过反向代理完成，或自行修改 Express 初始化 App。

> 注意: [Nginx 反向代理注意](https://github.com/Suwings/MCSManager/issues/22)  | [Apache 反向代理注意](https://github.com/Suwings/MCSManager/issues/34)
-----------
## 浏览器兼容性

- `ECMAScript 5` 标准
- `IE 10+` `Chrome` `Firefox` `Safari` `Opera` 等现代主流浏览器

> 例外: 文件在线管理界面需要 `IE 11+` 