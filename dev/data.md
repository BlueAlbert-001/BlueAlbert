# 游戏数据类功能

## 一、概述 <a href="yi-gai-shu" id="yi-gai-shu"></a>

本部分介绍的是天幕微信版中各统计功能的技术接入说明，以下功能均需要单独接入，请开发者与运营人员沟通后，按照文档说明接入功能。在接入以下数据统计功能前，请先确保以下问题正常

{% hint style="info" %}
* [SDK兼容性](https://oppo.skysriver.com/faq/compatibility)不存在问题
* ​[已正确引入与初始化SDK](https://oppo.skysriver.com/dev-guide/basic/initialization)​
* 已接入[登录功能](https://oppo.skysriver.com/dev-guide/basic/login)（若使用无登录功能SDK，需要确认发送了uid）
{% endhint %}

## 二、功能清单列表 <a href="er-gong-neng-qing-dan-lie-biao" id="er-gong-neng-qing-dan-lie-biao"></a>

功能与接口是否必接预计工时（单人）备注​[内购分析](https://oppo.skysriver.com/dev-guide/data/purchase)​否1小时可用于实时统计内购类游戏用户付费与LTV。 结算数据请一定以OPPO结算数据为准，天幕统 计数据仅供参考​[banner分析](https://oppo.skysriver.com/dev-guide/data/createbannerad)​否0.5小时统计OPPO小游戏banner广告从加载与展示两阶 段次数以及异常次数。​[视频分析](https://oppo.skysriver.com/dev-guide/data/createrewardedvideoad)​否0.5小时统计OPPO小游戏激励视频banner广告从加载与 展示两阶段次数以及异常次数。​[性能分析](https://oppo.skysriver.com/dev-guide/data/loadinglog)​否0.5小时统计了代码包加载完（即OPPO白屏后）加载 CDN资源阶段的加载性能数据​[自定义事件](https://oppo.skysriver.com/dev-guide/config/event)​否视具体情况而定用于统计自定义的事件上报，需配合配置后 台一起使用​[A/Btest](https://oppo.skysriver.com/dev-guide/config/abtest)​否1小时用于多方案对比测试，需配合配置后台一起 使用
