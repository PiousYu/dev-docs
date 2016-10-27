#PLCEditor项目

##V0.5
大家好，我们的第五个版本出炉了！该版本中进行了一些问题的修复和一些功能的添加。

###新的改变

* PLCEditor修复了部分BUG

    * 解决插入一个Network，无法插入到当前NetWork下方的bug

    * 解决NetWork生成之后，名字无法修改的bug

    * 解决插入一个Subroutine，弹出对话框中事件部分浏览按键无效的bug

    * 解决Subroutine生成之后，名字无法修改的bug

    * 解决Subroutine生成之后，事件无法修改的bug

* PLCEditor添加了新的快捷键

    * 添加Ctrl+F快捷键

    * 添加Ctrl+Y快捷键功能

    * 添加Delete删除功能快捷键


* PLCEditor对部分功能做了调整

    * 进入在线状态之时，会自动进行梯形图的整理。

    * 编译在输出目录中生成的文件名为BuildTC6.xml，下载为DownloadTC6.xml，上传为UploadTC6.xml。

    * 主菜单的命令是否可以执行（不可执行变灰）与当前的在线状态挂钩。

    * 梯形图的实时变量有效性检查，更新了InstructionManager.xml文件后，目前工程的大部分变量都能正确判断有效性。



###下载

* [PlcEditor_0.104.0.0.zip](Resource\PLCEditor\PlcEditor_0.104.0.0.zip)
* [PLC说明](Resource\PLCEditor使用说明书.md)



##V0.4
大家好，我们的第四个版本出炉了！该版本中进行了一些问题的修复和一些功能的添加。

###新的改变

* PLCEditor修复了部分BUG

    * 消除DEBUG模式下程序退出时在VS上输出的内存泄露警告。

    * 信息输出若干MessageBox没有判断MainWnd是否存在的BUG

    * 解决避免界面与数据不同步的问题的BUG

* PLCEditor添加了新的功能

    * 信息输出翻译加中入文件名标记。

    * 信息输出双击将会发送正确的位置信息。

    * 信息输出双击消息中的条目可以正确的定位全局变量。（完成但是目前编译期信息输出不完整）

    * 信息输出双击消息中的条目可以正确的定位局部变量。（完成但是目前编译期信息输出不完整）

    * 信息输出双击消息中的条目可以正确的定位梯形图。

    * 梯形图中的变量可以直接拖动到状态表。

    * 查找替换对话框中可以定位梯形图。

    * 查找替换对话框可以选择模糊查找或精确查找。

    * 交叉引用的翻译。

    * 交叉引用中可以定位梯形图。

    * 信息输出Debug函数也采用消息模式驱动。



###下载

* [PlcEditor_0.103.0.0.zip](Resource\PLCEditor\PlcEditor_0.103.0.0.zip)
* [PLC说明](Resource\PLCEditor使用说明书.md)



##V0.3
大家好，我们的第三个版本出炉了！该版本中进行了一些问题的修复和一些功能的添加。

###新的改变

* Weihong.Phoenix.Plc.dll修改

    调整Plc启动顺序，首先启动Plc服务器。这样，即时启动Plc扫描是出现异常，从客户端(PlcEditor)亦可以连接到服务器。

* 翻译工具修改

	修复参数为相对路径时不能正确进行翻译并编译成dll的bug；
	
	添加更新监控数据的代码，在开启监控后可以获取监控数据；
	
	添加 空值判断，防止抛出不明确的 空引用 bug

* PLCEditor添加了运行停止功能

* PLCEditor连接BUG修复

	* 修复了连接状态不能保持的BUG。

* PLCEditor监控调试BUG修复

	* 修复了监控时开关和线圈状态反馈显示不正确的BUG

* PLCEditor添加启动和停止功能

	* 现在我们可以在PLCEditor连接到服务器后，通过菜单栏的 PLC->运行/停止 来启动/停止服务器端 Plc逻辑扫描

	 

	
###下载

* [PlcEditor_0.102.0.0.zip](Resource\PLCEditor\PlcEditor_0.102.0.0.zip)
* [PLC说明](Resource\PLCEditor使用说明书.md)



##V0.2
大家好，我们的第二个版本出炉了！

###新的改变

* 将编译所需的Type.xml文件保存到了项目文件中，并且在编译的过程中自动添加到Tc6XML格式的文件中，不需要在编译的时候特别指定了。

* 编译器命令行参数的修改，下面是新命令行参数的说明：

	* /o:outfile

 	/o:为参数前缀，outfile为参数值，此参数为生成的`Plc逻辑程序集`路径及名称，支持相对路径和绝对路径。
	 
	 例如：想在C盘Custom文件夹下生成名为Ncstudio.plc的文件则应写为
	 
	 ```
	 	/o:C:\Custom\Ncstudio.plc	
	 ```
	 如果该参数不指定，默认情况下，会将生成的程序集命名为plc.dll并保存到`选定的编译器(目前为Tc6ToCSharp.exe)`所在目录。
	
	* /t:tc6file
	
 	/t:为参数前缀，tc6file为参数值，此参数为`由Plc梯形图图形化语言翻译过来的的tc6格式文件`的路径及名称，支持相对路径和绝对路径。
	 
	 例如：想编译C盘Custom文件夹下名为tc6.xml文件则应写为
	 
	 ```
	 	/t:C:\Custom\tc6.xml	
	 ```
	 如果该参数不指定，默认情况下，会使用`选定的编译器(目前为Tc6ToCSharp.exe)`所在目录中的tc6.xml文件。
	 
	* /d:directory

 	/d:为参数前缀，directory为参数值，此参数为应用程序对生成的CSharp代码进行编译时所需资源目录，目录中应包含编译所需的所有资源。
	 
	 例如：想编译时所需资源在C盘Custom文件夹下
	 
	 ```
	 	/t:C:\Custom	
	 ```
	 
	如果该参数不指定，默认情况下，会使用`选定的编译器(目前为Tc6ToCSharp.exe)`所在目录。
	
###下载

* [PlcEditor_0.101.0.0.zip](Resource\PLCEditor\PlcEditor_0.101.0.0.zip)
* [PLC说明](Resource\PLCEditor使用说明书.md)


##V0.1
欢迎大家使用PLCEditor！这是我们的第一个版本，实现了梯形图PLC的一些基本功能。下面我们简单地来看一下目前的PLCEditor为大家提供了哪些服务:

### 目前功能

*	更加人性化的图形化编辑软件`PLCEditor`。他目前具有这样一些功能：

	* 项目管理。可以利用项目的方式管理PLC相关的数据和程序逻辑。
	
	* 图形化编辑。摒弃了我们之前的助记符形式的编码方式，让开发的难度大幅降低。
		 
* 	可以扩展的库`Weihong.Phoenix.Plc.dll`。

![PLC说明](Resource\Image\PLCEditor架构.jpg)

我们可以看到，我们后端的库是可以扩展的。可以应用于多种语言，多个平台，具有相当的扩展性。目前我们实现了从TC6格式到C#的翻译。
	
###目前存在的问题

目前的软件还在预发行阶段，所以有一些问题还是存在的。比较影响使用的BUG有这么一些：

* 快捷键系统没有完善，并不是所有的快捷键都已经实现。
	
* 查找替换功能还不支持模糊查询
	
###下一阶段的目标
在下一个版本的发行中，我们预期会有如下更改：

* 任务
	
	* 局域网上传下载。目前是支持局域网对PLC进行上传下载，可以在客户端进行编辑并作用于服务器。
	
	* 局域网监控调试。可以实时监控服务器上PLC的运行情况。
	
* BUG
目前还没有BUG修复计划。

###下载
* [PlcEditor_0.100.0.0.zip](Resource\PLCEditor\PlcEditor_0.100.0.0.zip)
* [PLC说明](Resource\PLCEditor使用说明书.md)

##软件版本变更

|软件|版本|日期|
|:--|:--|:--|
|[PlcEditor_0.104.0.0.zip](PLCEditor\PlcEditor_0.104.0.0.zip)|V0.5|2016.6.12|
|[PlcEditor_0.103.0.0.zip](PLCEditor\PlcEditor_0.103.0.0.zip)|V0.4|2016.5.30|
|[PlcEditor_0.102.0.0.zip](PLCEditor\PlcEditor_0.102.0.0.zip)|V0.3|2016.4.29|
|[PlcEditor_0.101.0.0.zip](PLCEditor\PlcEditor_0.101.0.0.zip)|V0.2|2016.4.19|
|[PlcEditor_0.100.0.0.zip](PLCEditor\PlcEditor_0.100.0.0.zip)|V0.1|2016.4.7|
