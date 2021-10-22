# 微信banner分析（.createBannerAd）

## 一、概述

开发者可以调用 `.createBannerAd` 创建banner广告组件，banner广告组件在创建后会自动拉取广告数据并进行渲染，开发者只需要控制 Banner 广告组件的位置和显示/隐藏即可。

使用方式与微信 [`wx.createBannerAd`](https://developers.weixin.qq.com/minigame/dev/api/ad/wx.createBannerAd.html) 完全一致。

## **二、初始化banner对象**

```java
//创建banner广告，和微信一致
const bannerAd = wx.tmSDK.createBannerAd({
    adUnitId: 'xxxx',
        style: {
        left: 10,
        top: 76,
        width: 320
    }
})
bannerAd.show()
```

## **三、显示banner**

```java
bannerAd.show()
```

## **四、隐藏banner**

```java
bannerAd.hide()
```

## **五、销毁banner**

需要用新的banner时，销毁旧的节约资源。

```java
oldBannerAd.destroy()
const newBannerAd = wx.tmSDK.createBannerAd({
  // ...
})
newBannerAd.show()
```

## **六、onResize**

开发者在创建banner广告时需设置宽高，也可以在创建后重新设置。

```java
bannerAd.onResize(res => {
    bannerAd.style.width = 400;
})
```