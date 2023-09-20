# 文本/音频内容安全识别

{% hint style="danger" %}
**！！！接入天幕登录版本SDK才能调用**
{% endhint %}

## 文本内容安全识别

调用方法示例如下

```javascript
wx.tmSDK.msgSecCheck({
    g_chat_type: '跨服', //聊天频道：私聊、跨服、公会、世界等，注：创角可不传该字段
    content: 'hello world!', //文本内容
    scene: 2 //场景枚举值（1 资料；2 评论；3 论坛；4 社交日志）
})
    .then(res => {
        console.log('msgSecCheck', res);
    })
    .catch(err => {
        console.error('msgSecCheck', err);
    });
```

{% hint style="info" %}
具体参数可参考微信文档（注意点：接入后，access\_token和openid无需开发者传参数）

文本内容安全识别：[https://developers.weixin.qq.com/miniprogram/dev/OpenApiDoc/sec-center/sec-check/msgSecCheck.html](https://developers.weixin.qq.com/miniprogram/dev/OpenApiDoc/sec-center/sec-check/msgSecCheck.html)
{% endhint %}

## 音视频内容安全识别

调用方法示例如下

```javascript
wx.tmSDK.mediaCheckAsync({
    media_url: 'https://developers.weixin.qq.com/miniprogram/assets/images/head_global_z_@all.png',
    scene: 1,
    media_type: 2
})
    .then(res => {
        console.log('mediaCheckAsync', res);
    })
    .catch(err => {
        console.error('mediaCheckAsync', err);
    });
```

{% hint style="info" %}
具体参数可参考微信文档（注意点：接入后，access\_token和openid无需开发者传参数）

文本内容安全识别：[https://developers.weixin.qq.com/miniprogram/dev/OpenApiDoc/sec-center/sec-check/mediaCheckAsync.html](https://developers.weixin.qq.com/miniprogram/dev/OpenApiDoc/sec-center/sec-check/mediaCheckAsync.html)
{% endhint %}
