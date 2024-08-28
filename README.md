[合集 \- 环境配置(2\)](https://github.com)1\.最全！嵌入式STM32单片机开发环境配置教学Win/Mac！！！08\-28[2\.最简最速！C\+\+版OpenCV安装配置教程Win/Mac！！！08\-28](https://github.com/SkyXZ/p/18385688)收起
# 嵌入式STM32单片机开发环境配置教学Win/Mac


    · 本教程支持Windows和Mac


    · Windows可选的开发软件为Keil、Clion、STM32CubeMX，可自由选择开发方式


    · Mac的开发环境为(Clion\+OpenOCD\+STM32CubeMX)，仅支持HAL库


# Windows配置教程


        在Windows上面开发Stm32有多种工具组合，可以单纯使用Keil进行库函数、Hal库以及寄存器的开发，也可以通过Stm32CubeMX配合Keil开发STM32的Hal库，也可以使用CLion\+OpenOCD\+STM32CubeMX的组合来更现代化的开发Hal库，每种方式都有其优点，读者可以任意选择一个更加适合自己的开发方式，笔者使用的是第三种也就是CLion\+OpenOCD\+STM32CubeMX的组合，本章节中除了会讲述软件和环境的安装配置还会对每种开发方式中相关软件工程文件的使用配置进行基本的概述。


## Keil5配置教程


      需要的安装包下载地址：Keil5配置包.zip
​        链接：[https://pan.baidu.com/s/1joWgDoV7qujdAT3Jack0\_w?pwd\=nbvw](https://github.com)
​        提取码：nbvw


### 一、软件介绍


        Microcontroller Development Kit（简称 MDK），是 ARM 旗下公司 Keil 为 ARM 系列单片机 开发的一款便捷的开发工具，支持市面上绝大部分的单片机系列。


### 二、环境配置注意事项！！！


    1\. 安装的所有路径都不用能有中文出现！！


    2\. 在配置环境前请将电脑上的所有！注意是所有！的杀毒软件全部关掉包括Windows自带的安全中心也全部关掉！！！


        Windows安全中心关闭方法：


           · 点击"设置"\>"隐私与安全性"\>"Windows安全中心"\>"打开Windows安全中心"


           · 依次点击"病毒和威胁防护"、"防火墙和网络保护"，关闭里面的保护内容即可


    3\. 下载解压后文件夹里应该有以下几个文件及文件夹，请先行检查是否存在.


             · MDK531\.exe


             · Keil.STM32F4xx\_DFP.2\.13\.0\.pack


             · keil.STM32F1xx\_DFP.2\.2\.0\.pack


             · ARM.CMSIS.5\.7\.0\.pack


             · keygen\_new2032\.exe


             · 串口调试助手（文件夹）


             · ST\-LINK驱动（文件夹）


             · CH340驱动(USB串口驱动)\_XP\_WIN7共用 （文件夹）


              如下图所示：


[![文件夹图片](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156561-1635556383.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156561-1635556383.png)


    4\. 安装配置文件无病毒如果被安全软件误删，请动动小手关闭安全软件并从安全软件中恢复被“和谐”的文件。


        在下图所示位置：选中发现的威胁将被隔离的文件选择"允许在设备上"然后点击"执行操作"即可 [![2](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156039-202287492.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156039-202287492.png)


### 三、安装步骤


### 1\.鼠标右键点击 "MDK531\.exe"，并选择以管理员身份启动进行安装


        点击Next即可开始安装


[![安装keil](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156867-852724519.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156867-852724519.png)


### 2\.任意位置进行安装


        任意位置均可安装，但建议将安装位置选择D盘防止后期C盘爆满(C盘清洁设置具体操作方法可以查看我的这篇Blogs：[Win11减少C盘占用及清爽系统配置教程](https://github.com))


[![安装位置](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156962-1171701946.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156962-1171701946.png)


        安装过程中会要求填写姓名地址等联系方式，这部分无论填什么都不会影响后续的使用可以随意填写


[![安装填信息](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156685-775306677.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156685-775306677.png)


        填写完信息后耐心等待安装完成即可过程中可能会出现CMD窗口，完成安装后点击Finish便完成了软件本体的安装


[![安装完成](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156599-1244889402.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156599-1244889402.png)


        点击Finish后会出现一个Keil的界面，在这个界面里选择左上角Packs，把Check For Updates on launch的勾去掉后 关闭窗口，忽略提示即可。


[![关闭更新](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156180-1698144779.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156180-1698144779.png)


### 3\.安装芯片驱动包


        安装完软件之后我们还需要安装STM32的软件驱动包，我们提供在学习和项目过程常用的F1和F4芯片的驱动包供大家使用，依次点击最开始文件夹中的"Keil.STM32F4xx\_DFP.2\.13\.0\.pack"和"keil.STM32F1xx\_DFP.2\.2\.0\.pack"安装即可，步骤可参考软件本体的安装步骤。


### 4\.破解方法


        安装之后我们还不能正常使用本软件还需对其进行破解，首先在桌面或者在开始菜单中找到安装完成的Keil5软件("keil uVision5")，右键以管理员身份打开，选择左上角"File"下的"License Management"并复制弹出窗口里面的CID.


[![破解](https://images.cnblogs.com/cnblogs_com/blogs/829228/galleries/2416959/o_240825234614_%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-08-25%20200442.png)](https://images.cnblogs.com/cnblogs_com/blogs/829228/galleries/2416959/o_240825234614_%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202024-08-25%20200442.png)


        然后打开文件夹中的破解软件"keygen\_new2032\.exe"(PS:如果没有在解压之前关闭安全中心，这个破解软件可能会被安全中心查杀)将刚刚复制的内容粘贴到 CID 框，Target 选择ARM，下面的下拉框选择Professional，然后点击Generate后会得到一个软件的激活码


[![破解软件1](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156274-1309386951.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156274-1309386951.png)


        然后将获得的激活码复制填入New License ID Code中，点击Add LIC，中间表格区域出现激活内容即算激活成功


[![破解2](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156980-290124188.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156980-290124188.png)


至此，keil的安装完美结束啦！！！！！！！！！！！！！！！！


## STM32CubeMX安装配置教程


### 一、软件介绍


        STM32CubeMX 是 ST 意法半导体近几年来大力推荐的STM32 芯片图形化配置工具，目的就是为了方便开发者，允许用户使用图形化向导生成C初始化代码，可以大大减轻开发工作，时间和费用，提高开发效率。STM32CubeMX几乎覆盖了STM32 全系列芯片。在CubeMX 上，通过傻瓜化的操作便能实现相关配置，从MCU/MPU选型，引脚配置，系统时钟以及外设时钟设置，到外设参数配置，中间件参数配置，它给STM32开发者们提供了一种简单，方便，并且直观的方式来完成这些工作，所有的配置完成后它还可以根据所选的IDE生成对应的工程和初始化C代码。除此以外，STM32CubeMX还提供了功耗计算工具，可作为产品设计中功耗评估的参考。最终能够生成C语言代码，支持多种工具链，比如 MDK、IAR For ARM、TrueStudio等 省去了我们配置各种外设的时间，大大的节省了时间，并且随着ST停止了标准库的更新，ST官方大力推荐CubeMX与HAL库的使用，虽然现在还是 标准库的主场，但是CubeMX的使用率在逐年提高，所以学习下CubeMX的基本使用也是我们需要掌握的技能之一。


        CubeMX/HAL 库使用学习链接：[http://t.csdnimg.cn/UH7Ah](https://github.com)


        Java 官网：[https://www.java.com/en/download/manual.jsp](https://github.com)


        CubeMX安装官网：[https://www.stmcu.com.cn/Designresource/detail/software/711298](https://github.com)


### 二、安装软件


    1\. 进入上方给出的STM32CubeMX官网后点击下载（在官网下载需要注册下ST官网账号,目前最新为6\.10\.0版本，软件本身免费，使用Clion 作为开发工具的不要下载最新版，建议下载6\.4\.0\.）拿到安装包后右键选择以管理员权限运行本安装包，并选择"Install For All Users"


[![stm](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072157005-383850888.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072157005-383850888.png)


    2\. 随后在出现的界面一直点击Next即可


​ [![stm2](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156060-1953837175.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156060-1953837175.png)


    3\. 选择安装路径的界面建议将软件安装至D盘，后期软件包大小有些许大安装在D盘可以防止C盘爆满影响系统运行速度


[![stm3](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156231-1936873932.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156231-1936873932.png)


    4\. 之后一直选择Next并选择默认配置即可完成安装


[![stm4](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156254-78481909.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156254-78481909.png):[wgetCloud机场](https://tabijibiyori.org)


### 三、安装芯片驱动包


        打开安装好的 STM32CubeMX 软件 点上面的Help\-\>Manageembeddedsoftware packages 会跳出来一个选择型号界面勾选上你要安装的HAL库，点击“InstallNow” 直到安装成功即可。


[![stm5](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156941-387294162.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156941-387294162.png)


[![s](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072157008-1637594571.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072157008-1637594571.png)


至此，STM32CubeMX的安装完美结束啦！！！！！！！！！！！！！！！！


## OpenOCD安装配置方法


        OpenOCD安装地址：[Download OpenOCD for Windows (gnutoolchains.com)](https://github.com)


### 一、工具介绍


        OpenOCD(Open On\-Chip Debugger)是一款开源的开放式片上调试软件，需要在调 试适配器(如:JTAG、SWD等)的配合下可以对片上系统进行相应调试，以及在嵌入式设备 上测试系统内程序或边界接扫描测试。


### 二、安装方法


    1\. 在上述链接里选择下载OpenOCD并解压


[![ocd](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156515-122196002.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156515-122196002.png)


    2\. 将解压后文件的bin目录添加到环境变量中后即可使用


        首先打开系统设置，在搜索框搜索"环境"选择编辑系统环境变量，在弹出的窗口选择"环境变量"一项
[![ocd2](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156061-2008751149.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156061-2008751149.png)


        接着在下方"系统变量"窗格双击"Path"即可进入系统环境变量的编辑窗口


[![ocd3](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156416-743896988.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156416-743896988.png)
​


        最后在弹出窗口点击"浏览"后选择OpenOCD的Bin文件夹点击确认即可


[![ocd4](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156254-1266115092.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156254-1266115092.png)


至此，OpenOCD的安装完美结束啦！！！！！！！！！！！！！！！！


## Clion的安装与嵌入式开发的配置


        Clion安装地址：[CLion: A Cross\-Platform IDE for C and C\+\+ by JetBrains](https://github.com)


### 一、软件介绍


        Clion 是 Jetson 推出的一个C和C\+\+集成开发环境，其可以支持嵌入式开发，虽然这个软件是收费的但如果你是学生或者教育工作者的话均可以申请免费使用但是速度通过速度较慢大致需要1Days的样子，还有一种方式在此不做过多的赘叙（为何你不看看万能的Tao宝呢？？？）


        同时由于Clion自带MinGW，所以其实配置Clion的过程中不需要像其他网上的教程所说重新下载一遍MinGW！！！


### 二、安装教程


        Clion的安装较为简单，在此就不详细展开唯一要注意的便是在安装的界面中记得勾选"添加Bin文件到PATH"免得后期自己添加过于麻烦，只不过安装完成之后需要重启一下更新系统环境变量


[![clion](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156549-1406933057.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156549-1406933057.png)


### 三、嵌入式开发配置


        安装完Clion、STM32CubeMX以及OpenOCD后便可以开始配置Clion的嵌入式开发环境，由于新版的Clion无法在启动界面打开软件设置（也有可能是我没找到入口？），读者可以先随便新建一个项目并打开，在打开的项目主页面点击"文件"\-\>"构建、执行、部署"\-\>"嵌入式开发"，打开之后需要选择读者STM32CubeMX以及OpenOCD对应的bin文件的安装路径，一般来说添加了STM32CubeMX以及OpenOCD的环境变量后Clion会自动更新其路径，但如果没有自动更新出现路径也可以点击后面的三个点来手动选择软件的路径


[![s](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072155844-815895330.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072155844-815895330.png)


        在选择好软件的路径之后可以点击后面的测试按钮来测试STM32CubeMX以及OpenOCD在Clion上面是否成功配置，如果点击了测试后弹出的提示信息是绿色的即代表配置正确


[![w](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156884-1170460322.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156884-1170460322.png)


至此，Clion的嵌入式配置安装完美结束啦！！！！！！！！！！！！！！！！


# Mac配置教程


        由于Mac系统的特殊性，Mac暂时还无法安装Keil，于是只能选择优雅的使用CLion\+OpenOCD\+STM32CubeMX这一套跨平台开源的的开发工具，这套工具以现代化的IDE工具Clion为核心，可以用以多个AI插件来复制开发如Github的Copliot，笔者的前开发工具便为这个，用起来那是朗朗上手！


        由于Mac上的Stm32CubeMX以及Clion的配置方法与Win上的配置方法几乎一样，相关内容可以参考Windows的安装流程，本节仅介绍Mac上HomeBrew及OpenOCD的安装方法.


        这里给出Mac上相关软件和工具的下载路径：


                Clion：[https://www.jetbrains.com/clion/](https://github.com)


                STM32CubeMX：[https://www.st.com/en/development\-tools/stm32cubemx.html\#get\-software](https://github.com)


## HomeBrew安装


### 一、工具介绍


        Homebrew 是一个流行的包管理器，专为 MacOS（以及 Linux）操作系统设计。它允许用户通过命令行界面轻松安装、更新和管理软件包。Homebrew 的主要优势在于其易用性、灵活性和社区支持。用户可以通过简单的命令来安装所需的软件，而无需复杂的配置过程。 Homebrew 的工作原理是通过一个中央仓库，即 Homebrew Formulae，来管理软件包的配方（Formulae）。每个配方都是一个 Ruby 脚本，定义了如何下载、配置、编译和安装软件。Homebrew 社区不断更新这些配方，以确保软件包的最新性和兼容性。


[![home](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156350-2009420983.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156350-2009420983.png)


### 二、安装方法


  打开Mac的终端命令行


    1\. 检查系统中是否有HomeBrew



```
brew -v  #有输出的话便代表电脑中存在HomeBrew

```

    2\. 如果有HomeBrew，先进行卸载



```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/uninstall.sh)"

```

  类似于ROS，HomeBrew也有大神做了一个一键自动化安装脚本(但可能需要挂代理进行ke xue shang wang)



```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" #根据提示一步步安装即可

```

  出现一下图片中的内容即代表HomeBrew安装成功


[![ho](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156726-1320096778.png)](https://img2024.cnblogs.com/blog/3505969/202408/3505969-20240826072156726-1320096778.png)


至此，Mac上的HomeBrew安装完美结束啦！！！！！！！！！！！！！！！！


## OpenOCD安装


        Mac由于是Unix的内核，因此在HomeBrew这种包管理工具的加持之下，Mac配置环境下载工具比Win会轻松很多，就如OpenOCD来说Mac上只需一行代码便可以安装配置完成



```
	brew install open-ocd  #下载OpenOCD

```

## ARM toolchain安装


        由于Mac是Arm系统于是需要安装Arm的开发工具链（类似与Win中的MinGW），同样也是两行命令就能很快解决进行下载



```
brew tap ArmMbed/homebrew-formulae
brew install arm-none-eabi-gcc

```

  为了测试是否安装成功，可以在终端中输入一下命令进行检查,有输出便代表安装成功



```
arm-none-eabi-gcc -v 

```

接下来就只剩修改Clion中的STM32CubeMX以及OpenOCD路径了，配置方式和Win一样便不在赘叙


# 安装过程中的问题解决方法：


        在安装过程中遇到的任何问题及解决办法或者文档中出现的错误欢迎大家联系我进行添加和删改！


 \_\_EOF\_\_

   ![](https://github.com/SkyXZ)SkyXZ  - **本文链接：** [https://github.com/SkyXZ/p/18384473](https://github.com)
 - **关于博主：** 评论和私信会在第一时间回复。或者[直接私信](https://github.com)我。
 - **版权声明：** 本博客所有文章除特别声明外，均采用 [BY\-NC\-SA](https://github.com "BY-NC-SA") 许可协议。转载请注明出处！
 - **声援博主：** 如果您觉得文章对您有帮助，可以点击文章右下角**【[推荐](javascript:void(0);)】**一下。
     
