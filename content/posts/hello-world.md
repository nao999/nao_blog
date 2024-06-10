---
title: "Hello World"
date: 2024-06-10T15:41:52+08:00
draft: true
---

#### k8s pod、replicaset、deployment、service、node

![](https://nao190830.oss-cn-beijing.aliyuncs.com/img/2024/06/09/20240609161716.png)

#### pod：

#### replicaset

目的是为了维护一组在任何时候都处于运行状态的pod副本的稳定集合，通常用来保证给定数量的、完全相同的pod的可用性

#### deployment

为pod和replicaset提供声明式更新能力， 可以动态地创建和销毁 Pod。

#### service

将运行在一个或一组pod上的网络应用程序公开网络服务的方法。主要作用是用于接收和发出流量。可以通过Service配置`spec`下的`type`来公开Service

- CluserIP：在集群内部ip上公开Service,只能在集群内部访问

- NodePort：使用NAT在集群中每个选定Node的相同端口公开Service，使用`<NodeIP>:<NodePort>` 从集群外部访问 Service。是 ClusterIP 的超集。

- *LoadBalancer* - 在当前云中创建一个外部负载均衡器（如果支持的话），并为 Service 分配一个固定的外部IP。是 NodePort 的超集。
