---
title: CentOS 安装perforce 客户端
date: 2020-05-08 11:42
tags:
- Linux
- Perforce
---

root用户执行
1.
```
rpm --import https://package.perforce.com/perforce.pubkey
```

2. 添加Yum库配置
Add Perforce's repository to your YUM configuration.
Create a file called /etc/yum.repos.d/perforce.repo with the following content:
[perforce]
name=Perforce
baseurl=http://package.perforce.com/yum/rhel/7/x86_64
enabled=1
gpgcheck=1

3. 安装服务器 也包括了 p4-cli
Install the package by running sudo yum install helix-p4d
```
yum install helix-p4d
```

4. 设置环境变量
```
P4CHARSET=utf8
P4EDITOR=nvim
P4CLIENT=linux_15_80
P4MERGE=nvim
P4USER=grissomshen
P4PORT=0.0.0.0:8666
```

4. 登录与常用命令
```
p4 login # 登录
p4 client # 修改客户端配置
p4 sync # 执行同步
p4 submit # 提交
p4 opened # 列出修改的文件
p4 filelog # 获取文件的最后修改人
p4 annotate # 获取文件行数的最后修改人
```


