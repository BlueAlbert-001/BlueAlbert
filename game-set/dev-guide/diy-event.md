# 自定义事件 （.sendEvent）

## 概述

本篇为自定义事件的开发说明，功能说明请参阅：[自定义事件-功能说明](../main-features/diy-event.md)

主要实现逻辑为：在需要埋点上报的事件触发后，利用SDK接口上报事件ID、及事件中参数的具体值；天幕会根据事件ID统计事件触发次数，及事件下不同参数值的触发次数。

## 接入方式

使用SDK的`sendEvent` 记录并上报自定义事件

{% hint style="info" %}
对于使用自定义事件的场景与触发条件，请与产品人员沟通
{% endhint %}

## **调用方法**

![](../../.gitbook/assets/image%20%28320%29.png)

```java
//事件触发
wx.tmSDK.sendEvent('clickStartButton', {
});
//事件触发
wx.tmSDK.sendEvent('buyStuff', { //buyStuff为后台配置的事件ID
    brand: 'CASIO', //brand为后台配置的参数ID，CASIO为开发者传入的对应参数值
    productName: '计算器' //事件ID与参数ID仅可传天幕自定义事件后台配置的ID
});
```

{% hint style="info" %}
事件部分代码请在后台“天幕——游戏配置——自定义事件”中复制，开发者仅需填充事件中参数的值。
{% endhint %}

{% hint style="info" %}
（1）简单的事件可以不包含参数。

（2）调用方法中的内容简释如下，请注意以下ID必须使用天幕自定义事件后台配置的id：

* ‘buyStuff’为后台配置的事件ID；
* ‘brand’，’productName‘为后台配置的参数ID；
* 'CASIO'，'计算器'为各参数对应的参数值，即需要开发者传入的内容。

（3）事件ID、参数ID仅支持英文、数字与下划线，最多32个字符。
{% endhint %}

{% hint style="danger" %}
（1）事件中的参数一定要在后台事先配置，未配置但上传了的参数都会被归类为未定义参数，将统计不到对应参数的数据。

（2）若上报的参数ID与后台配置的参数ID不一致，系统为保证安全将过滤后台与上报不一致的参数ID以及第一点中后台未事先配置的参数ID，同时不统计计算这些未定义参数的数据。
{% endhint %}

{% hint style="danger" %}
请注意：

1. 如果本次触发事件与上次触发事件的时间间隔小于1秒而且触发次数大于10次，则禁止触发事件，防止上报次数过于频繁（SDK会自行进行过滤）
2. value长度不能大于128
3. key的长度不能大于16
4. data\(自定义事件参数对象\)中每个值不能为undefined,null,NaN
5. data\(自定义事件参数对象\)中每个值的类型必须为Number或者String
6. data\(自定义事件参数对象\)通过字符串转化处理后的长度不超过512
{% endhint %}

## 异常提示

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
      <td style="text-align:left">message</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x9519;&#x8BEF;&#x63CF;&#x8FF0;</td>
      <td style="text-align:left">
        <p>100100&#xFF1A;&#x4E8B;&#x4EF6;id&#x5FC5;&#x987B;&#x4E3A;&#x975E;&#x7A7A;&#x5B57;&#x7B26;&#x4E32;&#xFF1B;</p>
        <p>100101&#xFF1A;&#x81EA;&#x5B9A;&#x4E49;&#x4E8B;&#x4EF6;&#x53C2;&#x6570;data&#x957F;&#x5EA6;&#x4E0D;&#x80FD;&#x8D85;&#x8FC7;512&#xFF1B;</p>
        <p>100102&#xFF1A;data&#x53C2;&#x6570;&#x4E2D;&#x7684;value&#x503C;&#x90FD;&#x4E0D;&#x80FD;&#x4E3A;undefined/null/NaN&#xFF1B;</p>
        <p>100103&#xFF1A;key&#x7684;&#x503C;&#x5FC5;&#x987B;&#x4E3A;Number&#x6216;&#x8005;String&#x7C7B;&#x578B;&#xFF1B;</p>
        <p>100104&#xFF1A;value&#x7684;&#x503C;&#x5FC5;&#x987B;&#x4E3A;Number&#x6216;&#x8005;String&#x7C7B;&#x578B;&#xFF1B;</p>
        <p>100105&#xFF1A;key&#x7684;&#x957F;&#x5EA6;&#x4E0D;&#x80FD;&#x8D85;&#x8FC7;16&#xFF1B;</p>
        <p>100106&#xFF1A;value&#x957F;&#x5EA6;&#x4E0D;&#x80FD;&#x8D85;&#x8FC7;128&#xFF1B;</p>
        <p>100107&#xFF1A;data&#x53C2;&#x6570;&#x4E3A;&#x7A7A;&#xFF0C;&#x8BF7;&#x4F20;&#x5165;data&#x53C2;&#x6570;&#xFF1B;</p>
        <p>&#x6BCF;&#x79D2;&#x949F;&#x4E0D;&#x80FD;&#x8C03;&#x7528;&#x8D85;&#x8FC7;10&#x6B21;&#xFF1B;</p>
      </td>
    </tr>
  </tbody>
</table>

