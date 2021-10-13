---
description: 主要用于获取当前游戏版本
---

# 【通用】SDK初始化

## **概述**

在天幕SDK中，某些接口在功能上会涉及到**按游戏版本进行控制**（如广告位的按版本开/关），所以需通过此接口传入当前游戏的版本，才可正常使用；

涉及的接口在下方会有说明，请根据使用需求进行查看。

## **涉及的接口**

#### 卖量助手——广告位接入：

* [createFlow](componentization/createflow/)
* [checkFlowIsOpen](ad-position-status.md)
* [getFlowConfig](api/get-ad-position-config.md)
* [flowNavigate](api/landing.md)

**游戏配置——分享功能：**

* [onShareAppMessage](../../game-set/dev-guide/sharing/onshareappmessage.md)
* [shareAppMessage](../../game-set/dev-guide/sharing/shareappmessage.md)

#### 游戏配置——版本控制：

* [getJudgeConfig](../../game-set/dev-guide/function-switch.md)

## **调用方法**

调用`init`方法实现，示例如下

```javascript
wx.tmSDK.init({
     hideRequestLog: false,
     appVersion: '1.0.0'
});
```

{% hint style="danger" %}
请注意，每次更新版本，请记得修改传入的appVersion参数
{% endhint %}

## **传入参数说明**

请按实际情况，传入以下参数。

| 字段             | 字段类型    | 说明             |
| -------------- | ------- | -------------- |
| hideRequestLog | boolean | 是否隐藏请求日志       |
| appVersion     | string  | 当前应用提交微信审核的版本号 |

{% hint style="info" %}
hideRequestLog，默认置为false；这不会影响性能，且便于测试排查。
{% endhint %}
