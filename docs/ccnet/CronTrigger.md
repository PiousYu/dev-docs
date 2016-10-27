cronTrigger 触发器
====================================
**NOTE:** 此文章主要介绍ccnet中crontrigger触发器用法。

## Cron Trigger
cronTrigger 触发器支持日历重复间隔触发。
### 参数

* buildCondition 触发build条件

 值：NoBuild 不执行 IfModificationExists 改变时执行 ForceBuild 强制执行
* cronExpression 时间条件

 参数依次：Minutes Hours Days Months Days-of-Week
 eg:
 
 ```
<cronExpression>* * 1 1 *</cronExpression>
```

* name 名字

 触发器的名字
 
### 举例
* 1.每年的一月一号触发。
```
<cronTrigger>
<cronExpression>* * 1 1 *</cronExpression>
</cronTrigger>
```
* 2.每天6点到18点之间没5分钟触发一次
 ```
<cronTrigger>
<cronExpression>0/5 6-18 * * *</cronExpression>
</cronTrigger>
```

* 3.每天6点到18点之间没5分钟触发一次
 ```
<cronTrigger buildCondition=“ForceBuild”>
<cronExpression>0/5 6-18 * * *</cronExpression>
</cronTrigger>
```
* 4.每天6点到18点之间没5分钟检查一次，版本变化触发一次
 ```
<cronTrigger buildCondition=“IfModification”>
<cronExpression>0/5 6-18 * * *</cronExpression>
</cronTrigger>
```
