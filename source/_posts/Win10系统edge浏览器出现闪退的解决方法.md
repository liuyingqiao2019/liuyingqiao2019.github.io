---
title: Win10系统edge浏览器出现闪退的解决方法
date: 2020-03-30 9:18:23
tags: 闪退
categories: edge
---

#  Win10系统edge浏览器出现闪退的解决方法

记一个Win10系统edge浏览器出现闪退的解决方法：

第一步：

**Win+R** 呼出运行窗口，并在里面输入

`%USERPROFILE%\AppData\Local\Packages`,点击确定按钮

![1](1.png)

这时可以看到打开了一个文件夹，找到

`Microsoft.MicrosoftEdge_8wekyb3d8bbwe`文件夹，

右键 **删除**

![2](2.png)

第二步：

返回桌面，在 **搜索框** 输入

`PowerShell`搜索，并在搜索结果中选择 **以管理员身份运行** ,划重点 一定要以 **管理员身份**
运行，如果直接打开出现的后果会在文章最后说明。

![3](3.png)

第三步：

在打开的`Windows PowerShell`窗口中输入命令  
`Get-AppXPackage -ALLUsers -Name Microsoft.MicrosoftEdge | Foreach {Add-
AppxPackage -DisableDevelopmentMode -Register
"$($_.InstallLocation)\AppXManifest.*" -verbose}`  
看到下图即成功。

![4](4.png)

当然，如果没出现黄字的提示，看到下面那行的命令行出来时，关闭`Windows PowerShell`  
窗口后，打开浏览器，出现下图的画面，即表明浏览器闪退问题已解决。

![5](5.png)

出现报错的情况有：

一、 **Get-AppXPackage** 拒绝访问

![6](6.png)

 2.Win10 **防火墙** 没有打开

此时应该检查标题栏中的标题是 _选择Windows PowerShell_ 还是 _选择管理员：Windows PowerShell_ 。如下图：

![7](7.png)

![8](8-1.png)

若没有管理员的字样，就是原因1，若已经是以管理员身份运行了，则去 **控制面板** 检查防火墙是否已经打开

检查 **防火墙是否已经打开** 步骤：

此电脑-右键选择属性-在路径栏点击控制面板

![9](8.png)

在查找方式处，选择大图标

![10](9.png)

![11](10.png)

单击Windows Defender 防火墙，若看到下图的情形，则是没有打开防火墙，

![12](11.png)

此时点击使用推荐配置即可

二、按照所有步骤都执行了，但是浏览器还是闪退

莫慌，来看看你的命令输入是不是和下图的很像？

报错语句截图：

![13](12.png)

![14](13.png)

看看你输入的双引号是中文的“”，还是英文的””？看看你的命令语句中的黄字部分与解决方法步骤中的黄字部分是否一致？是不是多打了一个空格？

解决方法：直接解决步骤的第三步复制粘贴命令即可

