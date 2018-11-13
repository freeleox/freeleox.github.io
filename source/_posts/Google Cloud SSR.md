---
title: 谷歌云免费搭建一年SSR服务器
date : 2018-11-02
updated : 2018-11-02
comments : true
tags : code
categories : code
---

# 谷歌云免费搭建一年SSR服务器

<p style="text-align:right">作者：Leo</p>


想要看看“墙外的世界”的小伙伴，可以考虑部署谷歌云服务器啦~因为谷歌云免费使用一年的政策，相当于免费用了一年稳定的VPN呢。。
谷歌云赠送300美金金额，流量肯定够那些只用来翻墙或者写博客的小伙伴使用了。

## 你需要准备：

- 一台可以翻墙的电脑。（VPN软件试用流量应该就够了，推荐蓝灯。）



- 一张**双币/全币种**信用卡。我使用的是招行信用卡，谷歌云注册的时候，会从你的信用卡收取一美金证明你不是机器人，过后会退还。由于信用卡申请需要一段时间，建议这个提早着手准备。



- 一个谷歌账号。建议是你本人使用的。

## 申请谷歌云服务器

点击[申请试用](https://cloud.google.com/free/)，填写以下信息：![img](http://r.photo.store.qq.com/psb?/V11yCWJM1bo1cH/ESJHG3G0inrRQK3Yan8dcF7YTfXyO*Ka.DP95QtBgIQ!/r/dFIBAAAAAAAA)

国家选择中国，同意服务条款，电子邮件看你个人意愿。我貌似勾了是，但是并没有收到邮件。。



![img](http://r.photo.store.qq.com/psb?/V11yCWJM1bo1cH/UKOFnMQXL6Uj7NuSGaPNp3YhS57YXZ8RpFXqmC45QSI!/r/dFYBAAAAAAAA)

账号类型选择“**个人**”。个人信息填写完毕之后，掏出你的信用卡！

月份年份填有效期，验证码填信用卡背面那三位（不要告诉别人）。

当弹出以下窗口的时候，说明你已经申请成功啦~

![img](http://r.photo.store.qq.com/psb?/V11yCWJM1bo1cH/u*5pdH.DBpqMA46BtHrJ9baqjMIBEXEcJOG6zN.nGjo!/r/dFIBAAAAAAAA)

关于这几个问题的答案我已经不记得自己填的什么了emmm....大家如实填写吧，或者直接点击开始使用。

## 创建防火墙规则

接着就会进入你的控制台，可以浏览熟悉一下。接着在左侧的导航栏往下滑选择**VPC网络**。

等待几分钟启用Computer Engine。选择**防火墙规则**。

点击**创建**。

规则名字自定义，流量方向选择**出站**，目标选**网络中的所有实例**，来源过滤选择**IP地址范围**，并在下方填写**“0.0.0.0/0”**，然后点击创建。![img]()

再新建一条规则，方向选择**入站**。其他和出站规则一样。

<p style=color:red;>再提醒一次，规则有两条，分别为“入站”和“出站”。目标请勾选“网络中的所有实例”。</p>

##  外部IP地址

在左侧继续选择**外部IP地址**。

![img](http://a1.qpic.cn/psb?/V11yCWJM1bo1cH/HjoVFnQHVWzZB97rD8x3DTLD1r9HeqYB2aQuHggIkvs!/b/dFQBAAAAAAAA&ek=1&kp=1&pt=0&bo=4AFUAuABVAIDGTw!&tl=1&vuin=2325356404&tm=1541210400&sce=60-4-3&rf=viewer_4)

创建，名称自定义。区域，选择 **asia-east1**。

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/MACKpnkhdNwg3U4JpHdybHgt6AabsqdhAusiypSB*Bs!/b/dFMBAAAAAAAA&bo=oQKYAqECmAIDGTw!&rf=viewer_4)

## 创建VM实例

回到控制台的首页，左侧的导航栏中选择**Computer Engine** ==> **VM实例**。

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/Mu7RUjliJZjJ5m4ZrGt7wyqWZzVtaLDbO*8ahECWSfA!/b/dFQBAAAAAAAA&bo=ygNqBMoDagQDCSw!&rf=viewer_4)

创建，机器类型选择**微型0.6 GB 内存** ，区域我选择的是**asia-east1-c**，你也可以选择**asia-east1-a**。

启动磁盘选择**Ubuntu 16.04 LTS**。

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/xs20H1Z4PxykLf9D9VW8M1JUhx6QWduP.FdFN77lrGQ!/b/dEcBAAAAAAAA&bo=jgScBI4EnAQDCSw!&rf=viewer_4)

选择后如图所示：

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/mfdsLOC4Tl4E7*qU*pzjmitnfmeb7*yK2cKT6*eCPNA!/b/dDUBAAAAAAAA&bo=YAK2AWACtgEDCSw!&rf=viewer_4)

往下滑，点开**管理、安全、磁盘、网络、单独租用**

选择**安全**，在这里你可以上传你的ssh密钥文件，如果没有就跳过，选择**网络**

**内部IP**选择静态，**外部IP**选择刚刚创建的优质层级，点击完成。

## SSH连接服务器

等待配置成功后，会显示刚刚新建成功的实例，如图：

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/S70ojTKywWFGcI64dCNXoMw8fIzlXEkRCeLWAhO2ikM!/b/dFIBAAAAAAAA&bo=zgNmAc4DZgEDCSw!&rf=viewer_4)

点击连接下方的**”SSH“**，会弹出一个新的浏览器窗口。

![img](http://m.qpic.cn/psb?/V11yCWJM1bo1cH/K.2M1aYZCPtb.INBLKPKwk.WfPVSQV3GnIfAGSuumeI!/b/dFIBAAAAAAAA&bo=bARcAwAAAAADBxU!&rf=viewer_4)

输入`sudo su`进入root模式，我一直用的是`sudo -i`。

输入`apt update`等待一小会，更新完成后输入`apt upgrade`，再按照指示输入`y`，回车。

依次输入以下代码，回车：

```
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
apt-get update
apt-get install -y python-pip
pip install shadowsocks
```

等待完成。

接下来进入编辑器，输入`vim /etc/ss-conf.json`，成功后摁下`i`进入插入模式（这点很重要否则无法编辑），复制以下代码：

```
{
  "server": "这里填你的外部IP",
  "server_port":  8838（这里是端口，默认8838，可自定义，9000~15000之间）,
  "local_address":  "127.0.0.1",
  "local_port": 1080,
  "password": "这里填你想要的密码",
  "timeout":  600,
  "method": "aes-256-cfb"
}
```



更改完后记得把括号及其内容删除，最终结果是这样的：

```
{
  "server": "xx.xxx.xxx.xxx",
  "server_port":  8838,
  "local_address":  "127.0.0.1",
  "local_port": 1080,
  "password": "xxxxxx",
  "timeout":  600,
  "method": "aes-256-cfb"
}
```

输入完毕后，摁下**ESC**，退出插入模式，使用方向键将光标移到最下，英文状态输入**`:wq`**，接着回车

等待，输入`ssserver -c /etc/ss-conf.json -d start`。

## 配置SSR客户端

**Shadowsocks for Windows 客户端下载：**
https://github.com/shadowsocks/shadowsocks-windows/releases

**Shadowsocks for Android 客户端下载：**

https://github.com/shadowsocks/shadowsocks-android/releases

**Shadowsocks for Mac客户端下载：**

https://github.com/shadowsocks/ShadowsocksX-NG/releases



**Shadowsocks for ios客户端下载：**

切换美区App Store下载**shadowrocket** ，美区账号可向朋友借或者淘宝买一个。



下载后打开配置页面，**服务器地址**输入你的外部IP地址，也就是刚刚代码中的`server`一栏内容。

端口对应`sever_port`，密码对应`password`，加密选择`aes-256-cfb`。点击确定，启用此代理。

恭喜你，可以享受“墙外的世界”了。