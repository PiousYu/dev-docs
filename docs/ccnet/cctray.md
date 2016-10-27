CCTray 
==============================================
cctray是CruiseControl.NET客户端，它可以监控集成的项目，查看项目状态和日志情况。

软件地址：[CruiseControl.NET-CCTray-1.8.5.0-Setup.exe](docs\ccnet\CruiseControl.NET-CCTray-1.8.5.0-Setup.exe "")

安装和一般软件安装一样就不介绍了，直接介绍如何配置。
# 配置
* 打开软件->File->settings,打开如下对话框。

    ![settings.png](docs/ccnet/Picture/settings.png "")
* 选择Build projects->Add...->Add Server,弹出的对话框中输入安装CruiseControl.net的机器的名字或ip地址。

    ![AddServer.png](docs/ccnet/Picture/AddServer.png "")
* 点击ok，在project对话框中选择你要监控的项目。
 
    ![selectProject.png](docs/ccnet/Picture/selectProject.png "")
* 然后cctray中就已经有我们选择的项目了。

    ![cctray.png](docs/ccnet/Picture/cctray.png "")
    
# 使用 

* 状态区分

    **红色**：失败
    
    **绿色**：成功
    
    **黄色**：运行
    
* ForceBuild 

   *强制运行任务，编译查看最新的代码或测试是否有问题*
   
   选中项目->右键->ForceBuild

* 查看日志

    cctray上双击任意项目，弹出ccnet网页。
    
    ![ccnet.png](docs/ccnet/Picture/ccnet.png "")
* 双击要查看的项目->进入项目信息页面->选中build版本->View Build Log->日志信息显示在网页右侧

    ![projectinfo.png](docs/ccnet/Picture/projectinfo.png "")

    