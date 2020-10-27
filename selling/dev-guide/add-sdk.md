# 【通用】SDK接入

## 概述

在接入天幕SDK前请做好以下准备：

1. 是否有天幕账号，若无，请先[注册天幕账号](https://www.skysriver.com)，已有账号请登录；
2. 添加游戏，在控制台页面可见当前账号已加入的主体，请进入对应主体中的【游戏管理】后台进行添加。

![](https://cdn.61week.com/tianmu/doc/index/image/selling/dev-guide/add-sdk/1.jpg)

下面对接入流程进行详细说明，共有两个步骤，十分钟左右即可搞定SDK接入。

## **Step1.下载SDK**

在【游戏管理】页面，点击操作中的【下载/接入SDK】开始接入。

### 1、选择需要的SDK版本

天幕提供了**有登录**以及**无登录**两种版本SDK文件。

因为微信的[登录机制](https://developers.weixin.qq.com/minigame/dev/guide/open-ability/login.html)设定，无法在一次登录流程中多个服务器同时获取openID，故：

1. 如果游戏原本**无获取openID的逻辑**，则使用**有登录版本SDK**。
2. 如果待接入天幕SDK的游戏本身有获取openID的逻辑，请选用**无登录版本SDK**
3. 如果曾接入过其他系统的SDK，且其他系统中有获取openID的逻辑，请选用**无登录版本SDK**

   （阿拉丁的SDK无此逻辑，无需做处理，即使用**有登录版本SDK**即可）

{% hint style="info" %}
**登录功能版SDK**由天幕集成封装微信登录功能

**无登录功能版SDK**需要由开发者自行接入微信登录并发送openid提供给天幕方可使用天幕的功能。
{% endhint %}

### 2、下载SDK

请按要求**配置微信的域名白名单**，非常重要，务必添加，确认添加完毕后，点击下一步。

![](https://cdn.61week.com/tianmu/doc/index/image/selling/dev-guide/add-sdk/2.jpg)

选择你需要的SDK版本：

![](../../.gitbook/assets/image%20%28325%29.png)

{% hint style="danger" %}
1. 请勿多个游戏使用同一个SDK，每个游戏会对应一个单独的SDK；
2. 微信小游戏转为qq小游戏时，请将其视为接入一个新游戏
{% endhint %}

{% hint style="warning" %}
如果接入时报错：小程序session解析错误

请检查接入的SDK与小游戏本身是否对应（SDK及SDK所在项目的appid/appsecret，与小游戏实际是否一致）
{% endhint %}

## **Step2.接入SDK**

### **1、所有版本SDK接入流程说明**

{% hint style="danger" %}
小游戏引入SDK时请务必注意如下事项：

* SDK必须放在主包中加载，切勿分包加载**（在game.js 中第一行引入sdk文件）**
* 在laya引擎中，文件名必须为.min.js结尾，否则会导致编译报错
{% endhint %}

将下载的sdk文件放置到小游戏工程中，在小游戏game.js中引入SDK，并在需要使用sdk功能的地方调用。

{% hint style="info" %}
请注意：

* 在cocos引擎中，如果打包之前没有game.js文件，则只需将SDK文件放在主包中一起打包，这样就可以直接调用了，无需引入SDK文件（还可以在wx.d.ts中定义tmSDK变量）
{% endhint %}

#### 植入方式（注意根据所下载SDK版本文件名植入，以下以天幕包含登录的全功能sdk为例）

* TypeScript或ES6 JavaScript语法植入方式：import 'tm\_sdk.min.js';
* ES5 JavaScript使用commonJs规范的植入方式：require\('tm\_sdk.min.js'\);

#### 校验SDK

* 植入SDK后，复制屏幕上的检测码，在小程序开发工具中将启动参数设为检测码，开始编译**;**
* 设置好参数并完成了编译，请点击“开始检测”按钮进行检测接入状态;
* 天幕将自动检测您的接入是否正常，即可了解SDK接入是否正常;

![](https://cdn.61week.com/tianmu/doc/index/image/selling/dev-guide/add-sdk/3.gif)

### **2、无登录版SDK使用说明**

以下流程**仅使用了无登录版SDK**的开发者需要阅读。

![](../../.gitbook/assets/image%20%28323%29.png)

1. 下载无登录版本的SDK
2. [SDK初始化](initialization.md)
3. 开发者通过自己的服务端接口获取到openid后调用SDK接口，发送openid。（**若不发送openid将导致天幕功能无法使用**）

```javascript
wx.tmSDK.sendUserInfo({ openId: '开发者传入的openId', gender: 1 }); 
// gender可选传入，默认值为1,默认代表男生 
```

{% hint style="info" %}
强烈建议在登录获取到openid以后第一时间发送给天幕，避免数据统计、卖量助手等功能出现异常。
{% endhint %}

{% hint style="danger" %}
**【注意事项】** 

1、无登录版本SDK，以下接口无法使用

*  [.updateUserInfo ](login/update-userinfo.md)（天幕-更新用户信息）
*  [.login](login/get-user-info.md)（天幕-登录/获取用户信息）

2、因为无openid无法使用数据统计功能、买卖量助手功能，请接入SDK后及时发送openid避免数据统计、买卖量助手等功能无法使用或功能异常。
{% endhint %}



