# 准备工作（必读）

## 任务清单

* [ ] SDK接入
* [ ] 登录（可选）
* [ ] SDK初始化
* [ ] 接入广告位（API or 组件化）

## Step1

{% hint style="info" %}
为了更好的理解文档，建议开发人员首先快速浏览：[名词解释——卖量助手](../glossary.md#2-mai-liang-zhu-shou)
{% endhint %}

要完整使用天幕的卖量助手，需要进行SDK的接入，请参阅：

{% content-ref url="basic/add-ask.md" %}
[add-ask.md](basic/add-ask.md)
{% endcontent-ref %}

## Step2

SDK接入完成后，在使用某些接口时，需要进行SDK的初始化，另外，游戏可能需要获取用户头像昵称等信息（登录流程），请参阅：

{% content-ref url="basic/initialization.md" %}
[initialization.md](basic/initialization.md)
{% endcontent-ref %}

{% content-ref url="basic/login/" %}
[login](basic/login/)
{% endcontent-ref %}

1. 未接入天幕登录功能（或使用无登录版SDK时未发送uid）导致卖量功能无法使用
2. 未按照正确SDK接入说明引入SDK文件导致异常或广告展示异常；
3. 未初始化导致广告未展示；

## Step3

{% hint style="info" %}
卖量助手的SDK接入工作主要为：接入广告位；

开始接入前，建议开发人员快速浏览：[广告位说明](../selling/ad-types/)；
{% endhint %}

请参阅以下内容：

{% content-ref url="selling/componentization/" %}
[componentization](selling/componentization/)
{% endcontent-ref %}

{% content-ref url="selling/api/" %}
[api](selling/api/)
{% endcontent-ref %}

{% content-ref url="selling/checkFlowIsOpen.md" %}
[checkFlowIsOpen.md](selling/checkFlowIsOpen.md)
{% endcontent-ref %}

## 其他

### 开发Demo

开发demo，请参阅：

{% content-ref url="../selling/dev-guide/dev-demo.md" %}
[dev-demo.md](../selling/dev-guide/dev-demo.md)
{% endcontent-ref %}

### 技术支持

接入过程中有任何问题，欢迎微信扫描下方二维码，咨询天幕对接人员

![](../.gitbook/assets/README-3.jpg)
