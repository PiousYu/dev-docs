#1.1 页面配置

##1.1.1 配置文件

Phoenix软件中，在软件根目录下存在一个用来进行文件路径配置的文件 ———— Setting.lua。读者可以在该文件中进行HMI文件路径的配置。

##1.1.2 配置详解
```
__Setting=
{
    --UI配置
    FramePath="Frames\\",
    StylePath="Styles\\Styles.xaml",
    MainPath="Main.xaml",
    ScriptPath="Scripts\\Scripts.lua",

};
```
* __Setting

    __Setting这个Lua表是用来进行配置编写的。

HMI这部分需要配置实例中的四个路径，并要注意一些规则。

* 规则

FramePath的路径根据Ncstudio.exe的路径相对指定。

StylePath、MainPath、ScriptPath的路径根据FramePath的路径进行相对指定。

* FramePath

    他配置的是HMI总的文件夹路径，系统会根据这个路径去寻找StylePath、MainPath、ScriptPath的路径。同时会加载该文件夹下的所有`.xaml`格式文件及其对应的`.lua`文件。

* StylePath

    动态样式库的文件路径。

* MainPath

    HMI入口文件，总的布局文件的路径。

* ScriptPath

    HMI公共宏的路径。
