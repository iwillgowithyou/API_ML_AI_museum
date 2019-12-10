# API_ML_AI_museum

## 智能博物馆产品需求文档——以阿里巴巴API为基础的语音导览器移动端落地案例使用说明

### 1.目标用户群体需求分析（面向参观者、管理者需求）

产品目标：用户可以通过语音导览享受到在线语音交互。

- 参观者（游客）用户需求分析：

1. 用户对智能语音导览的识别准确度

通过线上调查和用户访谈等各种方式可知，用户对智能语音导览的准确度仍有一些建议，语音导览对场景的识别不够精确，需要在一定的范围内才能很好地识别场景。

2. 用户对智能语音导览的语音合成功能的需求

针对博物馆的文物众多、分类细致的特点，用户所期待的是可以通过语音输入指定的相关类型文物检索来自助导览，并可以获得相关内容的介绍，可以通过前期获取博物馆文物的数据统计和资料收集，然后使用阿里巴巴的API的接口来实现用户输入语音，合成文字后转给导览器进行识别并反馈信息。

3.用户对智能语音导览器的人机交互需求

随着语音助手的逐渐流行，人们更注重人机交互的功能实现，绝大部分的用户对于语音交互在导览器上实现十分期待，我们根据调查发现，各年龄层的用户在使用导览器时存在各种常见的问题，而这些常见的问题我们可以通过智能语音识别ASR、语音合成服务TTS、自然语音处理NLU三种技术的结合
来实现导览器“能听”"会说"“智能问答和意图识别”等功能于一体，使得导览器具备理解用户和反馈信息的能力。

- 管理者（工作人员）需求分析：

4. 管理者对于设备（导览器）的管理和调试功能的操作是否简便

综合用户的需求，工作人员在派发导览器的时候，需向用户简单的介绍设备，并在给设备前确认设备可正常使用。

5. 工作人员对于导览器的更新是否会操作

文物的收录和转移都需要人工对设备进行实时的更新，工作人员能否简易地使用导览器的后台来进行数据的修改，值得思考。

![输入图片说明](https://images.gitee.com/uploads/images/2019/1113/075313_e57bd2b6_1831543.png "微信图片_20191112211607.png")
 
### 2.产品功能使用场景分析

- 用户： 
（1）用户到达博物馆后，不清楚自己想找的展品位置在哪，这时可通过产品对展品进行搜索，产品在屏幕上显示出相对应的位置以及可以通过配套耳机进行语音导览使用户能迅速到达。
（2）当用户到达展品处后，对展品的简介无法理解时，可使用产品进行自定义语音导览

- 博物馆：

（1）当博物馆发生突发事件时，展馆可以第一时间就近调动相关的安保人员进行维护处理。因为语音导览器可以实时查看安保人员所处的位置。
（2）博物馆想要知道哪些展品比较受欢迎？展品摆放区域是否合理？则可以通过语音导览器在后台系统对用户进行实时监测所得出来的数据，比如每日游客数量、游览行为数据，来对展品分布和游客接待工作进行调整。

### 3.使用到的API&数据库技术分析(所需API)

- 语音识别服务ASR ：将语音转换成文字的能力快速集成，打造出“能听”的应用。
- 语音合成服务TTS ：将文字转换为声音的能力快速集成，打造出“会说”的应用。
- 自然语音处理NLU ：集语义解析、智能问答、意图识别等功能于一体，让应用具备理解能力。

### 4.产品功能详情

- 功能一——定位地理信息（区域地理信息）

用户能够获得在展馆内精准的定位信息，并提供导航功能，用户输入具体馆内展品名字或者类别就能指引用户到达该展品展区，避免了用户在小区域内使用常用的导航app效果甚微的情况。

- 功能二——文本内容转化为语音内容

用户在参观展品时，可以选择把展品历史介绍的文字内容转化为语音输出(OCR)，给予用户介绍展品的功能，同时解决了人流量大的情况下展品解说人员人手不足的问题。

### 5.落地产品预算

- 案例说明：

广东省博物馆总大小6.7万平方米

- 技术说明：

高德地图室内定位SDK是由高德室内地图部和阿里智能生活事业部联合出品的一套室内定位开发调用接口，供开发者在应用中加入室内定位相关的功能。通过基于WIFI、蓝牙以及PDR的室内定位技术，可实现平滑的1-8米的定位效果和精度。

![输入图片说明](https://images.gitee.com/uploads/images/2019/1113/075516_4d1e7967_1831543.png "1.png")
 

- 方案出台 

由于博物馆基本空间都较大，所以选择wifi方案是更为正确的选择

![输入图片说明](https://images.gitee.com/uploads/images/2019/1113/075642_3e43a058_1831543.png "2.png")
 
- 数据采集：

每半年都需进行一次（假设一次采集费用为x，则每年要花费2x的费用）。产品需要结合地理信息来回馈语言提示以替代以前博物馆的语音导览设备，需要对部分存在和其它独特信息相关联的地理信息进行该特殊信息的记录。这就要求需要建立一个相关的数据库，并还因随着不同展品展出、活动举办、时间的过去做出相应的改变，聘请专业人员去维护它。

### 综上所述，最终敲定的产品方案：

1. 场地无线网络布置

根据广东省博物馆的无线网络建设需求，为了构建 一个安全、可靠、高速、稳定、易于管理的无线网络，本设计方案采用AC+Fit AP的网络构架对博物馆薄盖目标区域进行无线覆盖。广东省博物馆的大小为6.7万平方米，采用设备为新支点ICG-S2600（后续简称为S2600），S2600的覆盖人群为1000人，单位覆盖500平方米，预计使用140个S2600对场馆进行无线网络全覆盖。每个S2600价格在900元，共计126,000元。其他方面采用了CMAX-3030-CPUSEV53天线、L4A-HPNMDM-3M射频跳线以及合路和射频传输线等产品，具体使用情况根据场馆内的人群数量决定，根据广东省博物馆以往日均人流量初步将覆盖人群的数量定在同时20000人，费用保持在100,000元上下浮动10,000元。无线网络的覆盖总成本控制在300,000元。

2. 使用的API接口成本

本产品采用的是由阿里云提供的API服务，采用的是预付费计算（每3000万次/54000元），根据阿里云的定价标准以及结合广东省博物馆的人流量，将成本控制在60,000元。

3.数据库运维人员成本

以广州市2019从业人员人数和从业人员工资的统计数据计算，人均7450元，聘请三人，每年的运维人员成本为250,000元。

### 综合以上成本，最后共计610,000元。


---END---

