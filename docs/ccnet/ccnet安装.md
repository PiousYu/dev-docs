持续集成Criusecontrol.net安装
================================
ccnet需要.NET Framework 2.0和3.5版本

# 1.IIS
ccnet需要web页面查看持续集成的结果，所以需要先安装IIS。
## XP系统安装方法
* 打开控制面板，选择**添加或删除程序**。
* 选择**添加/删除windows组件**

   ![windows.png](docs/ccnet/Picture/安装/window.png "window")
* 勾选**Internet信息服务（IIS）**然后下一步
![internet.png](docs/ccnet/Picture/安装/internet.png "")
* 安装过程中弹出需要文件复制来源，此时将服务器[i386.rar](docs\ccnet\i386.rar "")解压，并将路径选择到**解压的路径里**，继续就可以。
![copy.jpg](docs/ccnet/Picture/安装/copy.jpg "")
* 完成后，打开控制面板，选择管理工具，可以看到Internet信息服务。
# 2.CruiseControl.net安装
* 安装软件

    软件地址：[CruiseControl.Net](docs\ccnet\CruiseControl.NET-1.8.5.0-Setup.exe "")
    
    双击安装，都按默认选择即可。
    
   **注意:**把ThoughtWorks.CruiseControl.Core.dll替成换[ThoughtWorks.CruiseControl.Core.dll](docs\ccnet\ThoughtWorks.CruiseControl.Core.dll "")这个dll解决连接TFS时Date不正确问题。
* ccnet虚拟目录

    ccnet默认会创建虚拟目录ccnet，如果虚拟目录创建失败就需要手动创建。
    
    **1.**控制面板->管理工具->Internet信息服务
    
    **2.**默认网站右击->新建->虚拟目录
    
    **3.**弹出虚拟目录向导，根据向导创建。
    
      * 别名：ccnet
      * 目录：“C：\Program Files\CruiseControl.NET\Webdashboard” 
    
    **4.**右键ccnet->属性，弹出属性对话框。
    
      * 选择**ASP.NET**,ASP.NET版本改为：2.0.50727
     
    ![ASP.png](docs/ccnet/Picture/安装/ASP.png "") 
    
      * 选择**文档**，添加**default.aspx**
     
    ![defaultasp.png](docs/ccnet/Picture/安装/defaultasp.png "")
    
    **5.**配置完成，此时右键**ccnet网站->浏览**就可以看到网页。

# 常见问题
