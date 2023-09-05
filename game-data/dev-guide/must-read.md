---
description: 请按照如下步骤完成“游戏数据”的接入，建议阅读者：开发人员
---

# 接入前必读

## 一、接入功能列表

| 功能名           | 接口或接入说明                                                                 | 可选或必选  |
| ------------- | ----------------------------------------------------------------------- | ------ |
| SDK接入         |                                                                         | **必选** |
| 登录            | 若使用无登录版需要返回openid                                                       | **必选** |
| 性能分析          | [.sendloading](performance-analysis.md)                                 | 可选     |
| 微信广告分析-banner | [.creatBannerAd](official-ad-analysis/.createbannerad.md)               | 可选     |
| 微信广告分析-视频     | [.creatRewardedVideoAd](official-ad-analysis/.createrewardedvideoad.md) | 可选     |
| 自定义事件         | [.sendEvent](../../game-set/dev-guide/diy-event.md)                     | 可选     |
| 内购分析          | [内购分析接入说明](pay.md)                                                      | 可选     |
| 分享素材分析        | [分享素材配置接入说明](../../game-set/dev-guide/sharing/)                         | 可选     |

## 二、接入流程

### Step1

要完整使用天幕的游戏数据，需要进行SDK的接入，请参阅：

{% content-ref url="../../selling/dev-guide/add-sdk.md" %}
[add-sdk.md](../../selling/dev-guide/add-sdk.md)
{% endcontent-ref %}

### Step2

有关于用户登录的处理，请参阅以下内容：

{% content-ref url="../../selling/dev-guide/login/" %}
[login](../../selling/dev-guide/login/)
{% endcontent-ref %}

### Step3（可选）

游戏数据中的以下功能需单独接入，请根据自身需求选择进行接入。

若需要接入自定义事件功能，请参阅：

{% content-ref url="../../game-set/dev-guide/diy-event.md" %}
[diy-event.md](../../game-set/dev-guide/diy-event.md)
{% endcontent-ref %}

若要接入性能分析功能，请参阅：

{% content-ref url="performance-analysis.md" %}
[performance-analysis.md](performance-analysis.md)
{% endcontent-ref %}

若要接入微信官方广告分析功能，请参阅：

{% content-ref url="official-ad-analysis/" %}
[official-ad-analysis](official-ad-analysis/)
{% endcontent-ref %}

若要接入内购分析功能，请参阅：

{% content-ref url="pay.md" %}
[pay.md](pay.md)
{% endcontent-ref %}

若要接入分享素材分析功能，请参阅：

{% content-ref url="../../game-set/dev-guide/sharing/" %}
[sharing](../../game-set/dev-guide/sharing/)
{% endcontent-ref %}

## 三、其他

### 开发demo

开发demo，请参阅：

{% content-ref url="../../selling/dev-guide/dev-demo.md" %}
[dev-demo.md](../../selling/dev-guide/dev-demo.md)
{% endcontent-ref %}

### 技术支持

接入过程中有任何问题，欢迎微信扫描下方二维码，咨询天幕对接人员

<div align="left">

<img src="../../.gitbook/assets/微信图片_20191009150820 (3).jpg" alt="微信扫一扫，添加天幕对接人员微信">

</div>
