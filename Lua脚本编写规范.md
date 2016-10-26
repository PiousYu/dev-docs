Lua脚本编写规范
===============================
##术语定义
1. Pascal 大小写

	将标识符的首字母和后面连接的每个单词的首字母都大写。可以对三字符或更多字符的标识符使用Pascal 大小写。例如：BackColor。

##命名规范
###通用规范
1. 名字应该能够标识事物的特性。
2. 名字一律使用英文单词，而不能为拼音。
3. 名字尽量不使用缩写，除非它是众所周知的。

### 文件名
`一定要` 命名采用`Pascal`大小写规范。	
eg: 
```
PauseControl.lua
```

###函数名
`一定要` 采用`Pascal`大小写规范。
eg:
```
function CalibrationNoEncoder()
```
###全局变量
`一定要` 采用`Pascal`大小写规范。
eg: 
```
FixedPosition
``` 
###局部变量
`一定要` 全部小写。
eg:
```
local homed
```
### 常量
`一定要` 大写加下划线。
eg：
```
KIND_PET_FOOD 
``` 

##注释
1.`一定要` 在每一个函数前加上上对此函数功能的描述，若函数带有参数，要对参数进行解释。
```
	--[[
		这是一个开灯的函数。
		param参数控制灯的打开和关闭，他的正确输入值为布尔类型。输入其他类型也没有问题。
	--]]
	function OpenLight(param)
		local test = type(param)
		if test == "Boolean" then
			Msg("输入的参数值无效！")
			return
		end
		if param then
			Phoenix.G.Channels[0].Y01 = true
		else
			Phoenix.G.Channels[0].Y01 = false
		end
	end
```
2.`强烈建议` 除了极有必要的注释外，函数的内部最好不要进行注释说明。

##分隔和缩进
###空格
1. `一定要` 在运算符前后各添加一个空格。运算符包括：
```
	{
		+  -  *  /  ^
		-(unary)
		<  >  <=  >=  ==  ~=
		and  or  not
		..  
	}
```
eg:
```
	c = a + b
	c = a > b 
	c = a and b 
```
2. `一定要` 在调用多个函数时，在各个函数之间空一格。
eg: 
```
	G90() G53() G01{x = 10}
```

3. `一定要` 在函数体、控制结构内写代码时空一个制表位。
eg:
```
	function f1()
		if i > 0 then
			print("OK!")
		end
	end
```
4. `一定要` 在连接符`..`两边各空一个空格。
eg:
```
	print("我是" .. "中国人!")
```
###换行

1. `强烈建议` 超过150列的代码换行，或换编写方式。

##Table(表)
1. `一定要` 在表后加上 `;` 号。
eg:
```
	tbl = 
	{
		[1] = 1,
	};	
```


