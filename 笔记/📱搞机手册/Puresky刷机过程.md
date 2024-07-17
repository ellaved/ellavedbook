![img](https://joinjonpic.s3.bitiful.net/2024012410363798957.jpeg?fmt=webp&q=48&w=800)

PureSky官改刷机教程&常见问题解答

![img](https://joinjonpic.s3.bitiful.net/2024012410363798907.jpg?1697655704?fmt=webp&q=48&w=800)

2023-05-21 小米13

一、写在前面
由于很多刚入门的玩机小白在面对刷机时存在一些困惑，此图文教程为了让小白们少走弯路，正确刷机。之前也出过此教程，但是由于原方案有些老旧，有些内容不适用现版本，所以本次更新一下，方便小白们食用。
温馨提示：刷机有风险，有重要的数据请自行备份，如果在手机上备份数据，备份完成后请将备份的数据包转移到电脑或者优盘上，否则清除数据后备份将不复存在
PureSky官改网站：[查看链接](https://jk.511i.cn/)



备份第一步！

本图文分为以下几个部分
①解锁Bootloder
②PureSky刷机包基本信息解读
③通过线刷刷入ROM
④通过卡刷刷入ROM
⑤刷机常见问题及解决方案
--◁=======分隔符=======▷--

![img](https://joinjonpic.s3.bitiful.net/2024012410363798450.jpg?fmt=webp&q=48&w=800)

二、解锁小米手机的Bootloader
注意：解锁会清除全部数据，解锁之前请备份数据！
①Bootloader是什么?(仅针对安卓手机)
简单地说Bootloader就是安卓系统运行前的一段程序，负责初始化硬件、加载内核、检验镜像签名等操作。我们刷机所涉及到的FASTBOOT模式只是非常片面的部分，就刷机来说一般常用到的有镜像刷写命令(fastboot flash)、槽位切换命令(fastboot set_active)、参数获取命令(fastboot getvar)、oem命令(fastboot oem)等。执行Fastboot命令，需要用到谷歌的platform-tools工具，详情见 [查看链接](https://developer.android.google.cn/studio/releases/platform-tools?hl=zh-cn)
②为什么要解锁Bootloader?
上面提到镜像检验是Bootloader的一个功能，它需要检测各个分区的文件是否符合厂商的签名，如果Bootloader处于锁定状态，那么检测到不符合厂商签名的文件那么手机将无法启动，而官改包以及各种第三方刷机包都是由第三方开发者修改或者构建的，不符合厂商的签名，所以为了能刷入第三方ROM包，需要解锁Bootloader才能实现。
③小米手机解锁Bootloader教程
第一步：在手机上登录小米账号并插入SIM卡，随后前往设置开启开发者选项，进入开发者选项找到设备解锁状态，将账号与设备绑定
第二步：下载小米官方解锁工具，传送门：[查看链接](https://www.miui.com/unlock/index.html)

![img](https://joinjonpic.s3.bitiful.net/2024012410363790357.jpg?fmt=webp&q=48&w=800)

点击立即解锁

点击立即解锁会下载一个miflash_unlock-xxx.zip的压缩包，将压缩包解压，双击miflash_unlock.exe

![img](https://joinjonpic.s3.bitiful.net/2024012410363796144.jpg?fmt=webp&q=48&w=800)

点击miflash_unlock

进入解锁工具后登录手机上登录的账号

![img](https://joinjonpic.s3.bitiful.net/2024012410363792968.jpg?fmt=webp&q=48&w=800)

登录小米账号

第三步：将手机关机，然后按住电源键和音量–键，手机会进入到FASTBOOT模式，如下图所示，较老的设备会显示一个兔子和FASTBOOT字样，然后用数据线连接电脑

![img](https://joinjonpic.s3.bitiful.net/2024012410363797488.jpg?fmt=webp&q=48&w=800)

进入FASTBOOT模式

进入解锁工具，将手机连接电脑后会提示已连接手机，随后点击解锁即可，再提醒一下，解锁会清除所有数据

![img](https://joinjonpic.s3.bitiful.net/2024012410363791286.jpg?fmt=webp&q=48&w=800)

连接手机，点击解锁

--◁=======分隔符=======▷--

![img](https://joinjonpic.s3.bitiful.net/2024012410363796626.jpg?fmt=webp&q=48&w=800)

三、PureSky刷机包基本信息解读
①刷机包名字组成

![img](https://joinjonpic.s3.bitiful.net/2024012410363792215.jpg?fmt=webp&q=48&w=800)

PureSky_机型代号_机型名称_版本号_MD5前十位_刷机方式_安卓版本.zip
其中，需要注意的是，刷机方式有3中类型
Fastboot:只能通过线刷刷入，例如
PureSky_ELISH_PAD5ProWiFi_V14.0.23.5.15.DEV_bsk463sb4i_Fastboot_13.zip
TwoInOne:既可以线刷，又可以卡刷，例如
PureSky_FUXI_Mi13_V14.0.23.5.15.DEV_bedsk7w9w3_TwoInOne_13.zip
Recovery:只能通过卡刷刷入，例如
PureSky_CEZANNE_HMK30U_22.4.15_ceb3j4ok4a_Recovery_12.zip
②刷机包内容

![img](https://joinjonpic.s3.bitiful.net/2024012410363798907.jpg?fmt=webp&q=48&w=800)

刷机包文件内容

bin:保存fastboot等刷机工具
images:保存刷机镜像文件
META-INF:可卡刷的刷机包卡刷脚本
PureSkyFlashUnix:Linux或MacOS线刷脚本
PureSkyFlashWindows:Windows系统线刷脚本
--◁=======分隔符=======▷--

![img](https://joinjonpic.s3.bitiful.net/2024012410363796667.jpg?fmt=webp&q=48&w=800)

四、通过线刷刷入PureSky刷机包
①Windows系统刷机教程
第一步：下载ROM包，并解压到某个位置，等待解压完毕

![img](https://joinjonpic.s3.bitiful.net/2024012410363797488.jpg?fmt=webp&q=48&w=800)

解压刷机包

第二步：双击PureSkyFlashWindows.bat开始执行刷机脚本

![img](https://joinjonpic.s3.bitiful.net/2024012410363798907.jpg?fmt=webp&q=48&w=800)

双击刷机脚本

第三步：对于二合一类型的刷机包需要等待转换super.img.zst，对于Fastboot类型的不需要转换

![img](https://joinjonpic.s3.bitiful.net/2024012410363794367.jpg?fmt=webp&q=48&w=800)

等待转换

第四步：将手机进入到FASTBOOT模式并连接电脑

![img](https://joinjonpic.s3.bitiful.net/2024012410363797488.jpg?fmt=webp&q=48&w=800)

第五步：认真阅读文字提示，根据提示输入y/n，自行选择是否需要清除数据、是否root、是否刷入twrp

![img](https://joinjonpic.s3.bitiful.net/2024012410363798957.jpg?fmt=webp&q=48&w=800)

根据提示选项刷机选项

第六步：耐心等待刷机完毕，如下图所示即为刷机完毕

![img](https://joinjonpic.s3.bitiful.net/2024012410363792215.jpg?fmt=webp&q=48&w=800)

刷机完毕

②Linux或MacOS刷机教程
第一步：将刷机包解压到某一位置

![img](https://joinjonpic.s3.bitiful.net/2024012410363799829.jpg?fmt=webp&q=48&w=800)

解压刷机包

第二步：将手机关机，按住电源键和音量–键，进入到FASTBOOT模式

![img](https://joinjonpic.s3.bitiful.net/2024012410363797488.jpg?fmt=webp&q=48&w=800)

第三步：打开解压的位置，在此位置打开终端，以Deepin为例，定位到解压文件夹，右键鼠标，在终端中打开

![img](https://joinjonpic.s3.bitiful.net/2024012410363792215.jpg?fmt=webp&q=48&w=800)

定位文件夹，打开终端

第四步：执行刷机脚本，确认在解压后的位置中打开终端后，输入sh ./PureSkyFlashUnix.sh，成功运行会有文字提示如下

![img](https://joinjonpic.s3.bitiful.net/2024012410363797154.jpg?fmt=webp&q=48&w=800)

第五步：如果一直卡在<waiting for any device>，可能是由于当前用户无法访问设备，请Ctrl+C打断，然后以sudo启动脚本：
sudo sh ./PureSkyFlashUnix.sh
正常刷入如下

![img](https://joinjonpic.s3.bitiful.net/2024012410363798957.jpg?fmt=webp&q=48&w=800)

以root用户运行脚本

第六步：等待刷机完毕

![img](https://joinjonpic.s3.bitiful.net/2024012410363795680.jpg?fmt=webp&q=48&w=800)

刷机完成

--◁=======分隔符=======▷--

![img](https://joinjonpic.s3.bitiful.net/2024012410363796718.jpg?fmt=webp&q=48&w=800)

五、通过卡刷刷入PureSky刷机包
卡刷前提：需要手机已安装第三方Recovery，例如TWRP、PBRP等，下面以TWRP为例
第一步：将刷机包下载到手机上
第二步：将手机关机，按住电源键和音量+键，将手机进入到Recovery模式

![img](https://joinjonpic.s3.bitiful.net/2024012410363792073.jpg?fmt=webp&q=48&w=800)

TWRP首页

第三步：进入TWRP后，点击安装–>定位到下载的ROM所在位置，选中该ROM

![img](https://joinjonpic.s3.bitiful.net/2024012410363796667.jpg?fmt=webp&q=48&w=800)

选择刷机包

第四步：点击刷机包后，进去会有一些选项，这些选项都不用管也不用动，直接滑动刷入

![img](https://joinjonpic.s3.bitiful.net/2024012410363790672.jpg?fmt=webp&q=48&w=800)

第五步：开始刷入ROM，会检验机型代号以及MD5是否正确，以确保刷机的安全性

![img](https://joinjonpic.s3.bitiful.net/2024012410363798023.jpg?fmt=webp&q=48&w=800)

第六步：会提示是否禁用模块，如果你之前安装了面具模块，并且害怕会因为某些模块导致不开机，可以根据提示禁用模块

![img](https://joinjonpic.s3.bitiful.net/2024012410363798501.jpg?fmt=webp&q=48&w=800)

第七步：选择是否刷入Root和是否刷入twrp，建议在提示是否刷入twrp时选择是，否则刷完没有第三方Recovery

![img](https://joinjonpic.s3.bitiful.net/2024012410363796667.jpg?fmt=webp&q=48&w=800)

第八步：等待刷机完毕，刷机完毕如下图，刷完不用点击清除Dalvik

![img](https://joinjonpic.s3.bitiful.net/2024012410363798501.jpg?fmt=webp&q=48&w=800)

第九步：重启系统，刷完后点击重启，确定当前槽位为A后点击系统，卡刷完毕

![img](https://joinjonpic.s3.bitiful.net/2024012410363790631.jpg?fmt=webp&q=48&w=800)

--◁=======分隔符=======▷--

![img](https://joinjonpic.s3.bitiful.net/2024012410363796626.jpg?fmt=webp&q=48&w=800)

六、刷机常见问题及解决方案
①关于是否需要清除数据
⑴什么情况必须清除数据？
官方包刷解密Data的官改包
不解密的官改包与解密的官改包互刷
其他第三方ROM与官方包或者官改包切换
⑵降级是否需要清除数据？
降级不是必须清除数据，小版本的降级无需清除数据，安卓版本的降级建议清除数据，但是降级操作需要关闭锁屏密码，否则指纹或者人脸可能解锁失败，甚至密码都无法解锁，如果不小心降级了又忘记了关闭锁屏密码，请用MT管理器或者进入TWRP删除/data/system/locksetrings.db
|
②刷机后无限重启如何解决
⑴面具模块的问题导致，进入twrp，高级，文件管理，定位到 /data/adb/modules，删除这个文件夹，然后重启
⑵安装了没有签名的软件导致，升级或降级系统后导致软件签名冲突，进入twrp，高级，文件管理，定位到/data/system/package_cache，/data/dalvik-cache，删除这两个文件夹
⑶解密和不解密的包互刷导致，这种情况只能清除数据解决
⑷刷机操作失误导致，尝试重新刷一次，确认操作是否有误
⑸ROM包本身有问题，尝试刷回上一个版本，或者跟ROM开发者反馈
|
③开机后面具如何正确修复环境
开机后显示“需要修复运行环境”，这个时候点击取消

![img](https://joinjonpic.s3.bitiful.net/2024012410363798560.jpg?fmt=webp&q=48&w=800)

点击取消之后，点击上面Magisk那个安装

![img](https://joinjonpic.s3.bitiful.net/2024012410363790581.jpg?fmt=webp&q=48&w=800)

随后点击直接安装，并点击开始

![img](https://joinjonpic.s3.bitiful.net/2024012410363792271.jpg?fmt=webp&q=48&w=800)

安装完成之后重启

![img](https://joinjonpic.s3.bitiful.net/2024012410363794795.jpg?fmt=webp&q=48&w=800)

如果重启完显示无法获取，请卸载Magisk应用，然后进TWRP安装Magisk，然后重启，重启以后手动安装对应版本的Magisk，再从修复运行环境那里开始即可
