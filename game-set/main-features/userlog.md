# 用户日志（暂未开放）

## 一、概述

用户日志功能是天幕提供给开发人员接入SDK功能后用于验证功能正常与否的功能后台。**目前暂未开放，敬请期待**。

开发者可以利用用户日志功能后台检查接入天幕SDK后用户行为上报是否正常。

目前支持检查接入的天幕功能有：

* 登录
* 分享转发
* 自定义事件
* 微信广告中banner与激励视频加载、展示与错误事件

## 二、功能说明

### **1、后台位置**

游戏配置-用户日志

![](../../.gitbook/assets/image%20%2865%29.png)

### 2、使用说明

当您在接入天幕SDK的功能后，需要验证接入的功能中用户行为上报是否正常，可访问用户日志后台。

* 2.1 首先您需要拿到测试用户的openid
* 2.2 然后您可以开始在游戏中操作，通过右上角的刷新按钮更新查询展示的用户行为 若功能正常接入，则会在列表中看到一条记录，展示了相应的操作行为。 若未在列表中看到记录，则接入存在问题，需要开发者检查问题。

![](../../.gitbook/assets/image%20%28100%29.png)

### 3、用户行为说明

当您在确认功能正常接入，数据正常上报后，对应的操作行为会展示在列表中。在原始日志中，对应行为字段的中文释义如下。

* bannerLoad：微信banner加载
* bannerLoadError：微信banner加载错误
* bannerShow：微信banner展示
* bannerShowError：微信banner展示错误
* custom\_event：自定义事件
* login\_in：访问
* login\_out：退出
* share：分享转发
* videoClose：微信激励视频关闭
* videoError：微信激励视频展示错误
* videoLoad：微信激励视频加载
* videoLoadError：微信激励加载错误
* videoShow：微信激励视频展示

### 4、了解行为详细信息

每一条记录都可以通过“查看”弹窗中的原始日志了解本次上报的行为日志数据详细信息。主要字段说明如下：

![](../../.gitbook/assets/image%20%2822%29.png)

其他重要字段如下：

* out\_ccode：本次访问行为的来源渠道ID 渠道ID信息可参阅【[买量助手使用说明](../../channel/main-features/channel-management.md)】
* device：用户的设备信息对象，具体可见官方说明【[api:获取系统信息](https://developers.weixin.qq.com/minigame/dev/api/base/system/system-info/wx.getSystemInfo.html)】

### 5、其他说明

* 目前用户日志功能性能还有优化中，显示的日志列表存在时间延迟，我们将持续优化尽可能减小延迟。
* 查询某个openid的日志列表时，右侧显示的用户详细信息每天更新一次，非实时更新。

