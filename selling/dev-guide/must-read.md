---
description: 请按照如下步骤完成“卖量助手”的接入，建议阅读者：开发人员
---

# 接入前必读

## 任务清单

* [ ] SDK接入
* [ ] 登录（可选）
* [ ] SDK初始化
* [ ] 接入广告位（API or 组件化）

## Step1

{% hint style="info" %}
为了更好的理解文档，建议开发人员首先快速浏览：[名词解释——卖量助手](../../glossary.md#2-mai-liang-zhu-shou)
{% endhint %}

要完整使用天幕的卖量助手，需要进行SDK的接入，请参阅：

{% page-ref page="add-sdk.md" %}

## Step2

SDK接入完成后，在使用某些接口时，需要进行SDK的初始化，另外，游戏可能需要获取用户头像昵称等信息（登录流程），请参阅：

{% page-ref page="initialization.md" %}

{% page-ref page="login/" %}

1. 未接入天幕登录功能（或使用无登录版SDK时未发送uid）导致卖量功能无法使用
2. 未按照正确SDK接入说明引入SDK文件导致异常或广告展示异常；
3. 未初始化导致广告未展示；

## Step3

{% hint style="info" %}
卖量助手的SDK接入工作主要为：接入广告位；

开始接入前，建议开发人员快速浏览：[广告位说明](../ad-types/)；
{% endhint %}

请参阅以下内容：

{% page-ref page="componentization/" %}

{% page-ref page="api/" %}

{% page-ref page="ad-position-status.md" %}

## 其他

### 开发Demo

开发demo，请参阅：

{% page-ref page="dev-demo.md" %}

### 技术支持

接入过程中有任何问题，欢迎微信扫描下方二维码，咨询天幕对接人员

![](../../.gitbook/assets/readme-3.jpg)

