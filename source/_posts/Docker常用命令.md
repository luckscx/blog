---
title: Docker常用命令
date: 2021-05-01
tags: [docker]
---
#docker 

## 启动进程

```bash

docker run -it "mirrors.tencent.com/ark/ds:Trunk.Shipping.1234" /bin/bash -c "/ds/start_ds.sh -DSAPort=15208"

```

指定执行一个前台命令

## 磁盘端口映射

`docker run -v /out:/inner -p 8080:80 luadoc`

## 查看镜像列表

`docker images`

## 查看运行的容器列表

`docker ps -l`

## 提交状态commit到镜像中

`docker commit [container_id] luadoc`

## Docker hub相关操作

`docker login --username grissomshen --password xxxxxx mirrors.tencent.com`

`docker tag [image_id] mirrors.tencent.com/nlpc/python3.7:1.4.0-production`

`docker push mirrors.tencent.com/nlpc/python3.7:1.4.0-production`

## Docker 复制文件

从外部复制到docker容器内

`docker cp myfile.txt ccae4670f030:/usr/share`

## 新开TTY访问docker

`docker exec [container_id] -it /bin/bash`

## 预拉取列表

`docker pull mirrors.tencent.com/ark/lua`

## 清理不需要的进程

`docker system prune`


## FAQ

### 权限

非root用户执行时，提示权限错误

使用root用户执行

`gpasswd -a ${USER} docker`