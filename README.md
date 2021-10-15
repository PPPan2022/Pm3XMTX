# PM3 复制ID卡
## tep1、知识储备

### 1、proxmark3能干啥

Proxmark3 是一款国外安全团队研发的开原设备，可以破解IC卡、ID卡等等，如门禁卡、学生卡、饭卡、公交卡、地铁卡等等。

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015152225752.png" alt="image-20211015152225752" style="zoom:50%;" /> 



### 2、卡片知识

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015155501823.png" alt="image-20211015155501823"  /> 

## step2、环境要求

> ①win10/win7
>
> ②需要复制的门禁卡
>
> ③空白卡一张
>
> ④PM3驱动
>
> ⑤Proxmark Tool

## step 3、读卡、识别卡类型

###  1、win10系统接入PM3

> win10 系统会自动识别并安装硬件驱动，用数据线把PM3硬件接入系统，查看设备管理，如图，出现COM口则代表硬件接入成功。

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015140733437.png" alt="image-20211015140733437" style="zoom:50%;" /> 





<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015140803511.png" alt="image-20211015140803511" style="zoom:50%;" /> 



### 2、win7系统接入PM3

> win7 系统无法自动识别硬件，需要手动安装硬件驱动。
>
> 设备正常接入的情况下，会出现如图所示“未知设备”。



<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015103451397.png" alt="image-20211015103451397" style="zoom:50%;" /> 



> 手动安装驱动
>
> 操作步骤：打开设备管理器 > 操作 > 添加过时硬件 >安装我手动从列表选择的硬件 > 选择端口 > 从磁盘安装 >选择下载好的驱动文件> 始终安装此驱动程序



<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015140843691.png" alt="image-20211015140843691" style="zoom:50%;" /> 





![image-20211015104932286](https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015104932286.png) 



<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015105205665.png" alt="image-20211015105205665" style="zoom:50%;" /> 



<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015104741726.png" alt="image-20211015104741726" style="zoom:50%;" /> 



<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015141554727.png" alt="image-20211015141554727" style="zoom:50%;" /> 

> 出现下图，表示驱动安装成功。

![image-20211015141923928](https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015141923928.png) 

### 3、读卡（以win10系统为例）

> 打开	Proxmark Tool.exe   >  选择com口  ，我这里是5口，所以我选择COM5。
>
> 端口选择正确不会有提示信息，如下图。

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015142847616.png" alt="image-20211015142847616" style="zoom:50%;" /> 



> 端口选择错误，会出现如图报错信息。

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015143049348.png" alt="image-20211015143049348" style="zoom:50%;" /> 



> 输入命令	hw  tune	回车，查看设备天线电压，以测试设备是否正确连接。(有时候输入命令可能需要多等几秒钟才会输出结果。)

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015143317191.png" alt="image-20211015143317191" style="zoom:50%;" /> 

> 把要破解的卡片放在圆形天线区，对卡片数据进行读取

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015144651173.png" alt="image-20211015144651173" style="zoom:50%;" /> 

## step 4、开始复制卡片

> 在第一节知识储备，卡片表格里面有说明，EM4XX卡片也叫ID卡，可以用T5577卡片来进行克隆。
>
> 取下圆形天线区的EM410X卡片，把空白T5577卡片放入方形天线区，进行克隆

<img src="https://gitee.com/little-magician/picture-resources/raw/master/MarkDown%20/image-20211015145310926.png" alt="image-20211015145310926" style="zoom:50%;" /> 

> 确认卡片是否复成功
>
> 把复制好的卡片放入圆形天线区，并进行数据读取，发现卡片类型变成Em410x，并且卡片ID和被破解的ID一样则表示卡片克隆成功

## step5、工具、使用手册、驱动

​     [资料下载](https://github.com/XMTongXie/proxmark3)

## step6、对新手的一些建议

> 为了能更快的上手PM3，我建议新手们要多注意细节，因为很多时候阻止你成功的问题并不是多么困难。
>
> 1、确保设备的连通性，在反复确认配置没错，环境没错，但Proxmark Tool.exe就是连接不上设备的情况下，你该考虑一下硬件问题，一般都会是数据线的问题。(我在这里栽了个跟头，浪费了将近两天时间。)
>
> 2、在使用的时候确保电源开关是开着的，电源在哪？看step1。