完全重写了之前SSR的一键安装包。
- 直接使用git clone的方式安装作者的源码，免去我要不断跟进更新的麻烦
- 直接使用`ssr stop`之类的命令方便管理
- 直接使用作者mujson的方式进行用户管理，无论单用户还是多用户都很方便
- 通过命令添加/删除用户，centos会自动开防火墙端口
- 可以通过命令直接更新/uninstall程序
- 有问题欢迎随时反馈

&nbsp;

# SSR的几个默认设置：
- ssr代码安装在`/home/ssr/`下。
- 默认的加密方式是：`chacha20`
- 默认的协议是：`auth_sha1_v4_compatible`
- 默认的混淆是：`tls1.2_ticket_auth_compatible`

# SSR的一键安装命令：
```
wget -N --no-check-certificate https://raw.githubusercontent.com/leonguyen52/shadowsocks_install/master/ssr-install.sh && bash ssr-install.sh
```

&nbsp;

# SSR一键包的几个命令：

- 添加用户：`ssr adduser`
- 删除用户：`ssr deluser`
- 启动SSR：`ssr start`
- 停止SSR：`ssr stop`
- 重启SSR：`ssr restart`
- 卸载SSR：`ssr uninstall`
- 更新SSR：`ssr update`

# 如果你想自己修改用户和的加密，混淆和协议的话：
修改`nano /home/ssr/mudb.json`文件
```
[
{
"d": 0,
"enable": 1,
"method": "chacha20",
"obfs": "tls1.2_ticket_auth_compatible",
"passwd": "91yun.org",
"port": 9191,
"protocol": "auth_sha1_v4_compatible",
"transfer_enable": 9007199254740992,
"u": 0,
"user": "9191"
}
]
```
几个参数的说明：
- method：加密方法
- passwd：ssr密码
- port：ssr端口
- protocol：协议
- obfs：混淆
- transfer_enable：流量

大家可以自己视情况修改。

# 如果新的有问题，大家依然可以使用旧的安装方式：
```
wget -N --no-check-certificate https://raw.githubusercontent.com/91yun/shadowsocks_install/master/shadowsocksR.sh && bash shadowsocksR.sh
```
- 默认加密为： chacha20
- 默认协议为： auth_sha1_v4
- 默认混淆为： tls1.2_ticket_auth
## 使用命令：
- 启动： /etc/init.d/shadowsocks start
- 停止： /etc/init.d/shadowsocks stop
- 重启： /etc/init.d/shadowsocks restart
- 状态： /etc/init.d/shadowsocks status

- 配置文件路径： /etc/shadowsocks.json
- 日志文件路径： /var/log/shadowsocks.log
- 安装路径： /usr/local/shadowsocks/shadowsoks
