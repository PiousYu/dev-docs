intervalTrigger
==============================
**NOTE:** 此文章主要介绍ccnet中intervalTrigger触发器用法。

## intervalTrigger
intervalTrigger 触发是支持间隔触发的，即每隔一段时间执行。

### 参数
 * buildCondition 触发build条件

 值：NoBuild 不执行 IfModificationExists 改变时执行 ForceBuild 强制执行
 * initialSeconds 延迟启动时间

 检测到改变时等待此时间后执行。
 * secondes 间隔时间
 
 设置每隔多长时间执行。

 * name 名字

 触发器的名字
 
### 举例
* 每隔 5分30秒触发
```
<intervalTrigger name="trigger" seconds="300" buildCondition="ForceBuild" initialSeconds="30">
```

* 每隔 5分钟检查源码改变并延迟30秒触发
```
<intervalTrigger name="trigger" seconds="300" buildCondition="IfModification" initialSeconds="30">
```