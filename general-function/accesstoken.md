# 获取accessToken

## 一、概述

accesstoken为获取小游戏全局唯一后台接口调用凭据，接入天幕SDK后会每小时定时刷新accesstoken。为避免开发者也调用accesstoken时与天幕冲突，开发者可以调用此接口获取access_token。

## 二、接口说明

### 1、 请求地址与方式

{% hint style="info" %}
请求地址：[https://api.kuaiyugo.com/api/config/v1/programs/:programId/accesstoken](https://api.kuaiyugo.com/api/config/v1/programs/:programId/accesstoken)

请求方式：GET
{% endhint %}

### 2、 请求参数

| 参数        | 类型     | 是否必填 | 最大长度 | 描述                      | 示例值                              |
| --------- | ------ | ---- | ---- | ----------------------- | -------------------------------- |
| programId | String | 是    | 32   | 天幕授权项目的唯一标识，可在游戏管理后台中获取 | 223fc70098ad11e9a5898928ba7882e6 |

### 3、 公共响应参数

| 参数   | 类型     | 描述    | 示例值                                        |
| ---- | ------ | ----- | ------------------------------------------ |
| err  | Number | 状态码   | 0 更新成功；非0 更新异常                             |
| msg  | String | 状态码描述 | 请求成功                                       |
| data | Object | 返回数据  | <p>{</p><p>"accessToken": ""</p><p>}</p> |

### 4、 响应参数

| 参数          | 类型     | 描述              | 示例值                                                                                                                                                                                       |
| ----------- | ------ | --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| accessToken | String | 返回的access_token | <p>27_t3e8Pqc7RzC1V8UB3rSC9GdryVrB0LcOxi3D4e614</p><p>Rg5d_3sUkLbHZX8skLCecrIpjOfQ4YY_AUHn6XogMHFd</p><p>1Lt4W85aSrfIOcr3bpZvKP798hLHuJd7NNt5i96m9526</p><p>EZk8SafcTKoKIJUaAGASTE</p> |

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
