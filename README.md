# tips_Caffe_installation

最近在做一个从视频中抓取文字的应用，需要使用caffe在此记录编译安装中遇到的问题及解决方法，很多内容都是参考了网友的经验。

## 系统信息：
- 操作系统：ubuntu 16.04
- Python: Anaconda3 + Python 3.6.4
- OpenCv: 3.4
- CUDA:8.0
- Cudnn: the respective version

## 概述：
安装caffe的困难主要是它依赖的包比较多，而且版本也较杂乱，比如OPENCV, 3.0以上的版本和2.0的版本有较大差异，Python 2 和 Python 3也有很大的不同，还有CUDA和Cudnn各个版本之间有这对应关系，支持不同的显卡。这些情况带来的最大影响就是各个版本之间函数库的路径，名称之间存在的差异，也正是这个原因，使得安装Caffe会比较耗时。

不过只要搞清楚了程序编译的基本概念，成功安装Caffe只是时间问题。caffe的编译是cmake,从github上clone的源代码中已经含有有一个写好的 makefile 和 makefile.confing.example，我们要做的只是依照自己电脑的具体情况，调整makefile.confing，为相应的library指明路径罢了。当然要做到这些也并不容易，下面就把本人在安装过程中遇到的问题，已经解决的方式做一个汇总。
