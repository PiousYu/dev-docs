#Tc6ToCSharp.exe

**NOTE** Tc6ToCSharp.exe是Phoenix平台为翻译tc6格式文件并生成Plc逻辑程序集 提供的控制台应用程序。通过命令行将所需参数传给应用程序。

##命令行参数说明

* /o:outfile

 /o:为参数前缀，outfile为参数值，此参数为生成的 Plc逻辑程序集 名称，名称中包含文件目录信息，支持使用绝对目录或相对目录。默认将生成的程序集命名为plc.dll保存到Tc6ToCSharp.exe所在目录。

* /t:tc6file

 /t:为参数前缀，tc6file为参数值，此参数为 由Plc逻辑翻译的tc6格式文件 名称，名称中包含文件目录信息，支持使用绝对目录或相对目录。默认使用Tc6ToCSharp.exe所在目录中的tc6.xml文件。

* /d:directory

 /d:为参数前缀，directory为参数值，此参数为应用程序对生成的CSharp代码进行编译时所需资源目录，目录中包含编译所需的所有资源。默认使用Tc6ToCSharp.exe所在目录。
