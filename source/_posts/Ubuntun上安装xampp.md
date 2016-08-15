---
title: Ubuntun上安装xampp
date: 2016-08-14 22:22:39
tags: 常用命令
---

### 1.下载xampp
```
$ wget http://iweb.dl.sourceforge.net/project/xampp/XAMPP%20Linux/5.6.15/xampp-linux-x64-5.6.15-2-installer.run
```
### 2.添加可执行权限
```
$ sudo chmod +x xampp-linux-x64-5.6.15-2-installer.run
```
### 3.安装
```
$ sudo ./xampp-linux-x64-5.6.15-2-installer.run
```
### 4.启动xampp
```
$ sudo /opt/lampp/lampp start
```
### 注意
1.如果phpmyadmin 提示没有权限 执行 
```
$ chmod -R 755 phpmyadmin/
```
2.phpmyadnin 无法从外网访问 修改/opt/lampp/etc/extra下的httpd-xampp.conf
```
<Directory "/opt/lampp/phpmyadmin">
    AllowOverride All
    Order allow,deny
    Allow from all
</Directory>
```
3.如果apache 提示没有权限 找到 /opt/lampp/etc下得httpd.conf
```
<Directory />
   Options All
    AllowOverride All
    Order deny,allow
    Allow from all
</Directory>
```
4.使用密码登录phpmyadmin找到
/opt/lampp/phpmyadmin config.inc.php 设置成 
```
$cfg['Servers'][$i]['auth_type'] = 'config'; 使用密码登录
```
注： cookie与config。当在正式环境时，用 cookie，要求用户必须输入正确的用户名与密码，而在本地测试服务器时，一般用 config，省得session失效后又得输入用户名与密码，以节省开发时间。
