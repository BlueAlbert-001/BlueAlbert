# 【通用】SDK接入

## 概述

若要使用完整的功能，需接入天幕SDK。在接入天幕SDK前请做好以下准备：

1. 是否有天幕账号，若无，请先[注册天幕账号](https://www.skysriver.com)，已有账号请登录；
2. 添加游戏进入对应的主体，在控制台页面可见当前账号已加入的主体，请进入对应主体中的【游戏管理】后台进行添加。

![](../../.gitbook/assets/image%20%28153%29.png)

下面对接入流程进行详细说明，共有两个步骤，十分钟左右即可搞定SDK接入。

## **Step1.下载SDK**

点击操作中的【下载/接入SDK】开始接入

请按要求配置微信的域名白名单，非常重要，务必添加，确认添加完毕后，点击下一步。

![](../../.gitbook/assets/image%20%28129%29.png)

{% hint style="danger" %}
1. 请勿多个游戏使用同一个SDK，每个游戏会对应一个单独的SDK；
2. 微信小游戏转为qq小游戏时，请将其视为接入一个新游戏
{% endhint %}

{% hint style="warning" %}
如果接入时，报错：小程序session解析错误

请检查接入的SDK与小游戏本身是否对应（SDK及SDK所在项目的appid/appsecret，与小游戏实际是否一致）
{% endhint %}

## **Step2.接入SDK**

{% hint style="danger" %}
小游戏引入SDK时必须遵守如下事项：

* SDK必须放在主包中加载，切勿分包加载**（在game.js 中第一行引入sdk文件）**
* 在laya引擎中，文件名必须为.min.js结尾，否则会导致编译报错
{% endhint %}

将下载的sdk文件放置到小游戏工程中，在小游戏game.js中引入SDK，并在需要使用sdk功能的地方调用。

#### 植入方式

* TypeScript或ES6 JavaScript语法植入方式：import 'tm\_sdk.min.js';
* ES5 JavaScript使用commonJs规范的植入方式：require\('tm\_sdk.min.js'\);

#### 校验SDK

* 植入SDK后，复制屏幕上的检测码，在小程序开发工具中将启动参数设为检测码，开始编译**;**
* 设置好参数并完成了编译，请点击“开始检测”按钮进行检测接入状态;
* 天幕将自动检测您的接入是否正常，即可了解SDK接入是否正常;

![](../../.gitbook/assets/sdk-demo.c229fdba.gif)

\*\*\*\*
