---
layout: post
title:  "setup react-native for android with ubuntu!"
date:   2016-01-12 15:23:23 +0800
categories: qihw react-native
---


#### 安装 Android SDK.    
1. https://developer.android.com/sdk/installing/index.html?pkg=tools
2. 解压后，运行 /tools/android  ,打开Anroid SDK Manager，安装相应的andorid 版本的SDK.
3. 注意：国内被墙，用代理：
	在『Android SDK Manager - Settings』窗口中，在「HTTP Proxy Server」和「HTTP Proxy Port」输入框内填入 mirrors.neusoft.edu.cn  或腾讯的 android-mirror.bugly.qq.com  和 80，并且选中「Force ...」复选框。    
4. 注意：一定要安装 Android6.0(v23) ,react-native构建时会直接找这个sdk. 还有对应的tools-对应版本的sdk build-tools也要装.
    要安装Extras - Android Support Repository ,否则会出错 : Could not find com.android.support:appcompat-v7:23...
    另:如果windows/mac 可以装Configure hardware acceleration (HAXM), otherwise the emulator is going to be slow. 但目前linux上不支持。
5. 安装： Genymotion ,创建和管理使用 模拟器，确实看起来功能强大,使用方便.
        
####  安装  watchman ,
watchman 的用途是自动检测文件变化进行构造用的。需要先安装 :   autoconf  automake ,还有python python-dev  ,下载 watchman 源码，编译.
{% highlight bash %}
	$ sudo apt-get install autoconf automake 
	$ sudo apt-get install python python-dev 
	$ git clone https://github.com/facebook/watchman.git
	$ cd watchman
	$ git checkout v4.3.0  # the latest stable release
	$ ./autogen.sh
	$ ./configure
	$ make
	$ sudo make install
{% endhighlight %}

#### 安装 react-native-cli:
    $ npm install -g react-native-cli 

#### 创建项目：
    $ react-native init testProject       

#### 运行项目：
1.  要运行模拟器或者真机，能连上adb .
2.  项目目录下运行 npm start .  否则在运行android时会提示 react native android failed to load JS bundle
3.  项目目录下运行 react-native run-android 
    


