---
layout: post
title: ssh_proxy
date: 2020-05-08 13:09:58
tags:
- Linux
- SSH
---

给SSH访问上http proxy

```
yum install connect-proxy
```

修改 ~/.ssh/config
```
Host github.com 
    ProxyCommand connect-proxy -H proxy.company.com:80 %h %p
    ServerAliveInterval 30
```

