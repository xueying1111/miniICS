#使用文档

1.下载与安装
通过git下载本项目

`$sudo git clone https://github.com/xueying1111/miniICS.git`

下载完成后，进入util目录，使用如下命令安装

`$sudo ./install.sh`

2.使用
a.通过命令行，进入目录`examples`,运行如下命令。

`$sudo python miniedit.py`

启动可视化操作窗口

b.通过左侧工具栏，建立自己的拓扑。

c.完成拓扑的创建后，在上方工具栏找到Edit->Preferences,勾选Start CLI,若未勾选，则不会启动命令行模式。

d.点击左下角Run按钮，启动。

e.此时控制台会进入mininet命令行模式，在初始化完成时，由于本项目基于零信任基础建立，所有主机之间是互相断开的状态，需要身份验证通过后方可建立连接。
此时使用`pingall`命令，会发现主机之间是ping不通的状态，此时，我们需要让他们建立连接，使用如下命令操作：

`valid host1 host2 password`

该valid命令接受三个必要参数：
host1:此参数为需要建立的两台主机中的其中一台，为其名称，可通过miniedit界面查看主机名称，也可通过右键主机，选择Properties,修改Hostname修改该名称。
host2：此参数为需要建立的两台主机中的另一台，同上。
password：此参数为设置的秘钥，可通过项目目录下cli.py文件，找到SDPICSPwd参数，修改秘钥。

在密码正确，且两台主机都存在的情况下，校验通过，会为这两台设备建立连接，使用`ping host1 host2`或`pingall`查看连接状态，此时会发现除了这两台主机能相互ping通，其他主机都处于无法ping通状态。



