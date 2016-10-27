触发器与Action
==============================

**NOTE:** 本文对Action这个属性的解释以及用法进行了一定的描述，为读者提供了修改支持。

##Action用途

系统在运行的过程中会有一些“动作”被执行，这些动作执行的条件有很多，比如周期扫描，又比
如说事件触发。这些条件满足后执行的动作我们就将其定义为Action.

##Action用法

举个例子来说明Action的用法。
```
	<EventTrigger RouteEvent="Loaded">
		<ui: Action="Test">
	</EventTrigger>
```
这里利用了事件触发器来激活一个动作（Action），动作的名字叫“Test”

##Action的源

上面我们讲到了动作的名字，其实也就是Action的源。
在我们的系统中，是这样存放和加载这些源的。
	1.第一步，系统默认读取一个文件
	这个文件是指定路径的一个文件，文件的路径为\Frames\Function\Function.lua
	2.第二步，如果内容不存放在这个文件中那则在这个文件中指向另外的文件
	Lua中对此的实现是在Function.lua文件中require `指定文件名` 即可
	3.第三步，这个文件内容的添加
	只要在这个文件中添加指定格式的内容，并指定命名，在Action属性就可以调用了。
	
##文件中的内容
```
	function test()
		Msg("这是一个测试程序")
	end
```
	
###函数作为第一类值
	Lua中函数是可以作为变量被存放在表中的，如下：
```
	Phoenix = {
		Program = 	function test()
						Msg("这是一个测试程序")
					end	
	}
```
	