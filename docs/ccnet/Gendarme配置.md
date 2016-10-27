Gendarme 配置
==========================================
**NOTE：** 此文介绍CCnet如何配置Gendarme工具（.net代码分析工具）。
# Gendarme 概述
Gendarme 是可扩展的.NET代码分析工具。
# 配置

## 1.工程文件（project.xml或ccnet.config）
配置项目执行Gendarme分析。

```
<Tasks>
...
<gendarme>
	<executable>D:\Gendarme\gendarme.exe</executable>
	<assemblies>
		<assemblyMatch expr="NcExplorer.dll" />
		<assemblyMatch expr="*.exe" />
	</assemblies>
	<baseDirectory>F:\Phoenix\Peripheral\NcExplorer\Debug</baseDirectory>
	<configFile>D:\Gendarme\rules.xml</configFile>
</gendarme>
...
</Tasks>
```

## 2. dashboard.config

配置此文件可以在ccnet集成网页上看到Gendarme分析结果。

```
需要添加两条语句：xslFile、xslReportBuildPlugin
 <buildPlugins>
      <buildReportBuildPlugin>
        <xslFileNames>
         ...
          <xslFile>xsl\gendarme-summary-ccnet.xsl</xslFile>
        </xslFileNames>
      </buildReportBuildPlugin>     
     <xslReportBuildPlugin description="Gendarme Report" actionName="GendarmeBuildReport" xslFileName="xsl\gendarme-report-ccnet.xsl" />
</buildPlugins>
```
* 界面截图

![genderme.png](docs/ccnet/Picture/genderme.png "")

##3.packages.xml(若没有安装该工具，且联网需要配置)
将下面语句的installed的值改为yes，则会在线安装Gendarme工具。

```
<package name="Gendarme Results" description="Display the results of a Gendarme report" type="Plugin" file="Gendarme.zip" installed="yes"/ >
```

# 常见问题
