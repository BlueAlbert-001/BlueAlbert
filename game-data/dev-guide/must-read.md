---
description: 请按照如下步骤完成“游戏数据”的接入，建议阅读者：开发人员
---

# 接入前必读

## 一、接入功能列表

| 功能名 | 接口或接入说明 | 可选或必选 |
| :--- | :--- | :--- |
| SDK接入 |  | **必选** |
| SDK初始化 |  | **必选** |
| 登录 |  | **必选** |
| 性能分析 | [.sendloading](performance-analysis.md) | 可选 |
| 微信广告分析-banner | [.creatBannerAd](official-ad-analysis/.createbannerad.md) | 可选 |
| 微信广告分析-视频 | [.creatRewardedVideoAd](official-ad-analysis/.createrewardedvideoad.md) | 可选 |
| 自定义事件 | [.sendEvent](../../game-set/dev-guide/diy-event.md) | 可选 |
| 内购分析 | [内购分析接入说明](pay.md) | 可选 |
| 分享素材分析 | [分享素材配置接入说明](../../game-set/dev-guide/sharing/) | 可选 |

## 二、接入流程

### Step1

要完整使用天幕的游戏数据，需要进行SDK的接入，请参阅：

{% page-ref page="../../selling/dev-guide/add-sdk.md" %}

### Step2

有关于用户登录的处理，请参阅以下内容：

{% page-ref page="../../selling/dev-guide/login/" %}

### Step3（可选）

游戏数据中的以下功能需单独接入，请根据自身需求选择进行接入。

若需要接入自定义事件功能，请参阅：

{% page-ref page="../../game-set/dev-guide/diy-event.md" %}

若要接入性能分析功能，请参阅：

{% page-ref page="performance-analysis.md" %}

若要接入微信官方广告分析功能，请参阅：

{% page-ref page="official-ad-analysis/" %}

若要接入内购分析功能，请参阅：

{% page-ref page="pay.md" %}

若要接入分享素材分析功能，请参阅：

{% page-ref page="../../game-set/dev-guide/sharing/" %}

## 三、其他

### 开发demo

开发demo，请参阅：

{% page-ref page="../../selling/dev-guide/dev-demo.md" %}

### 技术支持

接入过程中有任何问题，欢迎微信扫描下方二维码，咨询天幕对接人员

![&#x5FAE;&#x4FE1;&#x626B;&#x4E00;&#x626B;&#xFF0C;&#x6DFB;&#x52A0;&#x5929;&#x5E55;&#x5BF9;&#x63A5;&#x4EBA;&#x5458;&#x5FAE;&#x4FE1;](../../.gitbook/assets/wei-xin-tu-pian-20191009150820%20%281%29.jpg)

