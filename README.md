
# 安装脚本
```
wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/silveryxx/v2ray-agent/master/install.sh" && chmod 700 /root/install.sh && /root/install.sh
```
## 启动脚本
```
vasma
```

## 服务管理
### Xray-core、v2ray-core、trojan-go
- 重启
```
# xray
systemctl restart xray

# v2ray
systemctl restart v2ray

# trojan-go
systemctl restart trojan-go
```

- 启动
````
# xray
systemctl start xray

# v2ray
systemctl start v2ray

# trojan-go
systemctl start trojan-go
````

- 关闭
```
# xray
systemctl stop xray
```
# V2ray官方一键安装脚本（新版）

V2RAY官方的安装脚本命令为(SSH连接VPS后执行)：
```
apt-get install -y curl
curl -L -s https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-release.sh | bash
curl -L -s https://raw.githubusercontent.com/v2fly/fhs-install-v2ray/master/install-dat-release.sh | bash
systemctl enable v2ray

```
复制上面的安装脚本命令到VPS服务器里，复制代码用鼠标右键的复制，然后在vps里面右键粘贴进去，因为ctrl+c和ctrl+v无效。接着按回车键，脚本会自动安装。


安装成功后需要自己准备一个配置文件，可以参考我的配置文件，请自行修改端口、uuid等参数(执行下面的命令下载参考配置文件)：
```
wget https://raw.githubusercontent.com/silveryxx/v2ray-agent/master/config.json  -O -> /usr/local/etc/v2ray/config.json
```

安装完成后，请执行： service v2ray restart ,以确保v2ray启动成功。

控制 V2Ray 的运行的常用命令：

service v2ray restart | force-reload |start|stop|status|reload

测试V2Ray配置文件：
```
/usr/local/bin/v2ray -test -config /usr/local/etc/v2ray/config.json
```
