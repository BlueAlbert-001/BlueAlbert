# .updateUserProfile

{% hint style="info" %}
此接口调用了微信官方wx.getUserInfo获取用户。由于官方登录、获取用户信息将使用新接口，在2021年4月13日后发布的小游戏（小程序）若依然使用wx.getUserInfo将无法获取用户信息。**建议下载2021年3月7日发布的新版天幕微信天幕SDK，并调用本接口获取更新用户信息**。关于微信小程序登录、用户信息相关接口调整说明：[https://developers.weixin.qq.com/community/develop/doc/000cacfa20ce88df04cb468bc52801?blockType=1](https://developers.weixin.qq.com/community/develop/doc/000cacfa20ce88df04cb468bc52801?blockType=1)
{% endhint %}

## ​概述

用于从微信获取用户的昵称头像信息。

{% hint style="info" %}
1. 接入此接口时，注意[兼容性问题](https://doc.skysriver.com/selling/dev-guide/login#2-jian-rong-xing-wen-ti-zhong-yao-1)。
2. 若使用了无登录版天幕SDK，无法使用该接口获取用户信息。
3. 使用该接口，需要下载新版天幕微信SDK（3月7日发布的新版）。
{% endhint %}

## **调用方法** <a href="tiao-yong-fang-fa" id="tiao-yong-fang-fa"></a>

```
wx.tmSDK.updateUserProfile({
refresh: false ,
desc: "更新用户信息" // 默认为更新用户信息，官方要求必填项，声明获取用户个人信息后的用途，后续会展示在弹窗中，请谨慎填写
}).then(res => {});
// refresh 可选 默认为false：不强制拉起授权弹窗，根据缓存时间判断是否拉起授权弹窗。
// true：无论是否有缓存，都会直接拉起授权弹窗
```

## **参数说明** <a href="can-shu-shuo-ming" id="can-shu-shuo-ming"></a>

| 字段    | 是否必填 | 字段类型    | 小程序 | 小游戏 |
| ----- | ---- | ------- | --- | --- |
| fresh | 否    | boolean | 不兼容 | 可调用 |
| desc  | 是    | string  | 可调用 | 可调用 |

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

