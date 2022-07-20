---
description: 针对拥有内购付费游戏的数据回传统计
---

# 内购分析

## 一、概述

该接口为拥有内购付费功能的游戏提供了内购分析统计的功能，通过回传内购付费相关的数据至天幕中，无需接入天幕SDK的支付功能。天幕可实时分析出内购中新用户付费、首付情况以及新用户内购LTV等指标，提供直接而实时的内购分析参考依据。

内购数据指标请参阅：[内购数据分析指标说明](../indicator-description/in-game-payment.md)

注：由于网络以及其他原因可能导致实际计算的数据与微信官方数据有较小误差，若用于核算等情况时具体结果以微信官方为准。

{% hint style="danger" %}
<mark style="color:red;">**注意：只有在未接入天幕SDK的支付功能，才可以调用该接口，如果接入了天幕SDK的支付功能，则不可以再调用该接口。**</mark>
{% endhint %}

## 二、接口说明

### 1、 请求地址与方式

{% hint style="info" %}
请求地址：[https://h5game-log.kuaiyugo.com/dataAnalysis/saveUserBehaviorLogV2](https://h5game-log.kuaiyugo.com/dataAnalysis/saveUserBehaviorLogV2)

请求方式：POST
{% endhint %}

### 2、 请求参数

#### header 参数

| 参数           | 示例值              |
| ------------ | ---------------- |
| Content-Type | application/json |

#### 请求参数

| 参数      | 类型     | 是否必填 | 描述     |
| ------- | ------ | ---- | ------ |
| userLog | Object | 是    | 支付数据对象 |

useLog的参数

| 参数  | 类型     | 是否必填 | 描述                        |
| --- | ------ | ---- | ------------------------- |
| v   | String | 是    | 由开发者定义的回传数据版本号，建议从1.0.0开始 |
| ext | Object | 是    | 支付数据对象详情对象，记录各种支付相关的数据字段  |

ext的参数

| 参数             | 类型      | 是否必填 | 描述                                                                                                                                                                                   |
| -------------- | ------- | ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| app\_id        | String  | 是    | 游戏的appid                                                                                                                                                                             |
| type           | String  | 是    | 事件类型，类型填写“pay”（支付）                                                                                                                                                                   |
| pay\_amount    | Number  | 是    | 支付金额，单位为分                                                                                                                                                                            |
| is\_first\_pay | Boolean | 是    | 是否首次支付，用于判断是否为首付用户                                                                                                                                                                   |
| uid            | String  | 是    | 登录返回的用户open\_id                                                                                                                                                                      |
| user\_ip       | String  | 是    | 用户的IP地址                                                                                                                                                                              |
| order\_code    | String  | 是    | 订单号（由开发者生成的订单唯一标识）                                                                                                                                                                   |
| pay\_type      | Number  | 是    | <p>支付方式： 2 米大师支付，3 第三方支付。</p><p>回传后第三方支付数据后可在<a href="../../general-function/revenue/">游戏收支</a>功能中自动同步，</p><p>并计算收入，无需人工上传。</p><p>对于微信和QQ平台小游戏，官方支付类型为米大师支付，<br>除米大师支付外均选择第三方支付。</p> |
| device\_type   | Number  | 是    | 手机系统类型，具体为1 other，2 IOS，3 android                                                                                                                                                    |
| device\_brand  | String  | 否    | 手机品牌，例如：vivo、OPPO、iPhone、HUAWEI                                                                                                                                                      |
| device\_model  | String  | 否    | 手机机型，例如：iPhone 6s Plus、OPPO A57等                                                                                                                                                     |
| net\_type      | String  | 否    | 网络类型，例如：wifi、5G、4G、3G等                                                                                                                                                               |
| scene          | String  | 否    | 各平台场景值，例如：微信中的1001、1037、1089等                                                                                                                                                        |
| zone           | String  | 否    | 游戏内区服，例如：北京一服，华东一区等                                                                                                                                                                  |
| goods\_name    | String  | 否    | 商品名称，例如：10钻石、1000金币、1张月卡等                                                                                                                                                            |
| game\_uid      | String  | 否    | 玩家游戏内ID                                                                                                                                                                              |
| game\_nickname | String  | 否    | 玩家游戏内昵称                                                                                                                                                                              |

### 3、 请求示例

```
{
  "userLog": {
    "v": "1.0.0",
    "ext": {
      "app_id": "wx1234567891234567",
      "type": "pay",
      "pay_amount": 2000,
      "is_first_pay": true,
      "uid": "oI2nx3EUnScOMVVBJBYq-1234567",
      "user_ip": "113.105.0.58",
      "device_type": 3,
      "device_brand": "OPPO",
      "device_model": "OPPO A57",
      "net_type": "4G",
      "scene": "1047",
      "order_code": "74a3a21ffca9b09d8def90a54a3014ca",
      "pay_type": 2，
      "zone": "华东大区1服"，
      "goods_name": "20钻石"，
      "game_uid": "1d45s23s2"，
      "game_nickname": "轻舞飞扬"
    }
  }
}
```

### 4、 公共响应参数

| 参数   | 类型     | 描述   | 示例值                |
| ---- | ------ | ---- | ------------------ |
| code | Number | 状态码  | 0: 上报成功;10001:参数错误 |
| data | Object | 返回数据 | {}                 |

#### 响应示例

```
{
    "code": 0,
    "data": {}
}
```
