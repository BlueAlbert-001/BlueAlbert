---
description: 游戏数据功能说明及使用指引，建议阅读者：小游戏策划、运营
---

# 主要功能说明

## 一、功能一览

1. [数据概览——快速了解矩阵概况 ](main-features.md#1-shu-ju-gai-lan)
2. [核心数据——掌握单款产品核心内容](main-features.md#2-he-xin-shu-ju)
3. [用户分析——活跃、新增用户一手掌握 ](main-features.md#3-yong-hu-fen-xi)
4. [用户留存——新增、活跃留存全掌握 ](main-features.md#4-yong-hu-liu-cun)
5. [收入增长——全方位分析微信收入 ](main-features.md#5-shou-ru-zeng-chang)
6. [渠道分析——分析当前游戏的渠道数据](main-features.md#6-qu-dao-fen-xi)
7. [分享裂变——详细分析分享情况](main-features.md#7-fen-xiang-lie-bian)
8. [用户终端——了解用户所在地区、使用设备 ](main-features.md#8-yong-hu-zhong-duan)
9. [场景值分析——了解用户来源 ](main-features.md#9-chang-jing-zhi-fen-xi)
10. [自定义事件——自定义打点统计](main-features.md#10-zi-ding-yi-shi-jian)
11. [性能分析——助力游戏加载性能提升](main-features.md#11-xing-neng-fen-xi)

{% hint style="info" %}
渠道数据，建议在[买量助手](../channel/)中查看（游戏数据中只提供了单款游戏下的渠道数据）
{% endhint %}

**可接入的功能一览**

| 功能 | 是否必选 | 对应接口或说明 |
| :--- | :--- | :--- |
| 接入天幕SDK | 是 | [接入SDK](../selling/dev-guide/add-sdk.md) |
| 登录 | 是 | [登录功能](../selling/dev-guide/login/) |
| 内购分析 | 否 | [内购数据回传](../general-function/midas.md) |
| 游戏加载性能分析 | 否 | [性能分析](dev-guide/performance-analysis.md) |
| 自定义事件 | 否 | [自定义事件](../game-set/dev-guide/diy-event.md) |
| 分享转发素材分析 | 否 | [分享转发素材](../game-set/dev-guide/sharing/) |
| 微信广告分析 | 否 | [广告分析](dev-guide/official-ad-analysis/) |

## 二、自定义视图

可以将当前报表的搜索条件&展示指标（及指标展示顺序）保存为自定义视图

只需切换视图，无需重复设定搜索条件、展示指标，以达到高效筛选数据的目的

详情请参阅：[自定义视图](../general-function/customized-view.md)

## 三、功能说明

### 1、数据概览

快速了解矩阵概况 

帮助产品策划与负责人快速了解产品矩阵概况与整体用户概况，聚焦于全局汇总数据，帮助管理层快速了解产品数据

![](../.gitbook/assets/image%20%28257%29.png)

{% hint style="warning" %}
由于官方接口返回的微信广告的汇总数据与细分数据中各广告点击量可能不一致（汇总的点击量比细分加和的点击量大），天幕广告分析中的汇总数据点击量采用的是使用细分数据中的点击量加和，而核心数据与数据概览中则直接使用微信接口的汇总数据接口返回数据，因此这两个菜单中的点击量可能会比广告分析中的偏大。
{% endhint %}

### 2、核心数据

掌握单款产品核心数据 

帮助单款产品负责人快速了解产品核心，并可自定义视图聚焦不同的关注重点，解决数据需求个性化问题。

指标说明：[核心数据](indicator-description/core-data.md)

![](../.gitbook/assets/image%20%28262%29.png)

### 3、用户分析

活跃、新增用户活跃度、留存、时长一手掌握 

从活跃用户活跃度到新增构成再到用户停留时长分布，帮助产品运营了解活跃用户粘度与新增用户来源情况，更有针对性的分析用户，解决用户分析无针对性的问题。

![&#x6D3B;&#x8DC3;&#x7528;&#x6237;&#xFF0C;&#x4E86;&#x89E3;&#x7528;&#x6237;&#x6D3B;&#x8DC3;&#x5EA6;](../.gitbook/assets/image%20%28259%29.png)

指标说明：[活跃用户](indicator-description/dau.md)

![&#x65B0;&#x589E;&#x7528;&#x6237;&#xFF0C;&#x4E86;&#x89E3;&#x7528;&#x6237;&#x6784;&#x6210;](../.gitbook/assets/image%20%28164%29.png)

指标说明：[新增用户](indicator-description/increased-user.md)

![&#x65F6;&#x957F;&#x5206;&#x5E03;&#xFF0C;&#x4E86;&#x89E3;&#x7528;&#x6237;&#x4F7F;&#x7528;&#x65F6;&#x957F;&#x60C5;&#x51B5;](../.gitbook/assets/image%20%28104%29.png)

{% hint style="info" %}
用户时长统计仅计算截止到前一日数据
{% endhint %}

### 4、用户留存

新增、活跃留存全掌握 

帮助产品运营与策划了解新增、活跃用户两类留存，全面分析用户留存。

![&#x65B0;&#x589E;&#x7559;&#x5B58;&#xFF0C;&#x53EF;&#x5207;&#x6362;&#x65E5;&#x3001;&#x5468;&#x3001;&#x6708;&#x4E09;&#x4E2A;&#x7EF4;&#x5EA6;](../.gitbook/assets/image%20%28146%29.png)

![&#x6D3B;&#x8DC3;&#x7559;&#x5B58;](../.gitbook/assets/image%20%2864%29.png)

### 5、收入增长

#### 5.1、收入概况

全方位分析微信收入 

收入概况帮助产品负责人与运营人员全面了解微信各项收入情况，分析ARPU，了解产品营收能力。 

![&#x6536;&#x5165;&#x6982;&#x51B5;](../.gitbook/assets/image%20%2848%29.png)

#### 5.2、微信广告分析

监控微信广告收入 

banner分析帮助产品负责人了解广告从加载、展示到点击全流程的次数以及错误情况，通过天幕统计的点击次数帮助运营人员了解banner广告受访情况。 

激励视频分析除了统计广告加载、展示播放、成功播放以及错误情况，同时还记录了时长与播放次数分布图，帮助运营人员更加直观的了解视频受访情况。

指标说明：[广告分析](indicator-description/ad-analysisadad.md)

{% hint style="info" %}
要使用该功能，SDK需做[额外接入工作](dev-guide/#step-3-ke-xuan)
{% endhint %}

![&#x5E7F;&#x544A;&#x5206;&#x6790;](../.gitbook/assets/image%20%2852%29.png)

{% hint style="warning" %}
由于官方接口返回的汇总数据与细分数据中点击量可能不一致（汇总的点击量比细分加和的点击量大），天幕广告分析中的汇总数据点击量采用的是使用细分数据中的点击量加和。而核心数据与数据概览中则直接使用微信接口的汇总数据，因此这两个菜单中的点击量会比广告分析中的偏大。
{% endhint %}

#### 5.3、内购分析

内购分析帮助产品负责人了解具有内购付费的游戏全面分析各类型付费用户人数以及金额，了解内购LTV以及付费用户留存。

指标说明：[内购分析](indicator-description/in-game-payment.md)

{% hint style="info" %}
若要使用该功能，需[额外接入工作](https://doc.skysriver.com/game-data/dev-guide/pay)
{% endhint %}

![](../.gitbook/assets/image%20%28199%29.png)

**5.4、内购订单查询**

内购订单查询可以查看每一笔成功的内购订单用户信息以及订单详细信息，运营人员可以导出用户信息，上传openid至微信MP广告平台，进行更有针对性的广告投放。

![](../.gitbook/assets/image%20%28240%29.png)

{% hint style="info" %}
接入回传内购数据均可实现订单查询功能。详见：[天幕内购数据回传](dev-guide/pay.md)
{% endhint %}

### 6、渠道分析

当前游戏所有渠道的数据（渠道在“[买量助手](../channel/)”中创建）

此处只能查看当前游戏的渠道数据，而非全部游戏，查看全部游戏的渠道请在“[买量助手](../channel/)”中查看

指标说明：[渠道分析](indicator-description/channel-analysis.md)

![&#x6E20;&#x9053;&#x5206;&#x6790;&#x5217;&#x8868;](../.gitbook/assets/image%20%28251%29.png)

![&#x5355;&#x4E2A;&#x6E20;&#x9053;&#x8BE6;&#x7EC6;](../.gitbook/assets/image%20%28268%29.png)

![&#x5355;&#x4E2A;&#x6E20;&#x9053;&#x7528;&#x6237;&#x65F6;&#x957F;&#x5206;&#x5E03;](../.gitbook/assets/image%20%28234%29.png)

### 7、分享裂变

详细分析分享情况 

结合天幕的转发素材配置功能，通过分析分享卡片，从游戏维度分享到各个分享位素材分享两个维度全面分析裂变，解决分享裂变分析无客观依据的问题。

指标说明：[分享裂变](indicator-description/sharing-analysis.md)

{% hint style="info" %}
分享素材的配置后台在“[游戏配置](../game-set/)”中、需[额外接入](../game-set/dev-guide/sharing/)
{% endhint %}

![](../.gitbook/assets/image%20%28142%29.png)

### 8、用户终端

{% hint style="info" %}
用户终端的所有数据每天更新至当前日期前一天，非实时计算数据。
{% endhint %}

#### 8.1、地域分析

了解用户所在地区 

地域分析从省份、城市两个维度帮助产品负责人了解用户所在地，通过可视化图标直观的了解地域分布，为用户分析提供参考依据。

![&#x7701;&#x4EFD;&#x5206;&#x5E03;](../.gitbook/assets/image%20%28135%29.png)

![&#x57CE;&#x5E02;&#x5206;&#x5E03;](../.gitbook/assets/image%20%2890%29.png)

#### 8.2、机型分析

了解用户使用设备 

机型分析从使用的设备品牌、机型两个维度帮助产品负责人了解用户使用的设备。 

![&#x8BBE;&#x5907;&#x54C1;&#x724C;](../.gitbook/assets/image%20%28153%29.png)

![&#x8BBE;&#x5907;&#x578B;&#x53F7;](../.gitbook/assets/image%20%28131%29.png)

#### **8.3、系统分析**

了解用户使用的设备系统

系统分析提供了系统分布，帮助用户终端设备分析有更多的参考依据。

![](../.gitbook/assets/image%20%2853%29.png)

### 9、场景值分析

了解用户访问来源

场景值分析根据微信官方定义的场景值记录了每一个场景值与场景类型的用户情况，让产品负责人可以更加直接的了解到自己的用户来源，解决了用户来源分析的问题，同时为渠道分析提供参考。

![](../.gitbook/assets/image%20%28137%29.png)

### 10、自定义事件

根据游戏特性，灵活打点

{% hint style="info" %}
自定义事件的内容配置在“[游戏配置](../game-set/)”中进行管理，接入说明见[自定义事件技术接入说明](https://doc.skysriver.com/game-set/dev-guide/diy-event)。
{% endhint %}

![](../.gitbook/assets/image%20%2875%29.png)

### 11、性能分析

助力游戏加载性能提升 

天幕性能分析区别于微信自身强大的性能分析，为产品开发团队提供了在微信自身框架加载完成后，游戏资源加载过程的实时数据。通过加载时长与次数分布，直观的展示了性能对于用户访问的影响。助力产品团队性能调优。

指标说明：[性能分析](indicator-description/performance-analysis.md)

{% hint style="info" %}
要使用该功能，SDK需做[额外接入工作](dev-guide/#step-3-ke-xuan)
{% endhint %}

![](../.gitbook/assets/image%20%28193%29.png)



