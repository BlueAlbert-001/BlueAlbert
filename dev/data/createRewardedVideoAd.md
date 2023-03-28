# 微信视频分析（.createRewardedVideoAd）

## 一、概述

开发者可以调用 `.createRewardedVideoAd` 创建激励视频广告组件，该方法返回一个全局单例，且使用方式与微信 [`wx.createRewardedVideoAd`](https://developers.weixin.qq.com/minigame/dev/api/ad/wx.createRewardedVideoAd.html) 完全一致。

## **二、初始化激励视频对象**

```java
//创建激励视频对象，和微信一致
let rewardedVideoAd = wx.tmSDK.createRewardedVideoAd({
    adUnitId: "xxx"
});
```

## **三、显示激励视频**

```java
rewardedVideoAd.load()
.then(() => rewardedVideoAd.show())
```

## **四、拉取失败并重新拉取**

```java
rewardedVideoAd.show().catch(err => {
    rewardedVideoAd.load().then(() => rewardedVideoAd.show())
})
```

## **五、监听用户关闭广告**

```java
rewardedVideoAd.onClose(res => {
    rewardedVideoAd.offClose();//取消监听用户点击关闭事件
    //（视频广告是一全局单例，当需要监听多个视频广告时，需首先取消前一个的监听，否则下发奖励可能异常）
    
    // 用户点击了【关闭广告】按钮
    // 小于 2.1.0 的基础库版本，res 是一个 undefined
    if (res && res.isEnded || res === undefined) {
      // 正常播放结束，可以下发游戏奖励
    }
    else {
        // 播放中途退出，不下发游戏奖励
    }
})
```
