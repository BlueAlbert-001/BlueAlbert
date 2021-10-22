# 游戏数据类功能

## 一、概述 <a href="yi-gai-shu" id="yi-gai-shu"></a>

本部分介绍的是天幕微信版中各统计功能的技术接入说明，以下功能均需要单独接入，请开发者与运营人员沟通后，按照文档说明接入功能。在接入以下数据统计功能前，请先确保以下问题正常

{% hint style="info" %}
* [SDK兼容性](../../questions/compatibility.md)不存在问题
* ​[已正确引入](../basic/add-ask.md)与[初始化SDK​](../basic/initialization.md)
* 已接入[登录功能](../basic/login/login.md)（若使用无登录功能SDK，需要确认发送了uid）
{% endhint %}

## 二、功能清单列表 <a href="er-gong-neng-qing-dan-lie-biao" id="er-gong-neng-qing-dan-lie-biao"></a>

| 功能与接口                              | 是否必接 | 预计工时（单人） | 备注                                                          |
| ---------------------------------- | ---- | -------- | ----------------------------------------------------------- |
| [内购分析](purchase.md)                | 否    | 1小时      | <p>可用于实时统计内购类游戏用户付费与LTV。<br>结算数据请一定以微信结算数据为准，天幕统计数据仅供参考</p> |
| [微信banner分析](createBannerAd.md)    | 否    | 0.5小时    | <p>统计微信小游戏banner广告从加载与展示两阶<br>段次数以及异常次数。</p>                |
| [微信视频分析](createRewardedVideoAd.md) | 否    | 0.5小时    | 统计微信小游戏激励视频banner广告从加载与展示两阶段次数以及异常次数。                       |
| [性能分析](sendLoadingLog.md)          | 否    | 0.5小时    | <p>统计了代码包加载完（即微信白屏后）加载<br>CDN资源阶段的加载性能数据</p>                |
|                                    |      |          |                                                             |
|                                    |      |          |                                                             |
|                                    |      |          |                                                             |
