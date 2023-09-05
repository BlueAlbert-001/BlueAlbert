# 悬浮窗

## 一、概述

悬浮窗功能

## 二、接入方式

#### &#x20;组件化接入方式（.floatingCustomer）

```javascript
 let data = {}; // 参数可选，默认可不传
 data = {
  width: 80,  // 设置浮动ICON的宽 按照实际画布尺寸相对普通微信视图尺寸缩放宽 可选 默认：80
  height: 80,  // 设置浮动ICON的高 按照实际画布尺寸相对普通微信视图尺寸缩放宽 可选 默认：80
  zIndex: 999999999, // 设置浮动ICON的层级 可选 默认：999999999
  left: 10, // 设置浮动ICON 左边距离画布的位置 可选 默认：左下角
  top: 10 // 设置浮动ICON 顶部距离画布的位置 可选 默认：左下角
 };

// ICON只能存在一个，保存创建后的返回对象，场景转换需要调用销毁
this.Floating = wx.tmSDK.floatingCustomer(data); 

// 销毁浮动icon
if (this.Floating) {
   this.Floating.destroy();
   this.Floating = null;
}
```

#### API方式接入（.getFloatingCustomerConfig）

```javascript
wx.tmSDK.getFloatingCustomerConfig()
    .then(res => {
        console.log(res);
    });

// 点击图片跳转客服时调用此方法
wx.openCustomerServiceConversation({
    showMessageCard: true,
    sessionFrom: c_param,
    sendMessageTitle: card_title,
    sendMessageImg: card_img
})
```

返回参数说明

```javascript
{
  "c_flag": true, // 外层关闭按钮的开关
  "icon": "", // 外层的icon
  "d_flag": true, // 红点开关
  "child_node":[
    // 客服跳转类型
    {
      "b_title":"按钮1", // 弹窗内层按钮的文案
      "img":"", // 弹窗内层展示的图片
      "card_img":"", // 客服消息-显示的卡片图片
      "card_title":"", // 客服消息-显示的卡片标题
      "c_param":"", // 内层跳转客服的消息
      "type": "", // custom(客服跳转-联系客服)、h5game(客服跳转-H5版游戏链接)、other(客服跳转-其它)
    },
    // 图片类型
    {
      "b_title":"按钮1", // 弹窗内层按钮的文案
      "img":"", // 弹窗内层展示的图片
      "type": "image", // 图片类型无跳转客服
    },
    // 邮件类型
    {
      "b_title":"邮件",  // 弹窗内层按钮的文案
      "content":"", // 邮件内容：邮件内容类型为1时为邮件内容、邮件内容类型为2时为图片链接
      "content_type": 1, // 邮件内容类型：1 纯文案内容 2 纯图片内容
      "id": 0, // 邮件ID，当有新邮件时候ID会更新，开发者自行轮询接口获取新邮件，根据ID判断提醒玩家
      "show_start_time": "", // 邮件发送时间
      "title": "", // 邮件标题
      "type": "image", // 邮件类型
    }
  ]
}
```
