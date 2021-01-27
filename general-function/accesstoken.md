# 获取accessToken

## 一、概述

accesstoken为获取小游戏全局唯一后台接口调用凭据，接入天幕SDK后会每小时定时刷新accesstoken。为避免开发者也调用accesstoken时与天幕冲突，开发者可以调用此接口获取access\_token。

## 二、接口说明

### 1、 请求地址与方式

{% hint style="info" %}
请求地址：[https://api.kuaiyugo.com/api/config/v1/programs/:programId/accesstoken](https://api.kuaiyugo.com/api/config/v1/programs/:programId/accesstoken)

请求方式：GET
{% endhint %}

### 2、 请求参数

| 参数 | 类型 | 是否必填 | 最大长度 | 描述 | 示例值 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| programId | String | 是 | 32 | 天幕授权项目的唯一标识，可在游戏管理后台中获取 | 223fc70098ad11e9a5898928ba7882e6 |

### 3、 公共响应参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
      <th style="text-align:left">&#x793A;&#x4F8B;&#x503C;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">err</td>
      <td style="text-align:left">Number</td>
      <td style="text-align:left">&#x72B6;&#x6001;&#x7801;</td>
      <td style="text-align:left">0 &#x66F4;&#x65B0;&#x6210;&#x529F;&#xFF1B;&#x975E;0 &#x66F4;&#x65B0;&#x5F02;&#x5E38;</td>
    </tr>
    <tr>
      <td style="text-align:left">msg</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x72B6;&#x6001;&#x7801;&#x63CF;&#x8FF0;</td>
      <td style="text-align:left">&#x8BF7;&#x6C42;&#x6210;&#x529F;</td>
    </tr>
    <tr>
      <td style="text-align:left">data</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x8FD4;&#x56DE;&#x6570;&#x636E;</td>
      <td style="text-align:left">
        <p>{
          <br />
        </p>
        <p>&quot;accessToken&quot;:&#xA0;&quot;&quot;
          <br />
        </p>
        <p>}</p>
      </td>
    </tr>
  </tbody>
</table>

### 4、 响应参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
      <th style="text-align:left">&#x793A;&#x4F8B;&#x503C;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">accessToken</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8FD4;&#x56DE;&#x7684;access_token</td>
      <td style="text-align:left">
        <p>27_t3e8Pqc7RzC1V8UB3rSC9GdryVrB0LcOxi3D4e614
          <br />
        </p>
        <p>Rg5d_3sUkLbHZX8skLCecrIpjOfQ4YY_AUHn6XogMHFd
          <br />
        </p>
        <p>1Lt4W85aSrfIOcr3bpZvKP798hLHuJd7NNt5i96m9526
          <br />
        </p>
        <p>EZk8SafcTKoKIJUaAGASTE</p>
      </td>
    </tr>
  </tbody>
</table>

### 5、 请求与响应示例

#### 请求示例

> https://api.kuaiyugo.com/api/config/v1/programs/223fc70098ad11e9a5898928ba7882e6/accesstoken

#### 响应示例

```javascript
{
    "err": 0,
    "data": {
        "accessToken": "27_t3e8Pqc7RzC1V8UB3r-SC9GdryVrB0LcOxi3D4e614Rg5d_3sUkLbHZX8sk-LCecrIpjOfQ4YY_AUHn6XogMHFd1Lt4W85aSrfIOcr3bpZvKP798hLHuJd7NNt5i96m9526EZk8SafcTKoKIJUaAGASTE"
    },
    "msg": "请求成功"
}
```

