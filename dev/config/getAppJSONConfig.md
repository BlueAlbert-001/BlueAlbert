# 在线参数 （.getAppJSONConfig）

## 一、概述

本篇为在线参数的开发说明，功能说明请参阅：[在线参数-功能说明](../../game-set/main-features/json.md)

主要实现逻辑为：SDK返回Json类型的参数，前端根据参数值控制游戏内容

## **二、接入方式**

使用SDK的`getAppJSONConfig`接口来实现。

## **三、调用方法**

### **1、直接调用**

```javascript
wx.tmSDK.getAppJSONConfig().then((res) => {
    console.log('在线配置参数:', res);
});
```

### 2、通过指定key获取配置

```javascript
wx.tmSDK.getAppJSONConfig('key').then((res) => {
    console.log('在线配置 key 对应的配置:', res);
});
```

上述的【key】对应为在线参数配置后台中的【参数ID】，将【参数ID】作为传入参数即可获取到对应ID的配置内容

## 四、返回值说明

根据你传入的参数不同，SDK会返回不同的内容

#### 1、当传入的参数为空时

在线参数配置后台如上图所示，参数为空时，会默认将该游戏下配置的所有【参数值Json】中的内容返回。

若配置的内容与实际需求的不相符，请在在线参数配置后台进行修改。

#### 2、当传入的参数为【参数ID】字段值时

将在线参数后台的【配置ID】字段值作为传入参数，会将该ID所对应【参数值Jason】的内容返回。

相关链接：[如何获取用户信息](../../questions/game-manage.md#ru-he-huo-qu-dang-qian-yong-hu-de-ji-ben-xin-xi)
