# qrcode
开发完app应用程序后我们都会提供个二维码，方便提供下载链接，那么在做这项需求的时候需要注意什么
首先我们需要知道二维码是个是个什么概念，以及他的应用场景是什么
一般二维码是个地址，我们用手机相关软件去问（扫描）它的时候相当于直接跳转到该地址，
当然我们今天的主要话题不是关于二维码，而是使用二维码下载相应的应用安装包文件，
对于国内我们一般扫描二维码常用的是微信或者相机浏览器，而这些设备主体分为安卓与IOS，
那么在扫描二维码的时候我们就需要注意了，不同的设备下载安装包途径是不一样的
一般的IOS是直接到Appstore的，安卓是直接下载相应的apk安装包文件，
故此我们在二维码所对应的网址下面是要做个对设备型号的判断即可，选择相应的设备跳转就可以了，
这是常规扫描，国内一般喜欢使用微信扫描二维码，但是微信又不支持在软件内部下载apk文件，
所以我们需要再微信扫描后的页面里面做个跳转浏览器的操作，故此我们还要多个
识别微信的过程，当在微信扫描的时候弹出遮罩层提示浏览器打开，并地址指向浏览器，此时重新在浏览器下载即可，
详细可以参考代码
备注：在做测试的时候可以在本地搭个服务器，在同一局域网扫描检查界面
