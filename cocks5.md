## s5一键安装

```
下载脚本 wget --no-check-certificate https://raw.github.com/Lozy/danted/master/install.sh -O install.sh
安装 bash install.sh  --port=端口 --user=账号 --passwd=密码
成功后会出现：Dante Server Install Successfuly!
卸载脚本：bash install.sh --uninstall
在外部访问CentOS中部署应用时，需要关闭防火墙。
关闭防火墙命令：systemctl stop firewalld.service
关闭开机自启动：systemctl disable firewalld.service
```
```
/etc/init.d/sockd state
 start 开始
 stop 停止
 restart 重新开始
 reload 重新加载
 status 地位
 state 状态
 adduser 添加用户
 deluser 欺骗者
 tail 尾巴
 conf 会议
 update 更新

```


