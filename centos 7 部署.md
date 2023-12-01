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
wget https://www.python.org/ftp/python/3.9.8/Python-3.9.8.tgz
```

解压

```shell
tar -xf Python-3.9.8.tgz
```

安装依赖

```shell
# centos
yum install zlib-devel bzip2 bzip2-devel readline-devel sqlite sqlite-devel openssl-devel xz xz-devel libffi-devel -y
```
```shell
# centos
yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gcc make
```

```shell
# Ubuntu
sudo apt install zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev libssl-dev liblzma-dev libffi-dev -y
```

```shell
# Ubuntu
sudo apt install zlib1g-dev libbz2-dev libssl-dev libncurses5-dev libsqlite3-dev libreadline-dev tk-dev gcc make -y
```

配置

```shell
cd /root/Python-3.9.8
```
```shell
./configure --prefix=/usr/local/Python39 --with-ssl
```

编译安装

```shell
make && make install
```

添加环境变量


```shell
cd /root/
```
```shell
vi ~/.bash_profile
```
覆盖以下变量文件 .bash_profile

```shell
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi

# User specific environment and startup programs

PATH=$PATH:$HOME/bin

export PATH=/usr/local/Python39/bin:$PATH
export PYTHON_HOME=/usr/local/Python39
export PATH=$PYTHON_HOME/bin:$PATH
export PATH
```
```shell
esc退出 :wq保存
```
```shell
使环境变量生效（有时候需要，有时候不需要）
source ~/.bash_profile
```




###  安装screen（用于python后台运行脚本）

```shell
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

### 教程地址
https://blog.csdn.net/DreamingBetter/article/details/123918531

```





