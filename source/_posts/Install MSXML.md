# Microsoft Office 2010安装需要MSXML版本的解决方法

当卸载了系统自带的office软件再安装后，则会跳出这样的错误提示，本文附下载链接及安装方法。

## 下载MSXML

- 推荐在官网进行下载，点击[下载](https://www.microsoft.com/zh-CN/download/details.aspx?id=6276)。
- 也可以在百度上进行搜索MSXML下载。

当我们打开官网下载链接后，选择下载，选择版本。

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/DyVogN5GxHrthDY9zC9dck1Ry7QqGuT4*MSgA3WUenQ!/b/dEgBAAAAAAAA&bo=8QQHAvEEBwIDCSw!&rf=viewer_4)

如图所示，x86代表系统为32位，x64则代表为64位。

查看电脑系统位数可通过**控制面板**==>**系统**，在**系统类型**查看是多少位操作系统。

选择相应版本，选择Next进行下载。

##  安装

点击下载好的程序，安装后（我这里秒安装成功，所以没截图），随便在某个位置，比如桌面，新建一个记事本。

右键==>新建==>文本文档

输入以下代码：

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\TypeLib\{F5078F18-C551-11D3-89B9-0000F81FE221}\6.0]@="Microsoft XML, v6.0"

[HKEY_CLASSES_ROOT\TypeLib\{F5078F18-C551-11D3-89B9-0000F81FE221}\6.0\0]@=""

[HKEY_CLASSES_ROOT\TypeLib\{F5078F18-C551-11D3-89B9-0000F81FE221}\6.0\0\win32]@="C:\\Windows\\System32\\msxml6.dll"

[HKEY_CLASSES_ROOT\TypeLib\{F5078F18-C551-11D3-89B9-0000F81FE221}\6.0\FLAGS]@="0"

[HKEY_CLASSES_ROOT\TypeLib\{F5078F18-C551-11D3-89B9-0000F81FE221}\6.0\HELPDIR]@="C:\\Windows\\System32\"
```

将记事本文档保存为**msxml.reg**，弹出改变文件拓展名提示框，点击确定。

（如果没有弹出，请在文件夹选项中选择**显示文件后缀名**，win7/8/10方法请自行百度搜索）

双击此文件，点击是。

然后就可以继续安装office2010啦~