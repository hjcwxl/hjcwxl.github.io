---
layout: page
title:  "apt-get和vim"
subtitle: "小白上路"
date:   2020-09-11 21:21:21 +0530
categories: ["工具的使用"]
---

## apt-get

- 定义
    - 1.将网站中所有的软件的名字基本信息下载下来
    - 2.下载安装过程会以下载下来的信息进行筛选
- 命令 
    - apt-get update
        - 更新本地下载的本地信息(更新镜像源的软件信息)
    - apt-get install(下载安装) nginx(软件名)
        - 下载软件
    - cp sources.list sources.list.bak
        - cp 文件名 .bak
        - 复制(备份)sources.list文件
        - sources.list apt的配置文件
    - cd /etc/nginx
        - cd 切换文件(切换到nginx)
    - nginx -v 
        - 查看nginx版本号
    - cd /etc/nginx vim nginx.conf
        - 切换到nginx配置文件

## 配置apt-get阿里云镜像源
- apt-get的工作原理(下载软件 工作分两部，搜索在本地)
    - 切换到 cd /etc/apt 文件下
    - vim sources.list 更换镜像源
- apt-get update
- apt-get install 软件名
- apt-get的配置文件(修改远程连接为阿里云的镜像)

## Linux系统

- 基本命令
    - mkdir 创建文件夹
    - touch 创建文件
    - rm 删除一个文件或者目录
    - pwd 查看当前目录路径
    - cd 切换文件夹
    - ls 查看文件夹
- 权限
    - chmod -R 777 目录路径(访问网站需要将网站根目录设置为777权限)
    - 读 写 执行分别被安排的数字为

## 安装nginx
- 安装
    - 如何判断nginx安装成功
        - 切换到nginx目录下，打 nginx -v 查看版本号来判断是否安装成功
    - 启动 service nginx start
    - 停止 service nginx stop
    - 重启 service nginx restart
- 修改nginx配置文件
	- 主配置文件 nginx.conf
	- 辅助配置文件 （要知道再哪里看 再主配置文件中查看）
		- sites-enabled里面的所有文件
		- conf.d里面的所有conf文件
	- 将sites-enabled里面的default(nginx中默认的网站配置文件)更改其网站根目录
- 查看错误日志文件(在哪里看)
    - 在 /var/log/nginx/error.log

## vim命令

- vim三种编辑模式
    - 命令行模式(esc/默认)
        - 引导，默认的模式
        - 刚进入的Xshell6里的默认模式就是命令行模式
        - 命令
            - :w 保存，:q 退出，:wq 保存退出
            - :q! 强制退出
            - yy 复制
            - dd 删除，如：删除一千行 1000dd
            - p 粘贴，u 撤回
    - 编辑模式
        - 在命令行模式下按a、A、i、I进入编辑模式
        - ESC 退出编辑模式，切换到命令行模式
    - 视图模式