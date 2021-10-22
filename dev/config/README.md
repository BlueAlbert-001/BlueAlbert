# 游戏配置类功能

## 一、概述 <a href="yi-gai-shu" id="yi-gai-shu"></a>

游戏配置提供了运营功能以及一些数据统计配置功能，在接入前，建议开发者与运营人员沟通好相关配置后台的需求后进行接入，

## 二、功能清单列表 <a href="er-gong-neng-qing-dan-lie-biao" id="er-gong-neng-qing-dan-lie-biao"></a>

| 功能与接口                                                    | 是否必接 | 预计工时（单人） | 备注                                               |
| -------------------------------------------------------- | ---- | -------- | ------------------------------------------------ |
| [​ 版本控制 （.getJudgeConfig）](getJudgeConfig.md)            | 否    | 0.5小时    | 使用该接口前，请注意需要[SDK初始化](../basic/initialization.md) |
| [在线参数 （.getAppJSONConfig）](getAppJSONConfig.md)          | 否    | 0.5小时    | 获取服务端参数进行功能控制                                    |
| [自定义事件（.sendEvent）](sendEvent.md)                        | 否    | 视具体情况而定  | 对于使用自定义事件的场景与触发条件，请与产品人员沟通                       |
| [A/B test（.abtest）](abtest.md)                           | 否    | 0.5小时    | 多方案测试，使用前建议与策划人员沟通                               |
| [分享素材（.onShareAppMessage）](sharing/onshareappmessage.md) | 否    | 0.5小时    | 适用于用户点击右上角菜单的转发按钮时调用                             |
| [分享素材（.shareAppMessage）](sharing/shareappmessage.md)     | 否    | 0.5小时    | 此方式用于小游戏主动分享时调用                                  |
| [分享素材（.getShareTemplates）](sharing/getsharetemplates.md) | 否    | 0.5小时    | 开发者可通过这个接口接收保存在天幕上的分享素材相关数据。                     |
