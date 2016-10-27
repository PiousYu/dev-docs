filterTrigger
==========================================
**NOTE:** 此文章主要介绍ccnet中filterTrigger触发器用法。
## filterTrigger
filterTrigger 是过滤触发器，必须和trigger合用。
### 参数

* buildCondition 触发build条件

 值：NoBuild 不执行 IfModificationExists 改变时执行 ForceBuild 强制执行
 
* endTime 结束时间

 默认值：23:59:59
 
* startTime 开始时间
 默认值： 00:00:00
 
* trigger 触发器块
 指定触发器，可以指定任意类型触发器。
 
* weekDays 过滤星期
* 
 值： Sunday
 
 Monday
     
     Tuesday
     
     Wednesday
     
     Thursday
     
     Friday
     
     Saturday
### 举例
* 周天 23:30-23:45 每隔60s执行一次
```
<filterTrigger startTime="23:30" endTime=“23:45”>
     <trigger type="IntervalTrigger" name="cc" seconds="60"  />
     <weekDays>
     <weekDay>Sunday</weekDay>
     </weekDays>
     </trigger>
</filterTrigger>
```
* 周六周天19:00-07:00之间每隔900秒强制执行。
```
<filterTrigger startTime="19:00" endTime=“07:00”>
     <trigger type="fileterTrigger" startTime=“0:00” endTime=”23:59:59“>
         <trigger type="IntervalTrigger" name="cc" seconds="900" buildCondition="ForceBuild" />
     <weekDays>
     <weekDay>Saturday</weekDay>
     <weekDay>Sunday</weekDay>
     </weekDays>
     </trigger>
</filterTrigger>
```
