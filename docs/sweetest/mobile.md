# Sweetest 移动端测试


## 环境配置

Sweetest 支持 Android/iOS 应用测试，底层使用的是 Appium 库，所以环境配置主要是 Appium 和 Android/iOS 环境的搭建。

### Windows Android Appium 环境搭建

#### 安装 Java

参见：https://www.jianshu.com/p/169bc950316b

> 注意使用 jdk 8

#### 安装 Android SDK

参见：https://www.cnblogs.com/zyjrjgzyx/p/9800137.html

#### 安装 Node.js

参见：https://www.cnblogs.com/zhouyu2017/p/6485265.html

#### 安装 Appium

参见：https://www.jianshu.com/p/d271092518a4

#### Appium Desktop Inspector 安卓真机配置（Windows）

参见：https://www.cnblogs.com/kaerxifa/p/7808073.html

android adb devices offline的解决办法：

adb kill-server
adb start-server

https://blog.csdn.net/liuhu767/article/details/49861687

Realme X 无权限问题
last option in dev mode : Disable permission monitoring
https://forum.xda-developers.com/find-X/help/enable-writesecuresettings-app-adb-t3855596

Appium Settings

权限设置
https://github.com/TilesOrganization/support/wiki/How-to-use-ADB-to-grant-permissions#windows-10

adb shell "dumpsys window w|grep \/|grep name=|sed 's/mSurface=Surface(name=//g'|sed 's/)//g'|sed 's/ //g'"

#### 安装 Appium-Python-Client

```shell
pip install Appium-Python-Client
```
文档：https://github.com/appium/python-client


### MacOS iOS Appium 环境搭建

https://www.jianshu.com/p/ae8846736dba
https://blog.csdn.net/weixin_30660027/article/details/101920755


## 关键字

### 锁屏状态，解锁，锁屏，重启

如下，我们可以对手机的锁屏状态进行判断（步骤1），如果是锁屏状态则解锁（步骤2，3，4），然后启动APP初始界面

|前置条件 | 测试步骤 | 操作     | 页面 | 元素                        |
| ------- | ------- | ------- | ---- | --------------------------- |
| SETUP	  |   ^1    | 锁屏状态 |      |                             | 	
|         |   >2    | 解锁	   |      |                             |
|         |   >3    | 滑动     |      |500,2000\|500,1000           |
|         |   >4    | 轻点     |      |d#1\|d#2\|d#3\|d#4\|d#5\|d#6 |
|         |    5    |重启      |      |                  |
