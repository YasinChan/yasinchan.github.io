title: "XAMPP安装过程中问题的解决方法"
date: 2017-01-05 16:00:00 +0800
update: 2017-01-05 16:00:00 +0800
author: me
cover: "-/images/XAMPP.png"
tags:
    - 问题
    - 整理
preview: 问题整理

---

### 前言
最近配置XAMPP过程中遇到Apache点击start却无法开启，Google后发现也有很多人遇到这种情况。查阅许久，问题成功解决。

#### 解决方法
当我们打开XAMMP时，我们点击Apache中的start却无法开启，下面报错
```
[Apache]  Error: Apache shutdown unexpectedly.
[Apache]  This may be due to a blocked port, missing dependencies, 
[Apache]  improper privileges, a crash, or a shutdown by another method.
[Apache]  Press the Logs button to view error logs and check
[Apache]  the Windows Event Viewer for more clues
[Apache]  If you need more help, copy and post this
[Apache]  entire log window on the forums
```
此时，我们可以打开`G:\xampp\apache\conf`(G:\xampp是我的安装目录)下找到`httpd.conf`文件，可以用sublime打开后找到
```
Listen80
```

```
ServerName localhost:80
```

将其中的80改为8080

[来源](http://stackoverflow.com/questions/18300377/xampp-apache-error-apache-shutdown-unexpectedly)

PS: 原文中还有一个步骤，翻译过来就是：
打开`httpd-ssl.conf`找到
```
Listen 443
```

```
VirtualHost _default_:443
ServerName localhost:443
```

将其中的443改为4433。
但是我发现不做这一步也没有问题。


此时我们重新开启Apache，发现可以开启，但是却出现以下的问题
```
[Apache]  Problem detected!
[Apache]  Port 80 in use by &quot;Unable to open process&quot; with PID 4!
[Apache]  Apache WILL NOT start without the configured ports free!
[Apache]  You need to uninstall/disable/reconfigure the blocking application
[Apache]  or reconfigure Apache and the Control Panel to listen on a different port
```

此时，我们可以运行对话框（按WIN + R键）键入：`services.msc`

出现如下界面：

![](-/images/服务.png)

找到箭头所指后右键关闭。

[来源](http://stackoverflow.com/questions/20558410/xampp-port-80-in-use-by-unable-to-open-process-with-pid-4-12)

此时我们重启Apache发现问题解决。

将我们需要的PHP文件放入`G:\xampp\htdocs`文件夹下在浏览器打开`localhost:8080/文件名.php`即可访问我们PHP文件。


PS：如果设置过程中还出现其他问题，可以点击我的文中的`来源`，看各个步骤完整的解决方法。