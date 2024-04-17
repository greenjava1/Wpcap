一、下载源码文件
下载源码文件WpcapSrc_4_1_3.zip

https://www.winpcap.org/devel.htm

二、编译步骤
1、解压文件，使用VS2017分别打开winpcap\packetNtx\Dll\Project\Packet.sln和wpcap\PRJ\wpcap.sln两个工程文件，如果提示版本升级，一直确认即可。

2、打开Packet.sln，选择Release no netmon和Win32。编译生成Packet.dll、Packet.lib。

如果编译时提示无法找到“airPcap.h"。
选择属性 -> C/C++ -> 预编译器，删除掉HAVE_AIRPCAP_API宏。
x64 release 可能要去掉 无用的npptools.lib依赖

3、打开wpcap.sln，选择Release-No AirPcap和Win32。编译生成wpcap.dll、wpcap.lib。

如果编译时提示无法找到Packet.lib，
选择属性 -> 链接器 -> 常规 -> 附加库目录，修改lib库为第二步生成的路径。

4、运行create_include.bat，WpdPack目录下生成Include。
