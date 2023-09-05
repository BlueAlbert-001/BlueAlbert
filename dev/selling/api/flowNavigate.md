# .flowNavigate

## 概述

{% hint style="warning" %}
使用该接口前，请先进行[SDK初始化](../../basic/initialization.md)
{% endhint %}

`flowNavigate`接口用于实现点击创意后跳转到对应游戏的落地页的功能

此功能的使用前提：调用了获取广告推广配置[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)

{% hint style="info" %}
此接口调用只适用于版本库 2.2.0 以上，所有开发者在调用时注意要把开发工具的版本库调到2.2.0以上的版本，否则会报错。
{% endhint %}

## **调用方法**

```java
wx.tmSDK.flowNavigate({
    positionId: positionId, // 广告位id, 请先使用该id获取推广创意列表
    creativeId: creativeId,  // 传入获取到的creativeId
}).then((newList)=>{
    console.log('跳转成功or取消跳转（可根据特有返回值区分两种情况）')
    console.log('自动刷新列表：', newList)//返回最新列表 
}).catch((error)=>{
    console.log('跳转失败', error);
})
```

## **传入值详解**

| 字段         | 字段类型   | 字段说明            |
| ---------- | ------ | --------------- |
| positionId | Number | 当前点击的positionId |
| creativeId | Number | 当前点击的creativeId |

## **返回值**

### **基本返回值**

基本返回值和[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)结构基本一致, 请参考[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)文档

{% hint style="info" %}
使用该返回值重新刷新创意的展示，可实现点击刷新的效果，[点击查看详情](./#2-dian-ji-shua-xin)
{% endhint %}

### **特有返回值**

| 字段              | 字段类型   | 字段说明         |
| --------------- | ------ | ------------ |
| navigateMessage | Object | 触发跳转后微信的原始消息 |

TIPS：用户**取消跳转**时，该值为：`errMsg:"navigateToMiniProgram:fail cancel"`

{% hint style="info" %}
可使用此值判断用户是否取消了跳转。
{% endhint %}
