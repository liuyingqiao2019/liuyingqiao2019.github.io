---
title: 记一次XAMPP的报错实例
date: 2020-02-11 20:36:34
tags: 报错
categories: XAMPP
---

# 记一次XAMPP的报错实例

昨天在用服务器构建网页时，使用到了XAMPP，但在访问服务器本身的IP时，却出现了如下的报错：

**_Uncaught error with message ‘[db.WindConnection.init] SQLSTATE[HY000]
[1045] Access denied for user ‘root’@’localhost’ (using password: YES)’_**

**_The server encountered an internal error and failed to process your
request. Please try again later. If this error is temporary, reloading the
page might resolve the problem.  
If you are able to contact the administrator report this error
message(<http://www.windframework.com/>)_**

内容大体上是说，权限不够或密码错误，于是我重新看了一下 **phpasmin** 里的账号密码

图中可以看到 **root** 的三个账户的密码都是无且授权为是  
So后面我根据百度的方法一顿操作

![2](2.png)

完了发现又多了其他问题，最严重的一个是– **Mysql服务无法启动**

![3](3.png)  
可以看到下图中XAPMM的Mysql以及无法启动且报一大堆的错

![4](4.png)

![5](5.png)

## OK,现在开始第一次尝试：

在Mysql目录bin里下找到`my.ini`文件用记事本打开，查找`[mysqld]`并在下面增加一行代码`innodb_force_recovery
=4`

![6](6.png)

结果XAMPP报错：  
![7](7.png)

## 第二次尝试：

看日志最后几行发现是3306端口被占用，既然3306不能用

![8](8.png)  
那我就换一个端口呗  
修改Mysql目录里bin中的`my.ini`文件的端口如下：  
![9](9.png)

顺便修改了 **默认ip地址** ：  
![10](10.png)

结果还是不行：  
![11](11.png)

10+小时过去了，试了各种办法都没法启动Mysql服务，于是，我直接 **重装XAMPP**  
![13](13.png)

## 文章后面为XAMPP对Apache的初始化

在XAMPP中选择配置  
![14](14.png)  
更改`Apache`的端口  
![15](15.png)

确保画 **蓝圈** 的地方是选择`Apache`的，更改画 **黄线**
里的端口值（在数字后面加个零即可）。记住原来的两个值，这里我原来的值分别是80和443

![16](16.png)

然后在XAMPP中找到Apache里conf目录的`httpd.conf`文件，用记事本打开并查找未更改端口前的第一个数值，将其改成更改后的端口值。如我这里是将80改为800，Ctrl+S保存

![17](17.png)

再在conf目录里的extra中找到`httpd-
ssl.conf`文件，用记事本打开并查找未更改端口前的第二个数值，将其改成更改后的端口值。如我这里是将443改为4430 ， **Ctrl+S** 保存

![18](18.png)

现在回到XAMPP，点击 **Apache** 中的 **Start** ,看到Apache和Mysql底色是绿色即完成;

![19](19.png)



