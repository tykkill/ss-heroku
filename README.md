
# ss-heroku
[Heroku](https://www.heroku.com/) 是一个支持多种编程语言的云平台即服务，ss-heroku 则是可部署在 Heroku 平台的 ss 服务。
和 [shadowsocks](https://github.com/clowwindy/shadowsocks) 不同的是 ss-heroku 使用的 WebSocket 代替原本的 sockets。

## 准备

### 1. 注册 Heroku 帐号
Heroku 提供免费账号，部分介绍如下：
- 512 MB RAM per dyno
- Free apps sleep automatically after 30 mins of inactivity to conserve your dyno hours
- Free apps wake automatically when a web request is received


注册地址：https://signup.heroku.com/ （注册和部署过程需要梯子--欲取之,先予之）
## 部署
1. 点击 [![](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/Forest10/ss-heroku.git/tree/master)，[一键部署到heroku](https://heroku.com/deploy?template=https://github.com/Forest10/ss-heroku.git/tree/master)


2 . 设置 加密算法和app 密码

![deploy](http://public-img.forest10.com/ss/heroku-ss-deploy-conf.jpeg)

[](http://public-img.forest10.com/ss/heroku-ss-deploy-conf.jpeg)

支持的加密算法类型如下https://github.com/mrluanma/shadowsocks-heroku#supported-ciphers

## 启动本地 Client
1. 下载release :
* mac:http://static.forest10.com/ss/ss-h-mac.zip
* win(64):http://static.forest10.com/ss/ss-h-win64.zip

2. 修改config.json参数，运行ss-h.exe 或 start.vbs (或 [win托盘工具taskbar.exe](https://github.com/onplus/shadowsocks-heroku/issues/39))

5. 启动成功，命令行显示：`server listening at { address: '127.0.0.1', family: 'IPv4', port: 1080 }`

## 配置代理
1. 下载：Chrome 浏览器 [SwitchyOmega](http://static.forest10.com/ss/SwitchyOmega.zip
) 插件（解压之后开发者模式安装插件至谷歌浏览器), 导入[教程](http://public-img.forest10.com/ss/switchyOmega-import-bak.png)备份文件[SSHeroku.Bak
](http://static.forest10.com/ss/SSHeroku.bak)）
2. 配置：添加SwitchyOmega代理服务器
```
    代理协议： SOCKS5
    代理服务器local_address：127.0.0.1 
    代理端口local_port： 1080 
```

## 可选
1. SwitchyOmega gfwList如果更新失败使用:http://static.forest10.com/ss/gfwlist.txt
2. heroku 30分钟内无请求会直接睡眠.可使用阿里云监控定时访问.
[阿里云监控](http://public-img.forest10.com/ss/ali-monitor-4-wakeup-heroku.png)
[配置](http://public-img.forest10.com/ss/ali-monitor-4-wakeup-heroku-detail.png)
3. 附上本地正常访问
 ![](http://public-img.forest10.com/ss/heroku-ss-local-client-show-detail-small.jpg)
4. 访问github有困难的可以使用https://git.code.tencent.com/forest10-github/ss-heroku
5. 感谢[七牛云](https://portal.qiniu.com/signup?code=1hkqx38g57yvm)提供的[免费图床](https://portal.qiniu.com/signup?code=1hkqx38g57yvm)以及[CDN](https://portal.qiniu.com/signup?code=1hkqx38g57yvm)支持
