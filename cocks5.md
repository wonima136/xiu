## s5一键安装
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

