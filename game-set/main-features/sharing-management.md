# 分享素材配置

## 概述

本篇为转发素材配置的功能说明，分享素材即分享卡片，您可以通过天幕的分享素材配置自定义不同的分享位以及卡片文案与图片。

开发说明请参阅：[分享素材配置-开发说明](../dev-guide/sharing/)

数据统计查询请参阅：[分享裂变分析](../../game-data/indicator-description/sharing-analysis.md)

## **分享位**

同一小程序/小游戏中，不同位置/功能下的分享，需要配置不同的内容。

天幕中，将这些位置/功能作为不同的分享位进行管理。

![上图可抽象为三个不同的分享位进行管理](https://cdn.61week.com/tianmu/doc/index/image/game-set/sharing-management/1.png)

一款小游戏中的分享场景举例：

| 分享位   | 说明             | 分享位ID          |
| ----- | -------------- | -------------- |
| 右上角分享 | 用户点击右上角...发起分享 | initiative     |
| 首页邀请  | 在首页邀请好友        | indexInvite    |
| 结束页邀请 | 死亡后邀请好友比拼      | gameoverInvite |
| 战绩分享  | 获得历史最高分后炫耀战绩   | highscore      |

## 使用说明

### 配置分享素材

每个转发素材需指定对应的分享位，随后设置分享文案和素材即可。

![选定分享位，然后上传素材](https://cdn.61week.com/tianmu/doc/index/image/game-set/sharing-management/2.png)

### **分享位管理**

点击页面的“分享位管理&接入”，进行分享位的管理

![](https://cdn.61week.com/tianmu/doc/index/image/game-set/sharing-management/3.png)

## 接入

请在“分享位管理&接入”中，点击每个分享位最右侧的“接入”图标，复制弹窗内容，发送给开发人员

![可复制该内容，直接发送开发，提高沟通效率](https://cdn.61week.com/tianmu/doc/index/image/game-set/sharing-management/4.png)

开发说明请参阅：[转发素材配置-开发说明](../dev-guide/sharing/)
