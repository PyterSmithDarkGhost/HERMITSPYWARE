
文档地址：[https://www.lookcos.cn/docs/hermit](https://www.lookcos.cn/docs/hermit)

已经修复截图相关功能，并且界面布局分析也很好用了。

### Hermit简介

Hermit，是一款用于Android自动化测试的软件。  
它不依赖于ADB，运行于安卓，软件自身提供 restful API。因此你只需要通过发送HTTP请求，它便能将对API的调用转化为对手机的操作。
支持快速的点击、滑动、读取与设置剪切板（支持中文）、模拟输入、寻找控件并点击等一系列操作，支持可视化布局分析。  
大小不到 3Mib，默认运行端口`9999`。

#### 基于无障碍的功能

1. 坐标点击
2. 坐标滑动  
3. 根据控件id的点击（如有多个相同id，可根据次序点击）
4. 根据控件text的点击（同上，可根据次序点击）
5. 根据控件content-desc的点击  
6. 查看屏幕截图  
7. 模拟输入功能（支持中文）
8. 十大全局功能（返回、按下home键、最近任务、显示通知、快速设置、长按电源键、分屏、锁屏、截屏）
9. 实时获取界面控件详细信息  

#### 基于Root的功能

1. 坐标点击  
2. 坐标滑动
3. 屏幕截图
4. 申请并判断root权限
5. 发送任意keyevent
6. 长按坐标
7. 根据包名启动APP

#### 获取设备信息能力  

0. 获取、设置剪切板内容（支持中文）
1. 设备屏幕长宽  
2. CPU 最大、最小、实时频率
3. CPU名
4. 内存总量、可用量
5. 存储总量、可用量
6. 所有安装的包名
7. 设备语言、系统版本号、手机型号、手机厂商

#### 可交互的布局可视化分析功能

类似Android Studio的LayoutInspector，可以分析界面层次和范围、获取界面上的控件信息，进而方便点击、滑动等操作。  
可通过鼠标点选控件（详情见[布局分析说明](/zh-cn/uiautomator)），查看对应信息:  

1. bounds （可点击范围）
2. boundsInParent
3. checked
4. class
5. clickable
6. package
7. resource-id （控件id）
8. scrollable
9. text （控件文本）
10. content-desc (控件描述)

![screencapture3.png](https://lookcos.cn/usr/uploads/2021/02/3890288493.png)

### 工作方式

![](https://www.lookcos.cn/usr/uploads/2021/01/2021012804240032.png)

#### 注意

> 可能示意图画的略微繁杂了点，简而言之：Hermit在安装并运行之后，会提供HTTP API，通过调用相应的API，进而转化为对手机的操作。因此，可以支持绝大多数语言。正是因为其基于restful API，所以可扩展性大大提升，目前已制作了基于其API的Python模块，使操作的易用性得以提升。
