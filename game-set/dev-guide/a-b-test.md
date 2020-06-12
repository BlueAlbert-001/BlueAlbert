# A/B test

## 概述

本篇为A/Btest的开发说明，功能说明请参阅：[A/Btest-功能说明](../main-features/ab-test.md)

主要实现逻辑为：通过在需要触发A/Btest的事件前，调用SDK接口，获取当前用户的所在的策略组，根据约定，不同策略组生效不同的对应逻辑（如策略组1为红色按钮、策略组2位绿色按钮）。

## 接入方式

 使用SDK的`abtest`接口来实现。

接入天幕SDK后，只要游戏配置-ABtest后台中配置了ABtest信息，完成配置后开发者根据配置的计划ID、用户策略组ID设计相应的功能逻辑，游戏即会根据配置信息生效进行用户分组。

### 使用示例

使用前，请在【游戏配置-A/B test 】中创建相关的测试计划。传入需要接入的测试计划ID 即plan\_id。

```text
let plan_id = 22;
wx.tmSDK.abtest(plan_id).then(res => {
    console.log(res);
});
```

### 返回值说明

传入测试计划ID后，会返回在对应计划下当前用户所属的策略组ID `group_id`

返回值的格式如下：

```text
{
   "planId": "123",
   "groupId": "group1"
}
    // 不存在则返回：{}
```

 注意：若传入的`plan_id`不存在，会返回空值。

