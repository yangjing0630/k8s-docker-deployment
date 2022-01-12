# Helm学习笔记

## Helm介绍

Helm是Deis开发的一个用户kubernetes应用的包管理工具，主要用来管理charts，有点类似于Ubuntu中apt 或 Centos中yum。

Helm Chart是用来封装kubernetes原声应用程序的一系列yaml文件，可以在部署应用时自定义应用程序的一些metadata。对于应用发布者而言 可以通过Helm打包应用、管理应用依赖、管理应用版本并发布应用到仓库。

## Helm组件及相关术语

- Helm

Helm是一个命令行下的客户端工具，主要用于k8s应用程序chart的创建、打包、发布等

- Tiller

Tiller是Helm服务端，部署在kubernetes集群中。

- Chart

Helm软件包，采用TAR格式。类似于APT的DEB包或YUM的RPM包，其包含了一组定义kubernetes资源相关的yaml文件

- Repository

Helm的软件仓库，repository本质是一个web服务器，该服务器保存了一系列的chart软件包以供用户下载

- Release

使用helm install 命令在kubernetes 集群中部署的chart称为release