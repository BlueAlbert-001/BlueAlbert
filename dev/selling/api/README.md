# API方式接入广告位

## 接入方式说明

目前天幕广告位接入的方式有两种：

1. 组件化的方式接入（仅支持cocos、laya引擎）
2. api的方式接入

| 广告位类型     | 组件化接入 | **API接入** |
| --------- | ----- | --------- |
| 多Icon广告位  | 支持    | 支持        |
| 浮动窗广告位    | 支持    | 支持        |
| 插屏广告位     | 支持    | 不支持       |
| 伪视频广告位    | 支持    | 不支持       |
| Banner广告位 | 不支持   | 支持        |

{% hint style="warning" %}
我们建议优先使用[组件化的方式](../../../selling/dev-guide/componentization/)接入广告位：

1. 若你的游戏引擎非cocos，laya
2. 或是组件的样式不满足需求（此情况常见于多Icon广告位）

SDK组件无法满足，则可通过API的方式接入。
{% endhint %}

通过API接入，请参照本篇下方的内容完成接入。

{% hint style="info" %}
接入广告位时，所需要的广告位ID（positionID），请在“[卖量助手-流量主游戏管理](../../../selling/main-features/flower-game-manage.md#guang-gao-wei-guan-li)”中获取。
{% endhint %}

涉及到的接口：

* 获取广告位开关：[checkFlowIsOpen](../../../selling/dev-guide/ad-position-status.md)
* 创意配置获取：[getFlowConfig](getflowconfig.md)
* 点击跳转：[flowNavigate](../../../selling/dev-guide/api/landing.md)

## **【重要】接口调用策略**

{% hint style="danger" %}
为保证数据**统计准确性、游戏性能及分发效率**，使用api方式接入广告位，请 **严格按照** 下列说明调用相关接口；否则造成的**相关线上问题带来的后果请自负**！
{% endhint %}

### 1、接口调用步骤

当游戏中需要展示创意的时候：

1. 首先通过调用[`checkFlowIsOpen`](../../../selling/dev-guide/ad-position-status.md)，传入广告位ID，获取广告位开关状态：开启/关闭。
2. 如果广告位为开启状态，调用[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)，传入广告位ID，获取配置。
3. 用户点击跳转时，请使用[`flowNavigate`](flowNavigate.md)实现，请勿使用微信原生接口实现，否则会导致数据统计异常。

### 2、特殊说明

每次调用[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)，对应广告位都会视作**产生曝光**，所以为了数据准确性：

1. 请先获取广告位的开关状态，广告位开启时再调用[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)。
2. **只有**在每次需要展示创意的时候才调用该接口，不要**提前调用**或**缓存上一次的接口返回值，不展示请销毁（但URL及已下载的图片资源建议缓存，见下方说明）**

{% hint style="warning" %}
提前调用，会影响曝光统计的准确性，另外，如果是在游戏loading阶段提前调用上述两个接口，还会应网络请求数量增加导致影响游戏的启动性能！
{% endhint %}

### 3、缓存机制

素材图片本身的缓存：[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)接口返回的是创意素材图片的URL；

请首次下载图片完成后，本地缓存URL及对应的素材图片文件，这样在本次游戏周期中再次调用[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)接口时，如有重复的素材图片（对应同一个URL，即**利用URL作为索引**），**直接从缓存中获取，而非重复下载**。

这可以大大提高素材加载速度，提高分发效率！

（推荐使用引擎自身的图片缓存机制实现）

{% hint style="danger" %}
请注意：

天幕CDN对于图片的网络请求设置了严格的**频次限制**；如因未设置上述缓存机制，导致触发频次限制**无法获取创意图片**，**影响导出效率等后果请自负！**
{% endhint %}

## 浮动窗广告位接入

### **1、type=1**&#x20;

若[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)返回值中type为1时，`positionId`对应的广告位类型是浮动窗类型中的静态图，图片尺寸为：190\*270\
如果创意列表creatives的show\_config中，只有image，则只需渲染该静态图。\


![浮动窗广告效果](<../../../.gitbook/assets/image (40).png>)

### **2、若返回值中存在fps**

如果创意列表`creatives`中有fps，那么对应的广告类型是浮动窗的多帧动图，返回的多个图片素材则需渲染为动态图片，按照fps的值进行**图片轮播**：

> 示例：fps=5，意味着每秒播放5张图片，即0.2秒切换一张

该广告创意实现的效果类似GIF。

### **3、数据刷新规则及点击跳转**

请按照如下说明完成接入：

数据刷新规则请参照：[数据刷新规则](./#shu-ju-shua-xin-gui-ze)

点击后跳转请参照：[点击后跳转](./#dian-ji-hou-tiao-zhuan)

## **多Icon**广告位接入

{% hint style="info" %}
更新说明：此类型广告位，在2020/04/02后，支持多帧动图（返回多张图片，按照指定速率轮播，实现gif效果）
{% endhint %}

### **1、type=7**

若[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)返回值中type为7时，`positionId`对应的是多Icon广告位类型，图片尺寸为：200\*200，请注意，多Icon广告位拥有多个创意，需要全部渲染处理。

{% hint style="danger" %}
这里有个**非常非常非常重要**的注意事项需要说明：

接口返回的创意数组中的内容，是根据**预估收益从高到底进行排序**，请将**排序靠前的创意**展示在**游戏中点击率高**（开发者根据游戏实际情况确定）的位置，以获取最大收益。

因影响广告位的展示效率，接入时建议与游戏策划人员进行沟通，相关链接：[天幕创意下发策略](../../../selling/creative-strategy.md)
{% endhint %}

![多Icon广告效果](<../../../.gitbook/assets/image (41).png>)

### **2、若返回值中存在fps**

如果创意列表`creatives`中有fps，那么对应的广告类型是多Icon的多帧动图，返回的多个图片素材则需渲染为动态图片，按照fps的值进行**图片轮播**：

> 示例：fps=5，意味着每秒播放5张图片，即0.2秒切换一张

该广告创意实现的效果类似GIF。

### **3、数据刷新规则及点击跳转**

请按照如下说明完成接入：

数据刷新规则请参照：[数据刷新规则](./#shu-ju-shua-xin-gui-ze)

点击后跳转请参照：[点击后跳转](./#dian-ji-hou-tiao-zhuan)

## Banner广告位接入

### 1、type=11

若[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)返回值中type为11时，`positionId`对应的是多Icon广告位类型，图片尺寸为：960\*334

### **2、数据刷新规则及点击跳转**

点击后跳转请参照：[点击后跳转](./#dian-ji-hou-tiao-zhuan)

## **数据刷新规则**

{% hint style="info" %}
此部分规则用于自动及用户点击后，刷新创意的显示，以实现最大化创意展示效率；

接入时，只需按下方提示，获取接口数据并展示即可，其他由天幕SDK实现。
{% endhint %}

### **1、自动刷新**

根据`auto_change`的值，自动刷新广告内容。

该“自动刷新”策略，仅适用于[type=1浮动窗广告位](./#fu-dong-chuang-guang-gao-wei-jie-ru)

#### **实现方法**

每次调用[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)，根据`auto_change`的返回值，设置一个Timer，调用[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)，展示接口返回的广告配置。

{% hint style="info" %}
如果要同时实现自动刷新和点击刷新，这里建议，在用户点击触发点击刷新逻辑后，重置这里的timer，避免出现点击刷新后，很快又触发自动刷新的情况。
{% endhint %}

#### **自测方法**

观察游戏中的广告，是否按照接口的返回值自动切换，可通过观察广告图片上的文字内容得知是否切换了广告。

### **2、点击刷新**

该“点击刷新”策略，仅适用于[type=1浮动窗广告位](./#fu-dong-chuang-guang-gao-wei-jie-ru)、[type=7多Icon广告位](./#duo-icon-guang-gao-wei-jie-ru)。

**实现方法**

1. 点击后调用[`flowNavigate`](flowNavigate.md)，利用该接口返回的创意配置刷新显示的创意。

#### **自测方法**

点击游戏中的广告，可通过观察广告图片上的文字内容得知是否切换了广告。

## **点击后跳转**

点击后跳转的功能由SDK实现，开发者只需调用SDK中的[`flowNavigate`](flowNavigate.md)接口，传入对应的广告位ID和创意ID即可。

### 1、创意ID的获取

在调用了[`getFlowConfig`](../../../selling/dev-guide/api/get-ad-position-config.md)后，返回的`creativeId`的值即为创意ID。

（创意ID中包含了要跳转小游戏的appid等信息，无需额外传入appid）

### **2、.flowNavigate**

{% hint style="info" %}
此功能的使用前提：调用了获取广告推广配置的[`getFlowConfig`](getflowconfig.md)；
{% endhint %}

[`flowNavigate`](flowNavigate.md)接口是用于在用户点击了广告位上的创意后，实现跳转到该创意指定的落地页功能。

> 例如，用户在a游戏某广告位上点击了推广b产品的创意，那么在用户点击后，可以跳转至b产品，这个跳转需要通过[`flowNavigate`](flowNavigate.md)接口来实现。
