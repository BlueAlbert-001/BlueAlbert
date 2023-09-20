# 同步玩家游戏信息(.syncPlayerInfo)

#### 调用方法如下

```javascript
wx.tmSDK.syncPlayerInfo(PLAYER_INFO);
```

参数说明：

```javascript
PLAYER_INFO 类型 Object
参数:  
{
    trackingId: 1,    // Number    同步场景：1 创建角色， 2 进入游戏
    g_uid: '',        // String    玩家角色id
    g_nickname: '',   // String    玩家角色昵称
    g_zone: '',       // String    玩家区服
    g_level: '',      // String    玩家等级
    g_vip_level: '',  // String    玩家VIP等级
}
```

#### 调用示例

<pre class="language-javascript"><code class="lang-javascript">wx.tmSDK.syncPlayerInfo({
<strong>    trackingId: 2,
</strong>    g_uid: '123456',
    g_nickname: '测试',
    g_zone: '1区',
    g_level: '50',
    g_vip_level: '1'
})
    .then(res => {
	console.log(res);
    })
    .catch(err => {
	console.error(err);
    });
</code></pre>
