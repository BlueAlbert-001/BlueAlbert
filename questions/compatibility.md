---
description: 天幕SDK与其他运营系统的兼容问题
---

# SDK兼容问题（重要）

### 引擎支持问题

天幕SDK支持现有主流的小游戏开发引擎：Cocos、Laya、Egret

### 登录过程中的兼容问题

需注意在登录流程中获取openID时处理如下兼容问题：

因为微信的[登录机制](https://developers.weixin.qq.com/minigame/dev/guide/open-ability/login.html)设定，无法在一次登录流程中多个服务器同时获取openID，故：

1. 如果待接入天幕SDK的游戏本身**有获取openID的逻辑**，需要去除此部分逻辑，改用天幕的接口[`.login`](../selling/dev-guide/login/get-user-info.md)直接获取openID
2. 如果游戏原本**无获取openID的逻辑**，则直接引入SDK即可。
3. 如果曾接入过其他系统的SDK，需要去除其中获取openID的逻辑（阿拉丁的SDK无此逻辑，无需做处理，即天幕SDK与阿拉丁完全兼容）

{% hint style="info" %}
除上述问题外，天幕SDK不会引起兼容性问题
{% endhint %}

相关阅读：[天幕登录流程/获取用户信息](../selling/dev-guide/login/)
