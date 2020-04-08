# 性能分析 （.sendLoadingLog）

## 一、概述

* 接入小游戏加载时长后，可以记录在完成微信界面加载后，用户停留在资源加载界面的时长，为[性能分析](../indicator-description/performance-analysis.md)功能提供支持，分析在资源加载阶段用户访问流失的情况。
* 具体可通过`sendLoadingLog` 方法实现，该方法可用于记录游戏进度条加载时长，便于统计与后续优化。
* 该功能为开发者选择性接入。

## **二、调用方法**

调用 `sendLoadingLog` 方法传入类型：

* `progressStart` 用于进度条开始加载
* `progressEnd` 用于进度条结束加载

统计中分为T1、T2、T3三阶段，对应的阶段说明如下：

* T1：在微信界面加载完成后，进入游戏，T1时长即微信界面加载完成后进入游戏界面的时长
* T2：在T1正式进入游戏后，进入资源加载，T2时长即正式进入游戏后到开始资源加载界面的时长
* T3：资源加载结束，进入游戏内容界面，T3时长即资源加载结束到进入游戏内容界面的时长

## **三、使用示例**

```java
//进度条开始加载前
wx.tmSDK.sendLoadingLog('progressStart');
...
//进度条加载完成后
wx.tmSDK.sendLoadingLog('progressEnd');
```



