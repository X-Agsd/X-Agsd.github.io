---
title: "Blog"
date: 2020-10-26T21:22:56+08:00
draft: true
---
# nanopi+花生壳实现内网穿透

 **1. 安装vsftpd**
 他就是一个局域网文件共享（我的理解）
 	nanopi连接网络后，在命令行输入
 	`sudo apt-get install vsftpd`
   	进行安装vsftpd
 	
 	 

```
设置vsftpd,命令行输入
sudo vim /etc/vsftpd.conf

打开以下参数
listen=NO
listen_ipv6=YES
anonymous_enable=yes
local_enable=YES
write_enable=YES
dirmessage_enable=YES
use_localtime=YES
xferlog_enable=YES
connect_from_port_20=YES
secure_chroot_dir=/var/run/vsftpd/empty
pam_service_name=vsftpd
rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
ssl_enable=NO
```
按下Esc ，输入“:wq”，保存退出

 **2.安装filezilla**
下载连接：https://filezilla-project.org/download.php?type=server
 	  	安装之后输入nanopi的局域网IP地址、用户名、密码、和端口。
 	  	![如图](https://img-blog.csdnimg.cn/20201008133749368.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjQxNDkz,size_16,color_FFFFFF,t_70#pic_center)
**3.安装树莓派phddns(花生壳，兼容nanopi)**

```
下载地址：
https://dl-cdn.oray.com/hsk/linux/phtunnel_5_0_rapi_armhf.deb
```
将phtunnel_5_0_rapi_armhf.deb文件，通过filezilla传输到nanopi上。
nanopi安装phtunnel_5_0_rapi_armhf.deb教程：
跟树莓派安装一致，需要注册花生壳和实名认证。
```
https://service.oray.com/question/11639.html
```
这里面要安卓APP或微信扫码进行激活设备
到这就完成了
