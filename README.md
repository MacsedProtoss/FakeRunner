# FakeRunner

## 简介

墙内的各位大学生虽然不用天天学刁强国，却早已面临各种跑步打卡软件的荼毒。而FakeRunner是一个跑步打卡软件的通用解决方案

它有以下**优点**：

- 通用：这意味着不需要根据各个软件进行定制
- 安全：首先更难被发现（因为使用的是目前基本无防范方法的方案，支持每次使用时自定义路线），其次法律无责（因为没有对任何软件进行crack等hack行为），再次没有猪队友（设置了自编译这个门槛，使得那些纯小白被拒之门外）
- 易用：看完本readme就完全可以使用了

它有以下**缺点**：

- 必须使用iOS+macOS才能进行

## 使用方法

1 . clone本仓库
2 . 在[此网站](http://www.gpsies.com/createTrack.do?source=post_page---------------------------)上选择路径点并生成gpx文件。

> 最多支持20个路径点，默认不自动沿路走，也可以手动打开自动按照路径来走。**速度调整**和**步伐调整**调整一个即可，调整后另一个会同步调整。建议速度根据配速要求来设置。全部完成后选择**导出**，记录为**GPX Track**，然后**下载**。

![step2.1](https://github.com/CGSportFucker/Images/blob/master/step2.1.png?raw=true)

![step2.2](https://github.com/CGSportFucker/Images/blob/master/step2.2.png?raw=true)


3 . 打开GPXFormater文件夹里的工程，选择run来编译并运行该软件，然后把下载的文件拖入到这个窗口即可。**拖入一次显示Patch Finished即可！**

![step3](https://github.com/CGSportFucker/Images/blob/master/step3.png?raw=true)

4 . 打开FakeRunner文件夹里的工程，同时将你的手机与Mac连接。在工程中先找到sign处填入你自己的team，然后把patch之后的gpx文件拖入到项目中。

![step3](https://github.com/CGSportFucker/Images/blob/master/step4.png?raw=true)


5 . 将FakeFunner的build target设置为你的iPhone（iPad），然后run工程。当你的iOS设备上已经显示了一个白色的app界面后，在Xcode中选择debug-simulate location-你的gpx文件名

![step3](https://github.com/CGSportFucker/Images/blob/master/step5.png?raw=true)

6 . All done， 现在打开你的跑步软件开始跑步吧 **注意跑步过程中不能断开与手机的连接，跑完之后要在Xcode中中止运行，否则你的定位会出现bug（该bug重启后可以恢复）**

## 原理

Xcode在debug的时候会hook iOS全局的定位API，所以无论什么软件都会被虚假定位到gpx文件所描述的位置