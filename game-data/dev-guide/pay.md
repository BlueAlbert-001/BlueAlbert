---
description: 针对拥有内购付费游戏的数据回传统计
---

# 内购分析

## 概述

该接口为拥有内购付费功能的游戏提供了内购分析统计的功能，通过回传内购付费相关的数据至天幕中，无需接入天幕SDK的支付功能。天幕可实时分析出内购中新用户付费、首付情况以及新用户内购LTV等指标，提供直接而实时的内购分析参考依据。

内购数据指标请参阅：[内购数据分析指标说明](../indicator-description/in-game-payment.md)

注：由于网络以及其他原因可能导致实际计算的数据与微信官方数据有较小误差，若用于核算等情况时具体结果以微信官方为准。

若接入米大师支付相关接口进行内购统计，请参阅：[米大师支付](../../general-function/midas.md)

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

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">app_id</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x6E38;&#x620F;&#x7684;appid</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x4E8B;&#x4EF6;&#x7C7B;&#x578B;&#xFF0C;&#x7C7B;&#x578B;&#x586B;&#x5199;&#x201C;pay&#x201D;&#xFF08;&#x652F;&#x4ED8;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">pay_amount</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x652F;&#x4ED8;&#x91D1;&#x989D;&#xFF0C;&#x5355;&#x4F4D;&#x4E3A;&#x5206;</td>
    </tr>
    <tr>
      <td style="text-align:left">is_first_pay</td>
      <td style="text-align:left">Boolean</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x662F;&#x5426;&#x9996;&#x6B21;&#x652F;&#x4ED8;&#xFF0C;&#x7528;&#x4E8E;&#x5224;&#x65AD;&#x662F;&#x5426;&#x4E3A;&#x9996;&#x4ED8;&#x7528;&#x6237;</td>
    </tr>
    <tr>
      <td style="text-align:left">uid</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x767B;&#x5F55;&#x8FD4;&#x56DE;&#x7684;&#x7528;&#x6237;&#x5FAE;&#x4FE1;open_id</td>
    </tr>
    <tr>
      <td style="text-align:left">pid</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">&#x5929;&#x5E55;&#x5E73;&#x53F0;&#x7684;&#x7EDF;&#x4E00;&#x7528;&#x6237;&#x552F;&#x4E00;&#x6807;&#x8BC6;&#xFF0C;&#x5DF2;&#x5E9F;&#x5F03;&#xFF0C;&#x65E0;&#x9700;&#x4F20;&#x5165;</td>
    </tr>
    <tr>
      <td style="text-align:left">user_ip</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x7684;IP&#x5730;&#x5740;</td>
    </tr>
    <tr>
      <td style="text-align:left">device_type</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x624B;&#x673A;&#x7CFB;&#x7EDF;&#x7C7B;&#x578B;&#xFF0C;&#x5177;&#x4F53;&#x4E3A;1
        other&#xFF0C;2 IOS&#xFF0C;3 android</td>
    </tr>
    <tr>
      <td style="text-align:left">device_brand</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x624B;&#x673A;&#x54C1;&#x724C;&#xFF0C;&#x4F8B;&#x5982;&#xFF1A;vivo&#x3001;OPPO&#x3001;iPhone&#x3001;HUAWEI</td>
    </tr>
    <tr>
      <td style="text-align:left">device_model</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x624B;&#x673A;&#x673A;&#x578B;&#xFF0C;&#x4F8B;&#x5982;&#xFF1A;iPhone
        6s Plus&#x3001;OPPO A57&#x7B49;</td>
    </tr>
    <tr>
      <td style="text-align:left">net_type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x7F51;&#x7EDC;&#x7C7B;&#x578B;&#xFF0C;&#x4F8B;&#x5982;&#xFF1A;wifi&#x3001;5G&#x3001;4G&#x3001;3G&#x7B49;</td>
    </tr>
    <tr>
      <td style="text-align:left">scene</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x5FAE;&#x4FE1;&#x573A;&#x666F;&#x503C;&#xFF0C;&#x4F8B;&#x5982;&#xFF1A;1001&#x3001;1037&#x3001;1089&#x7B49;</td>
    </tr>
    <tr>
      <td style="text-align:left">order_code</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">&#x8BA2;&#x5355;&#x53F7;&#xFF08;&#x7531;&#x5F00;&#x53D1;&#x8005;&#x751F;&#x6210;&#x7684;&#x8BA2;&#x5355;&#x552F;&#x4E00;&#x6807;&#x8BC6;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">pay_type</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">
        <p>&#x652F;&#x4ED8;&#x65B9;&#x5F0F;&#xFF1A;1 &#x5FAE;&#x4FE1;&#x652F;&#x4ED8;&#xFF0C;
          2 &#x7C73;&#x5927;&#x5E08;&#x652F;&#x4ED8;&#xFF0C;3 h5&#x7B2C;&#x4E09;&#x65B9;&#x652F;&#x4ED8;&#x3002;</p>
        <p>&#x56DE;&#x4F20;&#x540E;h5&#x7B2C;&#x4E09;&#x65B9;&#x652F;&#x4ED8;&#x6570;&#x636E;&#x540E;&#x53EF;&#x5728;
          <a
          href="../../general-function/revenue/">&#x6E38;&#x620F;&#x6536;&#x652F;</a>&#x529F;&#x80FD;&#x4E2D;&#x81EA;&#x52A8;&#x540C;&#x6B65;&#xFF0C;</p>
        <p>&#x5E76;&#x8BA1;&#x7B97;&#x6536;&#x5165;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>### 请求示例

```text
{
  "userLog": {
    "v": "1.0.0",
    "ext": {
      "app_id": "wx1234567891234567",
      "type": "pay",
      "pay_amount": 2000,
      "is_first_pay": true,
      "uid": "oI2nx3EUnScOMVVBJBYq-1234567",
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
| code | Number | 状态码 | 0: 上报成功;10001:参数错误 |
| data | Object | 返回数据 | {} |

#### 响应示例

```text
{
    "code": 0,
    "data": {}
}
```

