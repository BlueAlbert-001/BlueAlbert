---
description: 云存储Json参数，用于在线控制游戏内容
---

# 在线参数

## 概述

本篇为在线参数的功能说明，开发说明请参阅：[在线参数-开发说明](../dev-guide/json.md)

此功能可用于控制游戏内容，如广告展示策略等。

## 实现原理

在天幕后台创建JSON格式的配置参数，游戏端口通过SDK接口来获取该配置。&#x20;

相比功能开关，此功能更加灵活，但对应地维护难度较高；所以单纯的开关功能(true/false)，仍建议使用[版本控制](features-switch.md)实现。

## 使用说明

### 创建配置

点击“新建参数”按钮，在弹出的编辑窗口中，输入参数ID，参数说明以及Json配置。

![编辑页面](https://cdn.61week.com/tianmu/doc/index/image/game-set/json/1.png)

### &#x20;Tips

Json字符串的格式，可提前在[https://www.json.cn/](https://www.json.cn/) 中进行验证。

## 接入

请点击每条参数最右侧的“接入”图标，复制弹窗内容，发送给开发人员

![可复制该内容，直接发送开发，提高沟通效率](https://cdn.61week.com/tianmu/doc/index/image/game-set/json/2.png)

开发说明请参阅：[在线参数-开发说明](../dev-guide/json.md)
