# cocks5代理搭建
> 服务器尽量下靠近中国的

> 系统：conetos7

> 下完服务器开通端口

> 连接服务器终端切换root用户：sudo -i

> 关闭防火墙
 - 关闭防火墙命令：`systemctl stop firewalld.service`
 - 关闭开机自启动：`systemctl disable firewalld.service`

> 没有wget命令的安装一个`yum install wget -y`

> 下载脚本`wget --no-check-certificate https://raw.github.com/Lozy/danted/master/install.sh -O install.sh`

> 安装 `bash install.sh  --port=端口 --user=账号 --passwd=密码`
 - `成功后会出现：Dante Server Install Successfuly!`

> 卸载脚本：`bash install.sh --uninstall`


> 查看代理状态等等
```shell
/etc/init.d/sockd start # 开始
/etc/init.d/sockd stop # 停止
/etc/init.d/sockd restart # 重新开始
/etc/init.d/sockd reload # 重新加载
/etc/init.d/sockd conf # 代理配置文件
/etc/init.d/sockd status # 地位
/etc/init.d/sockd state # 状态
/etc/init.d/sockd adduser # 添加用户
/etc/init.d/sockd update # 更新
```
> 

> 配置文件修改IP成网卡名字，修改下面这两个参数，将原本的 ***IP*** 改成 ***eth0***
  - 这一步只针对个别服务器商，一般不需要改动看情况而定
 - internal: eth0
 - external: eth0
```shell
# Generate by sockd.info
# Generate interface 172.26.10.136
internal: eth0  port = 1038
external: eth0

method: pam none
clientmethod: none
user.privileged: root
user.notprivileged: sockd
logoutput: /var/log/sockd.log

client pass {
from: 0.0.0.0/0  to: 0.0.0.0/0
}
client block {
from: 0.0.0.0/0 to: 0.0.0.0/0
}
pass {
from: 0.0.0.0/0 to: 0.0.0.0/0
protocol: tcp udp
method: pam
log: connect disconnect
}
block {
from: 0.0.0.0/0 to: 0.0.0.0/0
log: connect error
}
```
> 重新加载下代理 `/etc/init.d/sockd reload`
> 查看下状态 `/etc/init.d/sockd state`

> 代理状态正常返回结果
```shell
+-----------------------------------------+
 Dante Server [ Running ] 
+-----------------------------------------+
 Dante Version:     sockd: dante v1.3.2
 Socks5 Info:      
                    :1038
 Socks5 User:       111
+_________________________________________+
```

> 声明：如果代理状态是 [ Running ]但是又上不了网，那应该是端口的问题。

