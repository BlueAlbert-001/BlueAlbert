# .login

## 概述

`login`接口用于获取已经存放在天幕平台的用户信息，包含OpenID、头像、昵称、地区等，用做后续业务逻辑判断的依据。（其中头像昵称需要用户授权，详见[授权登录](../../../selling/dev-guide/login/#shou-quan-deng-lu)）

{% hint style="info" %}
1. 接入此接口时，注意[兼容性问题](../../../questions/compatibility.md)
2. 若使用了无登录版天幕SDK，无法使用该接口获取用户信息。
{% endhint %}

## **调用方法**

```java
wx.tmSDK.login().then(res=>{
    console.log(res)
})
```

## **返回值样例**

```java
{
    "pid": "",
    "app_id": "wxa73fd8e544880e89",
    "open_id": "oc7L942AwAqIiBabNYb_cLl7mRsQ",
    "union_id": "",
    "nick_name": "",
    "avatar_url": "",
    "gender": 0,
    "city": "广州",
    "province": "广东省",
    "country": "中国",
    "language": "zh_CN",
    "gold": 0,
    "diamond": 0,
    "share_new": 0,
    "share_times": 0,
    "online_days": 0,
    "online_duration": 0,
    "last_login_time": 1551690740,
    "login_times": 1,
    "from_scene": "1044",
    "from_code": "ball-resurrection-1",
    "is_new": false,
    "ofp": "",
    "jwt": "",
    "login_province": "广东省",
    "login_city": "广州市",
    "login_district": "海珠区"
}
```

## **返回值说明**

| 字段                | 字段类型   | 字段说明                                                                                                                                                                         |
| ----------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| pid               | string | 用户在天幕的统一索引，但可能变化，已废弃                                                                                                                                                         |
| app\_id           | string | 应用的appid                                                                                                                                                                     |
| open\_id          | string | 用户在该应用下的openid                                                                                                                                                               |
| union\_id         | string | 用户的unionid，默认为空字符串。[union\_id获取方法](https://developers.weixin.qq.com/minigame/dev/guide/open-ability/union-id.html)                                                           |
| nick\_name        | string | 用户的微信昵称，为空时需要调用 [`updateUserinfo`](../../../selling/dev-guide/login/update-userinfo.md) 获取                                                                                   |
| avatar\_url       | string | 用户的微信头像，为空时需要调用 [`updateUserinfo`](../../../selling/dev-guide/login/update-userinfo.md) 获取                                                                                   |
| gender            | number | 男：1 / 女：0                                                                                                                                                                    |
| language          | string | 用户微信中设置的语言                                                                                                                                                                   |
| city              | string | 用户微信中设置的城市                                                                                                                                                                   |
| province          | string | 用户微信中设置的省份                                                                                                                                                                   |
| country           | string | 用户微信中设置的国家                                                                                                                                                                   |
| gold、diamond      | string | 游戏内金币、钻石，已废弃                                                                                                                                                                 |
| share\_new        | number | 用户在当前游戏的分享引入新用户的数量                                                                                                                                                           |
| share\_times      | number | 用户在当前游戏的分享次数                                                                                                                                                                 |
| online\_days      | number | 用户在当前游戏在线的天数                                                                                                                                                                 |
| online\_duration  | number | 累计在线时长（单位：秒）                                                                                                                                                                 |
| last\_login\_time | number | 最近一次访问的时间戳                                                                                                                                                                   |
| login\_times      | number | 用户在当前游戏的累计登录访问次数                                                                                                                                                             |
| from\_scene       | string | 来源场景值                                                                                                                                                                        |
| from\_code        | string | 来源[渠道ID](../../../channel/main-features/channel-management.md)                                                                                                               |
| is\_new           | bool   | 是否新注册的用户                                                                                                                                                                     |
| login\_province   | string | 根据用户ip判断用户所在的省份（注意：返回的省份名称与[行政划分](https://baike.baidu.com/item/%E8%A1%8C%E6%94%BF%E5%8C%BA%E5%88%92/4655526?fr=aladdin#3\_3)的名称一致，如西藏，返回的是西藏自治区。若要实现地区屏蔽功能，建议根据返回值前两位进行地区匹配） |
| login\_city       | string | 根据用户ip判断用户所在的城市                                                                                                                                                              |
| login\_district   | string | 根据用户ip判断用户所在的区县                                                                                                                                                              |

