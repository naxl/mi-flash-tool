2019-08-23
bug fix:
1，EDL支持Q版本sparse img中的type_fill模式

2019-09-04
bug fix:
1，修复由于sparse.img过大，造成原int型超出范围报错的debug，将int改为long型

2019-10-09
bug fix:
1，添加J1&J2区别ddr4和ddr5的新Hardware revision number

2019-10-30
bug fix:
1，更新edl SLA工具

2019-11-11
bug fix:
1，更新edl SLA工具，SLA 国内，海外，印度账号的刷机打点更新


2019-11-21 （该功能只有临时版提供给了J1&J2，其余版本暂时屏蔽）
bug fix:
1，添加FirmwareWrite升级ffu（J1&J2区分DDR版本）

2019-12-2
bug fix:
1，fastboot刷机流程退出事件中添加sleep时间来等待因为延迟的进程信息

2019-12-6
bug fix:
edl签名功能做如下更新
1.服务端ahaFlash接口做了更新，可以根据服务端返回的信息动态显示具体的权限等错误信息。
2.切换语种按钮的文本由中文简体修改为Chinese。

2019-12-18
bug fix:
1，添加FirmwareWrite升级ffu（非区分J1&J2流程，需要做provision）

2020-1-11
bug fix:
1，更新edl SLA工具，修复请求签名失败时提示文本显示错误

2020-3-14
bug fix:
1，更新fastboot版本
2，更新mes流程
3，支持MTK全擦刷机流程

2020-4-13
bug fix:
1，添加机械臂自动刷机逻辑

2020-4-14
bug fix:
1，添加EDL刷完机手机重启配置及功能

2020-5-7
bug fix:
1，艾特讯机械臂添加自动重连线程
2，PDL ConnectionIndex改为hubIndex+ConnectionIndex组合
3，修改收到机器就位信息后（DoRecMsg）独立更新UI

2020-5-18
bug fix:
1，FFU检索模式修改，添加判断刷机包FFULIST并比较版本逻辑
2，MTK da 读取设备时间改为1分钟

2020-5-20
bug fix:
1，优化PDL艾特讯机械臂加载设备时间长的问题

2020-6-5
bug fix:
1，添加MTK SLA mes逻辑

2020-6-8
bug fix:
1，FFU检索模式修改，改为只读工厂包里的ffulist
2，firehose获取应答时做wb导致provison时间太长增加等待应答时间

2020-7-6
bug fix:
1，fastboot刷机添加超时时间控制15分钟

2020-7-9
bug fix:
1，PDL艾特讯机械臂添加超时，心跳，停止指令

2020-7-14
bug fix:
1，PDL MES 接口添加获取FSN，并在刷机结束时候复制log到 日期/测试结果(pass/fail)/fsn@日期.txt中

2020-7-20
bug fix:
1，PDL MES 接口添加检测handle.txt文件逻辑

2020-7-22
bug fix:
1，PDL MES 流程由于checksn为耗时过程，在主线程阻塞ui更新，造成卡顿，改到刷机子线程处理mes流程

2020-7-30
bug fix:
1，工厂刷机增加工厂mes是否选择检查，添加mes结果log
2，PDL机械臂会出现混合心跳包log,造成解析穴位出错，修复该问题

2020-8-3
bug fix:
1，将更新mes结果调整到刷机线程处理，防止mes过慢影响ui更新，造成卡死
2，将PDL机械臂上送的信息处理方法放到线程中处理，防止过慢，影响UI更新，造成卡死
3,  2方案替换给启一个线程每30秒加载一下设备，去做刷机，机械臂信息想做list记录

2020-8-5
bug fix:
1，改成批次逻辑，一次刷机一个批次，配置文件中配置批次总数
2，同时添加计时（配置文件中配置），两次上料未到一个计时，自动为一个批次


2020-8-7
bug fix:
1，机械臂读取设备信息改为fastboot devices，不在刷机list为新设备，去做刷机

2020-8-9
bug fix:
1，机械臂读取设备信息改为循环读取


2020-8-28
bug fix:
1，机械臂读取设备信息改为来一台加载一台，根据穴位号只加枚举对应穴位号的usb设备列表
2，支持高通8350（the power reset command was too fast in Lahaina platform than before, so need to delay enough time for USB to shutdown when data transfer finished.），firehose reset_to_edl添加DelayInSeconds延迟启动时间
3，ffu改为只读刷机包，有就做ffu，没有就不做ffu

2020-9-10
bug fix:
1，修复MTK SLA bug

2020-10-19
bug fix:
1，处理UI显示问题

2020-11-20
bug fix:
1，MTK wb后添加重启动作

2020-12-11
bug fix:
1，适配高通edl刷机适配quick_reset流程

2021-1-15
bug fix:
1，兼容quick_reset流程和老的reset_edl流程

2021-1-26
bug fix:
1，添加自动备份存储功能：通过rom中的rawprogram_restore.xml文件做文件备份，该文件内容与rawprogram.xml格式一致，备份rom存储在工具restore目录下。

2021-2-20
bug fix:
1，在配置中添加只备份不刷机选项，用户可选定只备份不刷机，备份按照刷机包中的rawprogram_backup.xml做备份。
2，修改备份image存储文件夹格式，添加时分秒。
3，回刷rom还是按照rawprogram_restore.xml文件回刷，只会回刷本次刷机备份的rom。


2021-2-26
bug fix:
1，read指令获取应答截取raw数据逻辑修改，由于手机应答的格式不同，做了调整。
3，更新edl签名用户登录版本5.3.225.38。