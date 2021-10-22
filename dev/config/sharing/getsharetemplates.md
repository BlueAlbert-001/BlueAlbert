# .getShareTemplates

## 一、概述

开发者可通过这个接口接收保存在天幕上的分享素材相关数据。

{% hint style="info" %}
此接口用于一次性获取当前游戏所有分享位上的分享素材，**非必接**，请根据自身需求选择接入；

在明确知道所有分享位ID时，通过[onShareAppMessage](onshareappmessage.md)、[shareAppMessage](shareappmessage.md)即可实现获取特定分享位上的分享素材。
{% endhint %}

{% hint style="warning" %}
使用该接口前，请先进行[SDK初始化](../../basic/initialization.md)
{% endhint %}

{% hint style="info" %}
由于一次性可能获取多个分享素材的URL，为了提高游戏性能，不建议在游戏开始时预先load所有URL对应的图片资源。（只在分享的时候，load对应URL的图片即可）
{% endhint %}

## **二、调用方法**

```javascript
wx.tmSDK.getShareTemplates().then((res) => {
    console.log(res);
})
```

## **三、返回值样例**

```javascript
{
    "scene_1":[{
        "channel_code": "channelA",         //渠道码
        "title":"分享标题",
        "image":"分享图片",
        "path":"pages/index/index",         //跳转小程序路径
        "scene":"scene_1",                  //使用的分享位ID
    }],
    "scene_2":[{
        "channel_code": "channelB",         //渠道码
        "title":"分享标题",
        "image":"分享图片",
        "path":"pages/index/index",         //跳转小程序路径
        "scene":"scene_2",                  //使用的分享位ID
    }]
}
```

## **四、返回值详解**

| 字段            | 字段类型   | 字段说明    |
| ------------- | ------ | ------- |
| channel\_code | String | 分享渠道码   |
| title         | String | 分享标题    |
| image         | String | 分享图片地址  |
| path          | String | 跳转小程序路径 |
| scene         | String | 分享位ID   |
