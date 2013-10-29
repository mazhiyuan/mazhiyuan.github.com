---
layout: post
title: 如何快速利用win7建立wifi
description: 
category: blog
---
## 如何快速利用win7建立wifi
#### *for 晴子啊*

step 1：打开终端，输入命令
 
操作：WIN+R 输入cmd，回车，在黑漆漆的窗口输入

```bash
netsh wlan set hostednetwork mode=allow ssid=qingzia key=qingzia
```

ssid:无线网名称，qingzia

key:无线网密码，qingzia

表忘记回车

step 2：共享有线网络给wifi
运行成功后，打开网络和共享中心，点击左侧更改适配器设置。

![适配器图片](http://g.hiphotos.baidu.com/exp/w=500/sign=c469e352f2d3572c66e29cdcba126352/1b4c510fd9f9d72aaee1a4a6d42a2834359bbb80.jpg "")



进入适配器设置就会发现多出了一个网卡为“Microsoft Virtual WiFi Miniport Adapter”的无线网络连接。若没有，则尝试更新无线网卡驱动。

为方便起见，可将无线网络连接2重命名为虚拟WiFi。
![虚拟网络pic](http://g.hiphotos.baidu.com/exp/w=500/sign=585cf106a9773912c4268561c8188675/f603918fa0ec08faff62a41c59ee3d6d55fbda2f.jpg "")
![pic2](http://e.hiphotos.baidu.com/exp/w=500/sign=4c4b0493367adab43dd01b43bbd5b36b/58ee3d6d55fbb2fbf744efa94f4a20a44623dc1a.jpg "")

在网络连接里， 右键单击已连接到Internet的网络连接，选择“属性”→“共享”，勾上“允许其他网络用户通过此计算机的Internet连接来连接(N)”并选择“虚拟WiFi”。

确定之后，提供共享的网卡图标旁会出现“共享的”字样，表示“宽带连接”已共享至“虚拟WiFi”

![共享pic](http://a.hiphotos.baidu.com/exp/w=500/sign=6b010000a61ea8d38a227404a70b30cf/dcc451da81cb39dbee06d0edd0160924aa183042.jpg "")

![共享2](http://g.hiphotos.baidu.com/exp/w=500/sign=a5924a6115ce36d3a20483300af23a24/b90e7bec54e736d1d1093ab39b504fc2d5626977.jpg "")

step 3：在终端中输入命令，回车，完成

操作：WIN+R 输入cmd，回车，在黑漆漆的窗口输入
```bash
netsh wlan start hostednetwork
```

这就搞定了，赶快拿出你的爪机搜搜有没有qingzia的wifi吧

PS：下次开机时，只需要执行step3就ok了

PSPS：如果不行的话，就执行step1&step3

PSPSPS：如果还是不行的话，就打电话给我吧

OVER

