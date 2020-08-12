---
description: 本篇介绍如何使用createFlow进行插屏广告的渲染。
---

# 渲染插屏广告位

## **实机兼容性**

* 以下为通过实机测试的引擎以及版本，通常情况下，支持同一大版本下同一引擎的渲染（假设支持版本为1.0.0引擎，1.7.0，1.8.0，1.9.0版本的引擎可能都支持）。
* cocos引擎中，请确保在画布渲染完毕之后调用`createFlow`
* 不建议在横屏游戏中使用该广告位

## 支持的引擎

| 引擎 | 版本号 |
| :--- | :--- |
| laya | v2.0.0beta5.1 |
| cocos | v2.1.0 |

## **使用实例**

{% hint style="info" %}
只要确定广告位的参数与需要渲染的位置即可，SDK会根据广告位ID自动渲染出对应类型的广告位
{% endhint %}

```javascript
let flowUI = wx.tmSDK.createFlow({
    positionId: 1260，
});
// 监听插屏广告关闭事件
flowUI.onDestroy(function({message}) {
    console.log(message)
});
```

插屏广告位的destroy方法将在后续版本上线，目前仅支持用户手动关闭。

### **onError**

```javascript
flowUI.onError(function(error) {
    console.error(error);
})
```

### **offError**

```javascript
let callBack = function(error){ // 假设onError的时候绑定的为该函数
    console.log(error)
};
flowUI.offError(callBack);  // 取消某个监听事件
```

## **监听广告位跳转事件**

1. 监听广告位是否触发点击跳转
2. 回调参数中为返回的原始微信信息

   ```javascript
   flowUI.onNavigate(function(msg) {
    console.error(msg);
   })
   ```

## **取消监听广告位跳转事件**

```javascript
let callBack = function(error){
    console.log(error)
};
flowUI.offNavigate(callBack);  // 取消某个监听事件
```

