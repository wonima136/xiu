 * # linux centos7.6系统安装 ，SoftEther VPN Server
* ## SoftEther VPN 概述：
    ### SoftEther VPN 是日本筑波大学的一个研究项目，是一个开放源代码的跨平台多协议 VPN 程序，它包括伺服器端、客户端、伺服器端管理工具等数个软体，支持 SSL-VPN (SoftEtherVPN) 协议、 L2TP/IPsec 协议、 OpenVPN 协议和 Microsoft SSTP 协议，Windows、Linux、Android 和 IOS 等操作系统都可以连接到 SoftEther VPN 伺服器。
    <br>
---
 * ### 登录工具,我这里使用的是宝塔的工具：
```shell
https://download.bt.cn/xterm/BT-Term.zip
```
  ---
 * ### 在安装VPN前我们需要安装它的依赖库如下：
```shell
yum -y install gcc zlib-devel openssl-devel readline-devel ncurses-devel
```
  ---
 * ### 安装下载程序：
```shell
yum install wget -y
```
  ---
 * ### 依赖库安装完成后我们在安装softether server，通过官方下载：
```shell
wget https://github.com/SoftEtherVPN/SoftEtherVPN_Stable/releases/download/v4.31-9727-beta/softether-vpnserver-v4.31-9727-beta-2019.11.18-linux-x64-64bit.tar.gz
```
 * ### [国内下载地址] 依赖库安装完成后我们在安装softether server，通过官方下载：
```shell
wget https://gitee.com/wonima136/vpn/raw/master/softether-vpnserver-v4.31-9727-beta-2019.11.18-linux-x64-64bit.tar.gz
```



  ---
 * ### 下载之后完之后解压：
```shell
tar zxf softether-vpnserver-v4.31-9727-beta-2019.11.18-linux-x64-64bit.tar.gz
```
  ---
 * ### 5.进入解压目录（如果是默认安装都会在root里面）：
```shell
cd /root/vpnserver
```
 ---
 * ### 安裝（直接make 即可）：
```shell
make
```
 * ### 你想读这个软体的许可协议吗？我们选择，选择：```1``` yes
     ![安装](/img/make1.jpg "安装")
 * ### 你读过并理解许可协议了吗？我们继续，选择：```1``` yes
     ![安装](/img/make2.jpg "安装")
 * ### 你同意许可协议吗？我们继续，选择：```1``` yes
     ![安装](/img/make3.jpg "安装")
  ---
 * ### 10.启动它：
```shell
./vpnserver start
```
  ![安装](/img/start.jpg "安装")
  ---
 * ### 设置管理员ip跟端口账号密码，输入：
```shell
./vpncmd
```
 * ### 回复，输入：```1```
 * ### 设置端口输入你要搭建vpn的ip加端口：```ip:443```
 * ### 接着设置用户名我们这里留空直接敲回车：```回车留空```
 * ### 最后一步退出：```CTRL+C```
   ---
 * ### 我们使用windows环境下的远程管理工具vpnsmgr工具来管理VPN伺服器，下载SoftEther VPN Server设置工具
 * <https://www.softether-download.com/files/softether/v4.34-9745-rtm-2020.04.05-tree/Windows/SoftEther_VPN_Server_and_VPN_Bridge/softether-vpnserver_vpnbridge-v4.34-9745-rtm-2020.04.05-windows-x86_x64-intel.exe>
  ---
![安装](/img/1.jpg "安装")<br>
![安装](/img/2.jpg "安装")<br>
![安装](/img/3.png "安装")<br><br>
 * # 设置你的管理密码<br>
![安装](/img/4.jpg "安装")<br>
![安装](/img/5.jpg "安装")<br>
![安装](/img/6.jpg "安装")<br>
![安装](/img/7.jpg "安装")<br>
![安装](/img/8.jpg "安装")<br>
![安装](/img/9.jpg "安装")<br>
![安装](/img/10.jpg "安装")<br>
![安装](/img/11.jpg "安装")<br>
![安装](/img/12.jpg "安装")<br>
![安装](/img/13.jpg "安装")<br>
![安装](/img/14.jpg "安装")<br>
![安装](/img/15.jpg "安装")<br>
![安装](/img/16.jpg "安装")<br>
![安装](/img/17.jpg "安装")<br>
![安装](/img/18.jpg "安装")<br>
![安装](/img/19.jpg "安装")<br>
![安装](/img/20.jpg "安装")<br>
![安装](/img/21.jpg "安装")<br>
![安装](/img/22.jpg "安装")<br><br>
 * ### 连接SoftEther VPN Server工具
<https://github.com/SoftEtherVPN/SoftEtherVPN_Stable/releases/download/v4.31-9727-beta/softether-vpnclient-v4.31-9727-beta-2019.11.18-windows-x86_x64-intel.exe><br>
![安装](/img/pcok.jpg "安装")<br>
![安装](/img/sjok.jpg "安装")<br>
