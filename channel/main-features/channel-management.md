# 渠道管理

## 一、概述

管理当前主体下所有的渠道，帮助对渠道进行数据统计与合作渠道管理。主要分为两个功能：渠道的创建，渠道商的管理。

{% hint style="info" %}
建议首先阅读：[渠道相关名词解释](https://doc.skysriver.com/glossary#3-mai-liang-zhu-shou)
{% endhint %}

## 二、功能介绍

天幕买量助手的渠道管理分成两级，一级为渠道商，二级为媒体。

* **渠道商**：即合作的公司，例如您与腾讯合作，此时腾讯为合作的渠道商。
* **媒体**：具体的合作产品，即实际的下游戏。例如腾讯使用腾讯桌球与您合作，腾讯桌球即为一个媒体。
* **渠道ID**：每个渠道ID代表一个渠道商-媒体的关系，例如腾讯-腾讯桌球的渠道ID为XXXXXX，腾讯-跳一跳的渠道ID为XXXXXA。 渠道ID是针对渠道商-媒体的唯一ID，可在渠道管理中配置自动生成。

买量助手使用流程：[点击查看](https://cdn.kuaiyugo.com/tianmu/cms/2019-10-18_a5175a00f16611e9aa8c2517a70a9608.jpg)

## 三、渠道创建

### 1. 渠道的创建与渠道ID的生成

点击【创建渠道】，进入渠道创建的弹窗，进行信息填写，按页面提示信息填写，点击保存后生成渠道ID。

![&#x6E20;&#x9053;&#x7BA1;&#x7406;&#x83DC;&#x5355;&#x4E2D;&#x6E20;&#x9053;&#x5217;&#x8868;](../../.gitbook/assets/image%20%2893%29.png)

![&#x521B;&#x5EFA;&#x6E20;&#x9053;&#x64CD;&#x4F5C;&#x5F39;&#x7A97;](../../.gitbook/assets/image%20%2826%29.png)

### 2. 渠道路径的生成

在创建渠道操作时，您可以设置跳转路径。

*  默认为page/index/index,创建后将自动添加天幕系统的渠道参数，参数中包含渠道ID
* 若您的产品非默认路径，请填写您的默认路径，我们将会自动添加天幕的渠道ID等参数
* 若您未填写路径，则使用默认路径

比如您除了使用天幕统计，还是用了微信官方的统计，只需将微信官方的路径填写，我们的系统将会在微信的路径后自动添加天幕的参数用于统计。

您填写了微信路径，例如：page/index/index?wxgamecid=CCAAAAookkQQ997\_wwwwww，则生成的完整路径为：page/index/index?wxgamecid=CCAAAAookkQQ997\_wwwwww&channelCode=xxxxx。

若您使用了超过两家以上的统计平台，每家平台的参数都可以通过“&”进行连接。

若您的默认路径不为page/index/index，只需替换为您的默认路径，我们的系统同样会自动添加上天幕的统计参数。

### 3. 渠道信息的发送

点击操作中的发送渠道物料功能后会弹出一个窗口由您确认渠道投放产品等信息是否有误，可点击预览链接查看网页中呈现的信息，确认无误后点击复制链接即可将物料网页发送给合作方。

![&#x53D1;&#x9001;&#x6E20;&#x9053;&#x7269;&#x6599;&#x529F;&#x80FD;&#x5165;&#x53E3;](../../.gitbook/assets/image%20%2869%29.png)

![&#x786E;&#x8BA4;&#x7269;&#x6599;&#x4FE1;&#x606F;](../../.gitbook/assets/image%20%28163%29.png)

## 四、渠道商管理

渠道商管理功能可以帮助管理各种投放渠道的渠道商，不管渠道商再多，也可进行统一管理。

### 渠道商的创建与管理

![](../../.gitbook/assets/image%20%28188%29.png)

创建一个渠道商仅需要填写全称、简称，媒体可在需要时添加。

![&#x521B;&#x5EFA;&#x6E20;&#x9053;&#x5546;](../../.gitbook/assets/image.png)

{% hint style="info" %}
拓展阅读：[渠道商与开放数据管理](https://doc.skysriver.com/channel/main-features/distributor)
{% endhint %}
