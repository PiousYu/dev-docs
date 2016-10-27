Setting帮助
======================

**NOTE:** 这篇文章描述了全局设置文件Setting的有效键值信息.

## 配置描述

`Setting.lua`脚本文件：

```
Lang="zh-CN"
CPath="Config\\"
GPath="G.lua"
DataSavedPath="data.db"
DynamicDataPath="dynamic.lua"
FramePath="Frames\\"

```


## Attributes

| attributes                | values                      | desc |
|:------------------------- |:--------------------------- |:------------------------ |
| Lang                      | `zh-CN`or`en-US`or `...`    | 语言标识                   |
| CPath                     | `Config\\`                  | 配置目录的路径（相对或绝对）   |
| GPath                     | `G.lua`                     | G表扩展脚本路径（相对或绝对）  |
| DataSavedPath             | `Data.db`                   | 数据保存文件路径（相对或绝对）  |
| DynamicDataPath           | `Dynamic.lua`               | 动态文件配置脚本（相对或绝对）  |
| FramePath                 | `Frames\\`                  | UI框架目录（相对或绝对）      |
| SyncPath                  | `Sync.lua`                  | 数据同步表（相对或绝对）      |




## 配置扩展
定义的Setting支持二次扩展（主要应对的场景是在C盘写保护的时候方便的发行到D盘配置）
由于Setting采用的是`.lua` 脚本配置，所以可以方便的应用lua脚本的`require`机制对Setting进行二次扩展：

`C:`盘：
```
Lang="zh-CN"
CPath="Config\\"
GPath="G.lua"
DataSavedPath="data.db"
DynamicDataPath="dynamic.lua"
FramePath="Frames\\"

requier "D:\\Setting.lua"

```

`D:`盘：
```
CPath="D：\\Config\\"
GPath="D：\\G.lua"
DataSavedPath="D：\\data.db"
DynamicDataPath="D：\\dynamic.lua"
FramePath="D：\\Frames\\"

```

## 数据同步表 Sync.lua
```
Items={
	{
		"Phoenix.Channels[0].Auto.V"
		"Phoenix.Channels[1].Auto.V"
	};

	{
		"Phoenix.Channels[0].Auto.V0"
		"Phoenix.Channels[1].Auto.V0"
	};
}
```