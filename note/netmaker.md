# Netmaker笔记

> netmaker是一个开源的、基于WireGuard的网络控制工具，可以快速的用来组建WireGuard网络

### 工作原理

netmaker依赖WireGuard在机器间创建隧道，netmaker通过不同机器的wireGuard创建网络

netmaker server不会路由网络流量，否则这个网络就变成了一个中心辐射模型(hub-and-spoke model)
这会使中心服务器变成瓶颈,并且拖慢网络。相反，network会告诉网络中的节点他们之间可以相互直接通信, 这被称为full mesh network(网状网络)，这会让节点和节点的连接更快。

### 概念

- [WireGuard](https://www.wireguard.com/)

可以简单快速地在设备之间创建加密通道,vpn功能
