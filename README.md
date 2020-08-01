# 2020年新工科联盟-Xilinx暑期学校（Summer School）项目

## 基于HLS卷积神经网络的加速

### 项目概要

本项目是在Xilinx暑期学校的指导下完成的项目，项目的主要内容如下：

本设计利用OV5640采集图像，将采集到的图像传入ZYNQ,利用神经网络对图像进行特征提取、图像识别计算、分类操作，最终得到图像的分类信息。在此分类过程中，我们首先用纯SDK来实现卷积操作，并且成功验证了实验的正确性；然后将SDK代码中的卷积部分提取出来使用HLS加速，提高分类速度。具体功能如下：

<1>使用caffe进行网络的训练，数据集是CIFAR-10

<2>通过摄像头采集图像经由VDMA传入ZYNQ

<3>利用构建的神经网络进行图像识别分类

<4>对卷积计算特征提取过程进行HLS加速

系统框图如图所示：

![](C:\Users\Administrator\Desktop\GitHub\images\项目框图.jpg)         

图1 系统框图

从上图可以看出，PL首先将相机采集到的数据进行搬移到PS侧的DDR3上面，首先将采集到的图片（720P）resize到32*32,生成网络可以处理的图片。将处理后的图片数据加载到FPGA（PL端）进行神经网络计算，通过加速计算，在较短的时间得到计算后返回的结果，对FPGA（PL端）计算返回的结果在ARM中进行处理分类，通过HDMI线输出分类信息在显示屏进行显示。与此同时，对下一张图片resize,……,重复以上步骤实现对采集到的图片的分类过程。

### 使用的工具版本

本次实验使用的工具版本如下：

VIVADO 2019.1

HLS 2019.1

Modelsim 10.7

### 小组成员列表

组长：张宁宁  20BS168A  苏州大学  

组员：张硕   20BO127A  桂林电子科技大学  

​			杜玉玉  20BS173A  西北工业大学  

### 板卡型号与外设列表  

板卡型号：米联客MZ7015FA

外设列表：OV5640摄像头

​					显示屏

​					手机

### 仓库目录介绍

README.md：2020年新⼯科联盟-Xilinx暑期学校（Summer School）项⽬的介绍文件，应该包含项⽬概要，使⽤的⼯具版本，⼩组成员列表（可选），板卡型号与外设列表，仓库⽬录介绍，作品照片等。
images：存放README.md文件中引⽤的照片  

Sourcecode ：主要包括三个工程的文件夹，每个文件夹里面有相应的SDK文件，工程文件，具体的请查看该目录下的README.md    

ExecutableFiles:本⽬录存放可直接下载到板卡使⽤的FPGA 比特流文件，与SDK的elf文件

### 作品图片

我们将项目进行下班测试的测试结果如下：

![](C:\Users\Administrator\Desktop\GitHub\images\图片1.jpg)



![](C:\Users\Administrator\Desktop\GitHub\images\图片2.jpg)

![](C:\Users\Administrator\Desktop\GitHub\images\图片3.jpg)

![](C:\Users\Administrator\Desktop\GitHub\images\图片4.jpg)

![](C:\Users\Administrator\Desktop\GitHub\images\图片5.jpg)

![](C:\Users\Administrator\Desktop\GitHub\images\图片6.jpg)



































