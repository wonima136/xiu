### 环境安装
### java
```shell
yum install java-1.8.0-openjdk-devel.x86_64

linux 运行java格式
nohup java -jar /home/jar/WebmasterTools-0.0.1.jar >> /home/jar/WebmasterTools.log &

win 运行java格式
java -jar WebmasterTools-0.0.1.jar

```
### python3.9安装

下载

```shell
wget https://www.python.org/ftp/python/3.9.5/Python-3.9.5.tgz
```

解压

```shell
tar -xf Python-3.9.5.tgz
```

安装依赖

```shell
yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel xz xz-devel libffi-devel -y
```
```shell
yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc make
```

配置

```shell
cd /root/Python-3.9.5
```
```shell
./configure --prefix=/usr/local/Python39 --with-ssl
```

编译安装

```shell
make && make install
```

添加环境变量

```
```shell
cd /root/
```
```shell
vi ~/.bash_profile
```
```shell
insert在PATH后添加 /usr/local/Python39/bin

PATH=$PATH:$HOME/bin
export PYTHON_HOME=/usr/local/Python39
export PATH=$PYTHON_HOME/bin:$PATH
export PATH
```

esc退出 :wq保存

使环境变量生效
source ~/.bash_profile

```



### Nginx安装

```shell
yum install nginx -y 
```

配置Nginx配置文件位置

```
/etc/nginx/config.d/

ls /etc/nginx/config.d/
cd /etc/nginx/config.d/
vim xiaoshuo.conf

修改 root 为项目地址
保存之后重新加载
nginx -s raload

可以查看nginx是否启动
ps -aux | grep nginx
```

### python模块依赖安装

```
pip3 install -i https://pypi.doubanio.com/simple sanic jinja2 motor

pip3 install setuptools==33.1.1
pip3 install --upgrade pip
```

防火墙配置

```shell
# 查看防火墙某个端口是否开放
firewall-cmd --query-port=80/tcp

# 开放防火墙80端口
firewall-cmd --zone=public --add-port=80/tcp --permanent

# 关闭80端口
firewall-cmd --zone=public --remove-port=80/tcp --permanent

# 配置立即生效
firewall-cmd --reload

# 查看防火墙状态
systemctl status firewall

# 关闭防火墙
systemctl stop firewall

# 打开防火墙
systemctl start firewall

# 开放一段端口
firewall-cmd --zone=public --add-port=8121-8124/tcp --permanent

# 查看开放端口列表
firewall-cmd -zone=public --list-ports
```

###  screen

安装

```shell
# centos8下需要先安装epel-release
yum install epel-release screen -y
```

新建会话

```shell
screen -S soft
```

离开会话

```shell
Ctrl-a d
```

回到某个会话

```shell
screen -r soft
```

关闭会话

```
Ctrl-a k

关闭80端口占用
kill -9 `lsof -ti:8080`

清除全部进程
screen -wipe 

查看会话
screen -ls

删除一个
screen -X -S 122128 quit
```



### crontab:定时任务

```
#安装crontab:定时任务
yum install crontabs

#卸载crontab:定时任务
yum remove crontabs

#进入
crontab -e

#定时任务格式
01 02,04,06,08,10,12,14,16,19,20,22 * * * /usr/bin/php -f /home/www/cache/d58.php
0 15 * * * python3 /www/wwwroot/soft_group/sitemap_pro.py

#退出定时任务
:wq


C:\Python35\Lib>python C:\Python35\Tools\scripts\2to3.py -w bs4


/root/Python-3.9.5/Lib

python3 /usr/local/Python39/lib/python3.9/test/test_lib2to3.py -w bs4





nohup python my.py >> my.log 2>&1 &
# 或者
nohup python my.py >> nohup.out 2>&1 &
# 或者
nohup python my.py &  # 这种写法和上面第二种写法等价


https://blog.csdn.net/DreamingBetter/article/details/123918531

```





