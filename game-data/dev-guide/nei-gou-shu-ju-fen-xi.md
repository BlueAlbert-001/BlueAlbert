---
description: 针对拥有内购付费游戏的数据回传统计
---

# 内购数据分析

## 概述

该接口为拥有内购付费功能的游戏提供了内购分析统计的功能，通过回传内购付费相关的数据至天幕中，天幕可实时分析出内购中新用户付费、首付情况以及新用户内购LTV等指标，提供直接而实时的内购分析参考依据。

注：由于网络以及其他原因可能导致实际计算的数据与微信官方数据有较小误差，若用于核算等情况时具体结果以微信官方为准。

## 接口说明

### 请求地址与方式

{% hint style="info" %}
请求地址：[https://h5game-log.kuaiyugo.com/dataAnalysis/saveUserBehaviorLogV2](https://h5game-log.kuaiyugo.com/dataAnalysis/saveUserBehaviorLogV2)

请求方式：POST
{% endhint %}

### 请求参数

#### header 参数

| 参数 | 示例值 |
| :--- | :--- |
| Content-Type | application/json |

#### 请求参数

| 参数 | 类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| userLog | Object | 是 | 支付数据对象 |

useLog的参数

| 参数 | 类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| v | String | 是 | 由开发者定义的回传数据版本号，建议从1.0.0开始 |
| ext | Object | 是 | 支付数据对象详情对象，记录各种支付相关的数据字段 |

ext的参数

| 参数 | 类型 | 是否必填 | 描述 |
| :--- | :--- | :--- | :--- |
| app\_id | String | 是 | 游戏的appid |
| type | String | 是 | 事件类型，类型填写“pay”（支付） |
| pay\_amount | Number | 是 | 支付金额，单位为分 |
| is\_first\_pay | Boolean | 是 | 是否首次支付，用于判断是否为首付用户 |
| uid | String | 是 | 登录返回的用户微信open\_id |
| pid | String | 否 | 天幕平台的统一用户唯一标识，已废弃，无需传入 |
| user\_ip | String | 是 | 用户的IP地址 |
| device\_type | Number | 是 | 手机系统类型，具体为1 other，2 IOS，3 android |
| device\_brand | String | 是 | 手机品牌，例如：vivo、OPPO、iPhone、HUAWEI |
| device\_model | String | 是 | 手机机型，例如：iPhone 6s Plus、OPPO A57等 |
| net\_type | String | 是 | 网络类型，例如：wifi、5G、4G、3G等 |
| scene | String | 是 | 微信场景值之，例如：1001、1037、1089等 |
| order\_code | String | 是 | 订单号（由开发者生成的订单唯一标识） |
| pay\_type | Number | 是 | 支付方式：1 微信支付， 2 米大师支付，3 h5第三方支付，用于区分不同支付方式进行数据分析 |

### 请求示例

```text
{
  "userLog": {
    "v": "1.0.0",
    "ext": {
      "app_id": "wx54a500095eba26d9",
      "type": "pay",
      "pay_amount": 2000,
      "is_first_pay": true,
      "uid": "oI2nx3EUnScOMVVBJBYq-sk0KzhQ",
      "pid": "e496a4d0-1662-11ea-b3aa-cdab23d31c7a",
      "user_ip": "113.105.0.58",
  	  "device_type": 3,
      "device_brand": "OPPO",
      "device_model": "OPPO A57",
      "net_type": "4G",
      "scene": "1047",
  	  "order_code": "74a3a21ffca9b09d8def90a54a3014ca",
      "pay_type": 2
    }
  }
}
```

### 公共响应参数

| 参数 | 类型 | 描述 | 示例值 |
| :--- | :--- | :--- | :--- |
| code | Number | 状态码 | 0 上报成功 |
| data | Object | 返回数据 | {} |

#### 响应示例

```text
{
    "code": 0,
    "data": {}
}
```

