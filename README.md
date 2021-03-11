# -
Pet-seat
宠物喂食器开发计划书
This project is developed using Tuya SDK, which enables you to quickly develop branded apps connecting and controlling smart scenarios of many devices. For more information, please check Tuya Developer Website.

一、方案标题
智能宠物喂食器

二、方案应用场景
有宠物且频繁出差、无法及时照顾宠物的家庭

三、具体方案
功能及实现方案：
1、自动喂食功能：定时、定量、分类添加食物。提供自动水箱。在喂食机中设置多个食物槽，分类放置不同食物比如谷物、颗粒混合宠物粮、药物等。可以通过APP设置投喂时间与量。
   实现方案:在APP中添加“食物槽”面板，可以设置每种食物的名字及投喂时间和量；食物余量监测采用压力传感器，暂定使用HX711模块。

2、手动喂食功能：手机App远程控制添加食物。
   实现方案:通过控制舵机或者电机进而控制食物槽挡板的开合实现。

3、实时监控功能。
   实现方案:暂定添加openmv摄像头模块，连接在WiFi SoC主控板（WB3S）通过WiFi连接云端，用户可以通过APP访问云端进而获得摄像头画面，从而实时监控。

4、语音呼唤功能：喂食器添加食物后，通过声音吸引宠物。
   实现方案:利用三明治语音WiFi通信板实现。

5、备用电源功能:添加备用锂电池，在断电后仍然可以保持工作，同时可以监测电量。
   实现方案:锂电池12V输出，经过稳压模块输出5V或3.3V为各开发板供电。

7、照明与安抚灯功能:添加柔色呼吸灯，既可照明也可以起到宠物安抚的作用。

8、异常监测功能:当餐盘有余量大于两日、或水箱水位连续两日变化低于阈值时发出警报，提醒主人。
   实现方案:在主控板中实现相关逻辑，水箱水位监测采用谐振式高稳定性水压传感器。

9、宠物伴侣功能:添加可伸缩后备仓，内固定宠物玩具，例如猫抓盘、咬骨、立架等，可以不定时打开后备仓，解决宠物孤独烦闷问题。
   实现方案:伸缩仓使用滑轨设计，加上电机驱动轮带，内部物品固定放置。

所需物料
1、H桥直流电机驱动功能板

2、语音 Wi-Fi 通信板（VWXR2）或 Wi-Fi soc 主控板（WB3S），若控制功能有限则添加stm32f4系列mcu。

3、语音播放器

4、openmv摄像头模块

5、柔色呼吸灯若干

6、步进电机或者舵机若干

7、HX711压力传感器若干，谐振式水压传感器若干

8、涂鸦平台（云服务、app、低代码开发）

四、开发计划
3月1日~3月10日：确定计划方案。

3月11日~3月14日：根据计划方案购买硬件设备，测试本地摄像头模块、压力传感器模块、电机控制等各部分。

3月15日~3月20日：整合所有模块，完成嵌入式系统代码开发。并进行调试。

3月21日~3月24日：APP功能实现，利用涂鸦平台低代码开发。搭建云平台，同样利用涂鸦平台。

3月25日~3月29日：整体功能调试。

