# gRPC
iOS端集成gRPC的必要环境

###next, 这时候就要安装 grpc、protobuf 以及各种插件了，从网上找的资料中大部分都是这块内容，过程反复也不甚清楚，有些甚至都走不通。总结了下，[下载地址](https://github.com/enfinYH/gRPC.git)

###下载好后的样子：

![](http://i4.buimg.com/567571/0a273d148b8d8b21.png)

###next, 将文件复制到你工程目录下（根目录），讲<fileName>改成你工程的名字，例如我的工程名TestEnd,之后我们来配置一些参数：
- ####把<fileName>.podspec改名为TestEnd.podspec，打开该文件，第二行改为s.name     = "TestEnd"，保存并关闭。
- ####打开Podfile文件，把里面的<fileName>都替换为TestEnd，保存并关闭。
- ####打开Protos这个文件夹，这里存放的是需要的.proto文件，不可缺少，否则安装时报错。现在这里放了几个我们生成的文件。
####（注：官方DEMO中的grpc.podspec中指向的boringSSL实测是下不来的，可能跟在国内有关，故换成openSSL-for-ios） 

###好了，准备工作做完了，打开终端，cd到工程目录下，执行
<pre><code>pod install
</code></pre>
###不出意外如下图所示

![](http://i4.buimg.com/567571/c5a380fbf96a26a9.png)
###运行<工程名>.xcworkspace，编译一遍会报错，如下图所示：
![](http://upload-images.jianshu.io/upload_images/144854-001f9af445ab29c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
###按照下图所示，手动修改宏定义
###代码如下：
<pre><code>GPB_USE_PROTOBUF_FRAMEWORK_IMPORTS=1
</code></pre>
![](http://upload-images.jianshu.io/upload_images/144854-3e8416bd933b1b2a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###至此，gRPC环境已经全部集成
感谢简书作者:九天环佩




