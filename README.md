# shadowsocks
使用shadowsocks的一点方法
## 终端连接ssh
terminal命令终端，ssh 登录名@服务器地址，如 ssh root@12.12.12.12，enter键之后会提示你密码，登录名，服务器地址，密码。
## 错误一 清理当前终端内关于远程服务器的缓存与秘钥
ECDSA host key "ip地址" for has changed and you have requested strict checking错误。
输入 ssh-keygen -R "你的远程服务器ip地址"    
目的是清除你当前机器里关于你的远程服务器的缓存和公钥信息，注意是大写的字母“R”。  
## 为Debian / Ubuntu 安装shadowsocks服务端:  
$ apt-get install python-pip  
$ pip install shadowsocks
## 为Centos 安装shadowsocks服务端:
$ yum install python-setuptools  
$ easy_install pip  
$ pip install shadowsocks
## pip install 环节错误  
Command "python setup.py egg_info" failed with error code 1 in /tmp/pip-install-RW_sjI/shadowsocks/
sudo python -m pip install --upgrade --force pip 
sudo pip install setuptools==33.1.1
## 一键安装
1)wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh  

2)chmod +x shadowsocks-libev-debian.sh  

3)./shadowsocks-libev-debian.sh 2>&1 | tee shadowsocks-libev-debian.log


　　卸载方法：使用 root 用户登录，运行以下命令：

　　./shadowsocks-libev.sh uninstall
1
　　安装完成后即已后台启动 shadowsocks ，运行：

　　ps -ef | grep ss-server | grep -v ps | grep -v grep
1
　　可以查看进程是否存在。此脚本安装完成后，会将 shadowsocks-libev 加入开机自启动。

　　使用命令：

　　启动：/etc/init.d/shadowsocks start

　　停止：/etc/init.d/shadowsocks stop

　　重启：/etc/init.d/shadowsocks restart

　　查看状态：/etc/init.d/shadowsocks status
  ## linux上客户端  
  sudo add-apt-repository ppa:hzwhuang/ss-qt5  
  sudo apt-get update  
  sudo apt-get install shadowsocks-qt5
