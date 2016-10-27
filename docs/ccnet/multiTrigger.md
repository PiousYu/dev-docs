multipleTrigger
=============================
**NOTE:** 此文章主要介绍ccnet中multipleTrigger触发器用法。
## multipleTrigger
multipleTrigger支持多个触发器一起使用，条件有Or And

### 参数
* operator 操作条件

 值：Or 或者 And 并且
 
 默认值：Or
* triggers 触发器块
 
在此元素内可以添加多个触发器。

### 举例

* 周天23:30-23:45 每30s强制执行。
 
 ```
<multiTrigger operator="And">
<triggers>
<urlTrigger url="http://server/page.html" seconds="30" buildCondition="ForceBuild" />
<filterTrigger startTime="23:30" endTime=“23:45”>
<trigger type="IntervalTrigger" name="cc" seconds="60"  />
<weekDays>
<weekDay>Sunday</weekDay>
</weekDays>
</trigger>
</filterTrigger>
</triggers>
</multiTrigger>
```

 