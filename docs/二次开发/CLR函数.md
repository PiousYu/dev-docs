#CLR函数
**Note：**所谓的CLR函数是指：C#向Lua虚拟机中注册的一些非Lua原生的函数。这些函数有助于我们的开发，所以在下文中作简要介绍。

|函数名|参数|描述|
|:--|:--|:--|
|Sleep|int类型参数，单位ms|线程挂起时间|
|DebugLine|string类型参数|调试输出| 
|PointerToInt| |指针到int|
|Compile|   |...|
|Log|   |..|.
|GetNull|  |return cs null|
|IsValueType| | 传递寻址 ，返回值的类型|
|SetPhoenix|||
|StartProcess|  |启动一个进程 传递进程路径（...ext）|
|ThrowLuaException|  | 抛出CLR异常|
|WriteLine|  ||
|GetPhoenix|||
|GetBaseDirectory|||
|KillProcess|   |启动一个进程 传递进程路径（进程的名字）|
