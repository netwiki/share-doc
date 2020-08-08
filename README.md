BGP、OSPF、MPLS路由协议RFC分享

# 1. 概述
## 1.1 BGP
全球有无数台路由器，产生的路由更是多到无法想象。这些路由器分属于大大小小上千个ISP，分布在上百个国家和地区。这些国家由于政治、经济、文化背景千差万别，对互联网的理解也大相径庭。

边界网关协议（BGP）是运行于 TCP 上的一种自治系统的路由协议。 BGP 是唯一一个用来处理像因特网大小的网络的协议，也是唯一能够妥善处理好不相关路由域间的多路连接的协议。

## 1.2 OSPF
OSPF(Open Shortest Path First - 开放式最短路径优先是一个内部网关协议，用于在单一自治系统内决策路由。是对链路状态路由协议的一种实现。著名的Dijkstra算法被用来计算最短路径树。OSPF支持负载均衡和基于服务类型的选路，也支持多种路由形式，如特定主机路由和子网路由等。

## 1.3 MPLS
多协议标签交换（Multi-Protocol Label Switching，MPLS）是新一代的IP高速骨干网络交换标准，由因特网工程任务组（Internet Engineering Task Force，IETF）提出。

MPLS是利用标记（label）进行数据转发的。当分组进入网络时，要为其分配固定长度的短的标记，并将标记与分组封装在一起，在整个转发过程中，交换节点仅根据标记进行转发。

# 2. 分享
看看上面的描述大家是不是对于上面的三种协议非常感兴趣了，这三种协议非常复杂，不是短短一篇文件就可以介绍完毕的。

如果想着学习还得通过专门的学习资料才行，比如《TCP/IP路由技术》，思科路由相关的大量书籍，华三《网络大爬虫》及《网络之路》作为入门。

但是这些都不是最好的，最好的是`RFC`，其包含了关于Internet的几乎所有重要的文字资料。如果你想成为网络方面的专家，那么RFC无疑是最重要也是最经常需要用到的资料之一，所以RFC享有网络知识**圣经**之美誉。

但是RFC都是英文的对于很多小伙伴来说都不太友好，我当年学习时，为了方便就边学习边翻译，然后翻译了几个主要的RFC这里分析给大家了。如果觉得翻译的水平不咋地也可以看原文哦，也会附上。

## 2.1 rfc-4271
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/4271/rfc4271_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/4271/rfc4271.pdf)

本文讨论了一种自治系统路由协议，即边界网关协议（BGP）。
BGP宣告系统的主要功能是与其他BGP系统交换网络可达性信息。这个网络可达性信息包括历经的一系列自治系统（ASes）可达信息。该信息足以构建AS可达性连通图，对路由环路进行修剪，在AS级别，可能会执行一些策略决定。
BGP-4提供了一套支持无类别域间路由（CIDR）。这些机制包括支持公告一组目的地作为IP前缀，并消除BGP内网络“类别”的概念。BGP-4也介绍路由聚合机制，包括AS路径的聚合。

## 2.2 rfc-3107
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/3107/rfc3107_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/3107/rfc3107.pdf)

本文档规定了用于特定路由的标签映射信息的方式，他们搭载在同一边界网关协议（BGP）更新消息中，用于分发本身路由。当BGP用于分发特定路由时，也可以用于分发多协议标签交换（MPLS）映射到该路由标签。

## 2.3 rfc-4364
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/4364/rfc4364_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/4364/rfc4364.pdf)

本文档描述了服务提供商可以使用IP骨干网为其客户提供IP虚拟专用网（VPN）的方法。该方法使用“peer 模型”，其中，客户边缘路由器（CE路由器）将路由发送到服务提供商边缘路由器（PE路由器）；不同站点的CE路由器相互不对等，所以VPN的路由算法看不到“重叠”。数据包通过骨干区隧道，使核心路由器不需要知道VPN路由。

## 2.4 rfc-4456
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/4456/rfc4456_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/4456/rfc4456.pdf)

边界网关协议（BGP）是一种为TCP/IP互联网设计的自治系统间路由协议。通常，单个AS中的所有BGP speaker必须为全连接的，以便任何外部路由信息必须重新分配给自治系统（AS）内所有其他路由器。这是一个严重的规模问题，已经在几个替代方案很好地记录了。
本文档描述了一种称为“路由反射”方法的使用和设计来减轻对“全连接”内部BGP（IBGP）的需求。

## 2.5 rfc-4577
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/4577/rfc4577_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/4577/rfc4577.pdf)

许多服务提供商提供虚拟专用网络（VPN）服务给其客户，使用的技术是客户边缘路由器（CE路由器）作为提供商边缘路由器（PE路由器）的路由peer。边界网关协议（BGP）通过供应商的IP骨干网用于分发客户的路由，以及多协议标签交换（MPLS）通过提供商的骨干网用隧道传输客户数据包。这被称为“BGP/MPLS IP VPN“，BGP/MPLS IP VPN的基本规范假设PE路由器和CE路由器之间接口上的路由协议是BGP。本文档扩展了该规范，通过允许PE/CE接口的路由协议为开放最短路径优先（OSPF）协议。

## 2.6 rfc-4724
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/4724/rfc4724_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/4724/rfc4724.pdf)

本文档描述了一种BGP机制，其有助于最小化BGP重启导致对路由的负面影响。End-of-RIB标记被详细描述并且可以用来传送路由收敛信息。一种新的BGP能力，称为“GR能力”定义为允许BGP speaker表达其具有BGP重启期间保持转发状态的能力。最后，概述了TCP会话终止/重新建立期间暂时保留路由信息的处理。
本文档中描述的机制适用于所有路由器，即包括在BGP重启期间能够保持转发状态和那些没有（尽管后者只需要实现此文件描述的机制的一个子集）。

## 2.7 rfc-4760
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/4760/rfc4760_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/4760/rfc4760.pdf)

本文档定义了BGP-4的扩展，使其能够携带多种网络层协议的路由信息（如IPv6，IPX，L3VPN等）。扩展是向后兼容的 - 支持扩展的路由器可以与不支持扩展的路由器互操作。

## 2.8 rfc-2328
[中文版](https://github.com/netwiki/share-doc/blob/master/rfc/2328/rfc2328_%E4%B8%AD%E6%96%87%E7%89%88.pdf)  
[原版](https://github.com/netwiki/share-doc/blob/master/rfc/2328/rfc2328.pdf)

此文是往上已有的文档，我这就不重新造轮子了。

本备忘录说明了OSPF协议版本2。OSPF 是一种连接状态/link-state 路由协议，被设计用于单一的自制系统/Autonomous System 中。每个OSPF路由器都维持着同样的数据库以描述AS的拓扑结构，并以此数据库来创建最短路径树并计算路由表。
OSPF 在发现拓扑改变后，仅利用很少的路由流量就可以快速的重新计算出路径。OSPF 提供等值多路径。通过提供区域/area 路径，来提供额外的路径保护并可以减少协议所需要的流量。此外，所有的OSPF 路由信息交换都经过验证。



