# curl-
VS2022下使用curl，libcurl

编译和使用方法:
1.解压后执行下curl-master下的buildconf.bat
2.运行VS2022的x64 NativeTools Command Prompt
3.输入：cd 路径\curl-master\winbuild 进入到winbuild文件夹
4.输入：nmake /f Makefile.vc mode=static VC=15 MACHINE=x64 debug=yes点击回车
5.如果顺利.h和lib文件都将会生成到.../curl-master/builds文件夹下
6.在vs里的vc++目录-包含目录 添加.h文件  例如C:\curl\curl-master\builds\libcurl-vc15-x64-debug-static-ipv6-sspi-schannel\include
7.在vs里的链接器-输入-附加依赖项里添加
libcurl_a_debug.lib
Ws2_32.lib
Wldap32.lib
winmm.lib
Crypt32.lib
Normaliz.lib
就可以了。

引用方法
#define CURL_STATICLIB
#define HTTP_ONLY
#include <curl/curl.h>

