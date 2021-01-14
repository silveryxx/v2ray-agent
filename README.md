# v2ray-agent
- [Cloudflare 优化方案](https://github.com/mack-a/v2ray-agent/blob/master/documents/optimize_V2Ray.md)
- [流量中转](https://github.com/mack-a/v2ray-agent/blob/master/documents/traffic_relay.md)
- [手动自建教程](https://github.com/mack-a/v2ray-agent/blob/master/documents/Cloudflare_install_manual.md)
- [ssh入门教程](https://www.v2ray-agent.com/2020-12-16-ssh%E5%85%A5%E9%97%A8%E6%95%99%E7%A8%8B)
- [TG群](https://t.me/technologyshare)、[订阅频道-及时获取更新通知](https://t.me/v2rayagentshare)、[博客地址](https://www.v2ray-agent.com/)
- [公益订阅链接](https://github.com/mack-a/v2ray-agent/blob/master/documents/free_account.md)。


## 安装脚本
```
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/silveryxx/v2ray-agent/master/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```
V2ray官方一键安装脚本（新版）
网上流传一些v2ray一键安装脚本，有的用起来挺方便，但个人更喜欢采用官方脚本，官方脚本更加安全可靠，你懂得。

V2RAY官方的安装脚本命令为(SSH连接VPS后执行)：
```
apt-get install -y curl
curl -L -s https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh | bash
curl -L -s https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-dat-release.sh | bash
systemctl enable v2ray

```
复制上面的安装脚本命令到VPS服务器里，复制代码用鼠标右键的复制，然后在vps里面右键粘贴进去，因为ctrl+c和ctrl+v无效。接着按回车键，脚本会自动安装。


安装成功后需要自己准备一个配置文件，可以参考我的配置文件，请自行修改端口、uuid等参数(执行下面的命令下载参考配置文件)：

wget https://raw.githubusercontent.com/bannedbook/fanqiang/master/v2ss/server-cfg/v2/config.json  -O -> /usr/local/etc/v2ray/config.json
安装完成后，请执行： service v2ray restart ,以确保v2ray启动成功。

控制 V2Ray 的运行的常用命令：

service v2ray restart | force-reload |start|stop|status|reload

测试V2Ray配置文件：

/usr/local/bin/v2ray -test -config /usr/local/etc/v2ray/config.json
