# UnityXcodeApiUpdate 个人修改版本说明（中文版文档）
其实与其说是文档，个人跟倾向于搞成个教程。
* 这个原本是来源于日本的一个开发者弄的一个基于XcodeApi的用于拷贝第三方或者自定义xcode代码（可以理解成xcode5的XUporter）。个人原本自己写了一套（很久以前），发现这个写的比我好很多（囧），于是我就fork过来基于我自己项目情况进一步扩展了。  

## 使用流程
* 使用流程的话我就不一一截图，仅仅文字描述过程。
1. XcodeProjectSetting 这个是它的配置文件，原本支持的主要是这几个点
* URL Scheme
* Framework(自带库)
* Linker Flag
* Framework search path
* Compiler Flag
* 是否 Bit Code启动
* ATS
* ApplicationQueriesSchemes

后边我新增的主要就这个点
* tbl文件支持

也就是一些自带库都可以依靠这个配表配置即可，然后生成Xcode的时候就会把这些信息设定进去。

2. 关于如何支持第三方代码或者库等资源
* 第三库的话主要关注的参数就是Copy Directroy Path这个路径即可，使用思路就是自己在某个路径建立个文件夹，把第三方库等资源丢进去，然后这个参数填刚刚的路径就好。它再拷贝的时候相关设定都已经做好了。

##其它事项
* 其实这个就主要剩下还要考虑的是多平台支持了，关于这个可以通过配表实现，这个项目还在弄，以后好了再详细说明。
