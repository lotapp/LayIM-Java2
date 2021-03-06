# 概述

内部的即时通讯平台，有两种使用模式：
1，共内部员工之间即时沟通，所有系统中的用户可以互相聊天留言，也可以同一个部门内容群聊；和一般的即时通讯一样，但不支持加好友、新建群等操作。
2，客服模式，是同设置几个客服；所有的人只能和客服聊天，并且所有的聊天记录，任何一个客服都可以看到。
项目的前端使用LayIM，后端自己编写。

# 聊天模式

聊天模式没有太多好说的，他实现了LayIM中大多数功能就可以了，去掉添加好友、添加群的功能。

# 客服模式

客户端新增的功能：在没有选定客服的情况下可以 列举在线客户（所有客服）、选择客服。
后端可以 将服务转移到其他客服。其他客服也可以看到前面的沟通内容。
聊天模式又分两种，一种是专题模式（或专家模式），一种是一对一模式（或责任制模式、服务模式）

## 专家模式

专家模式就是不同的客户解决不同的问题，用户可以和同时向不同的专家（客服）咨询不同的问题，每个专家（客服）只负责这个问题.
专家（客服）和用户不是对等的，在客服端，有一个服务的用户列表（类似与聊天模式中的用户列表，但是没有组的概念），其中记录所有服务过的用户，如果有新的用户请求将会添加一个新的条目。这个用户原则上不会减少，但是可以设置长时间没有联系的用户自动隐藏，比如：一月没有联系的客户。

## 服务模式

服务模式就是一个用户固定一个客服，一站到底，当然如果这个客服解决不了的问题可以转移给其他客户，新客户可以看到前面所有的聊天记录，继续为该用户服务。
客服和用户不是对等的，在客服端，有一个服务的用户列表，其中记录所有服务过的用户，如果有新的用户请求将会添加一个新的条目。客服将用户转移给其他客服时这个用户自动从列表中移除，在其他客服列表中增加。通用可以设置长时间没有联系的用户自动隐藏。

# 其他增强功能

主要有两个：一、智能机器人；二、表单推送：比如推送用户验证（确认）表单、用户评价表单等等。
