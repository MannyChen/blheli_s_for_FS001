### 四合一电调BL_S固件烧录教程

#### 前期准备

1.硬件方面

贴片完成的电调*1（先将控制板烧录完成，再焊接到功率板上）

C2下载器*1（下载器购买链接[C8051F仿真器 usb仿真器 JTAG/C2 下载线 U-EC5 ML-EC3 EC6-淘宝网 (taobao.com)](https://item.taobao.com/item.htm?spm=a230r.1.14.24.1fad7e7fH3JVjL&id=35784484754&ns=1&abbucket=17#detail)）

1.27mm间距烧录探针*1(没有也可以直接焊接线材)

可调直流稳压电源*1

杜邦线若干

2.软件方面

固件烧录上位机：Flash Programming Utility

固件本体：J_H_30_REV16_7.HEX

调参工具：BLHeliSuite（安装包自行寻找，任选其一）

​					ESC - Configurator（https://esc-configurator.com）			



#### 开始烧录

1.首先先进行硬件方面的连接

使用4根杜邦线分别连接C2下载器的C2CK（即C2K）和C2D端子，以及3.3V和GND供电，另一段连接烧录探针（注意烧录器的缺口朝向，该图所示为下载器端口面向操作者）

![Snipaste_2023-03-14_22-42-19](D:\桌面\定制电调烧录\image\Snipaste_2023-03-14_22-42-19.png)

2.连接下载器到电脑，并安装Flash Programming Utility（software文件夹中的utildll.exe）

安装完成后打开软件，正常情况下软件会自动识别到C2下载器并显示如图所示的Adaptation Selection中的下载器ID，如果没有，则按照下图操作：

![Snipaste_2023-03-06_12-58-30](D:\桌面\定制电调烧录\image\Snipaste_2023-03-06_12-58-30.png)



3.下载器确认软件能够正常识别到后，使用烧录探针接触PCB上的相应触点（或者直接焊接线材到触点上），如图中红框所标注。（如果探针接触不良的情况下请选择焊接触点进行连接）

![Snipaste_2023-03-14_22-36-41](D:\桌面\定制电调烧录\image\Snipaste_2023-03-14_22-36-41.png)

4.确保硬件连接稳定后，选择软件中的Connect 选项，正常情况下红框所示会显示MCU的型号ID等信息，代表通信正常。然后选择跳转下载页面。

![Snipaste_2023-03-06_13-18-41](D:\桌面\定制电调烧录\image\Snipaste_2023-03-06_13-18-41.png)



5.在该页面选择Browse选项，打开文件夹后选取相应固件（software文件夹中的J_H_30_REV16_7.HEX）后选择Download选项，正常情况下等待进度条加载完成既可。

依次给4个MCU重复上述（3-5步骤）

![Snipaste_2023-03-06_12-59-08](D:\桌面\定制电调烧录\image\Snipaste_2023-03-06_12-59-08.png)



**作者：Meski**

**2023.3.14**
