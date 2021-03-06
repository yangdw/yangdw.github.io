---
layout: post
title: linux文件系统
categories:
- Tool Trick
tags:
- linux
---

> Linux中一切皆是文件。

## 文件属性
### 使用ls -al命令查看时文件列表时的常规属性包括：
- inode数
- [文件属性和权限] [硬链接个数] [归属用户] [归属用户组] [大小] [最后访问或修改的时间] [文件名或目录名]
	- 文件属性和权限，如-rw-rw-r--：
		- 文件类型：-(普通文件),d(目录文件),c(字符设备或块设备文件),s(数据接口文件),l(符号链接文件)
		- 文件权限：
			- -(不具备该权限),r(读取权限),w(写入权限),x(执行权限)
			- 按照顺序：文件归属用户权限，文件归属用户组权限，所有用户权限
			- 每组包含三个权限描述：读取权限，写入权限，执行权限
			- 可通过chmod命令更改文件权限
	- 硬链接个数：1表示属于本身

## 文件目录
- 根目录：/
- 一级目录：
	- /usr (Unix Shared Resources)，用户程序，包含可执行文件、源代码等
	- /var ，变量文件
	- /home ，用户主目录，每个登陆用户名对应一个同名的目录
	- /bin ，可执行文件
	- /sbin ，系统可执行文件
	- /lib ，系统库文件
	- /etc ，配置文件
	- /opt ，可选应用
	- /dev ，设备文件
	- /proc ，进程信息
	- /boot ，启动加载文件
	- /mnt ，挂载目录
	- /media ，可移动媒体设备
	- /srv ，服务数据