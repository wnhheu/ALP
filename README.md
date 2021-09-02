# 计算机组装--ALP

<!--more-->

啊，我之前装了一台计算机，在组装的过程中遇到了一些困难，而对于初学者而言，直接去看一张配置单可能实在是有些困难，所以我准备结合自身的学习经历来写一篇技术文档，这也算是一个很初步的对于这种类型的文章的尝试

是的，更确切的说，这是一次尝试，如果成功自然好，如果不成功可能要总结一下失败的教训

这样一篇文章在我写作之初便体会到自身知识的局限性，所以计划是通过迭代来提高文章的水平

目前是1.0版

---

一台计算机需要有什么？

- CPU
- 主板
- 内存
- 显卡
- 硬盘
- 散热器
- 电源
- 机箱

这些构成了一台电脑主机的所有要素（此处不包含外设，像鼠标、键盘、显示屏之类的）

好了，然后一个问题，上面列出来的8条分别是什么？

所以在装电脑之前我们需要先学习计算机的基本概念

## 计算机的硬件是怎么工作的

### CPU

CPU（中央处理器）是一个具有特定功能的芯片，里面含有指令集

ok，一个新的问题，什么是指令集

> 指令集就是CPU能够理解的操作的集合
>
> 就像你手上的计算器，假设上面只都有 + - * /
>
> 对于这四种基本的运算，计算器都能够直接地进行计算，它知道这些运算的含义，而如果你想要进行乘方运算如2 ^ 5，计算器不认识‘ ^ '，那就需要把 ^ 转换成乘法的形式才能被计算器所理解
>
> 指令集就是像 + - * / 这样基本的操作类型的集合，只不过 + - * / 这些操作是对计算器的。对于CPU来说，像RISC-V指令集中有JAR、BEQ、ADDI等指令，这些指令都可以被CPU理解并执行，而一些更复杂的指令就需要将已有的指令进行组合来得到，就像将乘方运算用乘法来实现一样

因为这里的目标是关于计算机装机，所以不会涉及太多偏专业的内容

说回来，CPU主要分为两个部分：算术逻辑单元和控制单元，CPU的工作主要在于管理和运算

管理就是合理分配每一个任务的算力，运算就是进行数据的处理，计算机嘛，核心当然是计算，但是也需要高效率地进行工作的分配，一味地埋头计算太笨拙了，所以CPU里面也会有分工

就像小学时候的烧水问题，如何趁着水烧开之前的时间多做一点工作，CPU也是这样的

<img src="C:\Users\wnhheu\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04onWindows_79rhkp1fndgsc\LocalState\rootfs\home\wnhheu\computer_assemble\ALP\image\cpu.jpg" alt="cpu" style="zoom: 25%;" />

### 内存

那么CPU计算所需要的数据是从哪里来的呢？当然不是我告诉它，“算一下 1 + 1 = ？“

CPU计算所需要的数据都是从内存中来的，内存中的数据则是通过输入设备传输进来的，像我说“算一下 1 + 1 = ？“可能可以被语音识别出来，然后存到内存当中，当然更多情况下是用鼠标、键盘等等输入设备

然后CPU处理完的数据也要先写会内存，然后数据才会被传输到输出单元

就像人的大脑一样

> 你看到了一件事情，你看到的内容通过视神经传到大脑，但是大脑在分析之前这写信息先被存储在一块区域，然后大脑从区域中调集信息进行分析，分析好了之后把结果传回这块区域，然后这块区域再传信息给你的嘴去说话或者你的手去行动，内存就是这样的一块区域

![内存](https://github.com/wnhheu/ALP/tree/master/image/ram.jpg?raw=true)

### 显卡

我们的电脑一般都有图形界面，图形界面就是用显卡来生成的，如果没有显卡那么你的电脑就无法点亮了，一般像服务器就不需要显卡，因为没有图形显示的需求，大多都是远程操作的

我们的电脑一般情况下都需要有一个显示屏，显示屏是由一个个像素点组成的，而存放每一个像素点的颜色会占用内存，因此显卡上会有集成内存称为显存

早期的电脑是由CPU来完成3D的运算，而随着3D游戏、3D动画的流行，对运算的要求越来越高，所以后来在显卡上面嵌入一个3D加速的芯片，就是所谓的GPU

<img src="C:\Users\wnhheu\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04onWindows_79rhkp1fndgsc\LocalState\rootfs\home\wnhheu\computer_assemble\ALP\image\gpu.jpg" alt="ram" style="zoom:25%;" />

### 硬盘

硬盘是用来记录和读取数据的，就像人脑的记忆一样

有人会问了，既然都是用来记录和读取数据的，那么硬盘和内存有什么区别？

> 内存和硬盘内部的结构不同
>
> 内存中的数据只有在通电时才能记录与使用，断电之后数据就消失了
>
> 硬盘中的数据则会一直保留，不管有没有通电

既然内存感觉这么不可靠，为什么不都用硬盘呢？

> 因为内存的速度远远快于硬盘的速度
>
> 内存的理论速度可以达到几十GB/s
>
> 而硬盘的速度可能都不足1GB/s

<img src="C:\Users\wnhheu\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04onWindows_79rhkp1fndgsc\LocalState\rootfs\home\wnhheu\computer_assemble\ALP\image\ssd.png" alt="ram" style="zoom: 50%;" />

### 主板

介绍了这么多的硬件，那么这些硬件之间是如何沟通的呢？

这时候就涉及到主板了

像人的神经系统串联起各个部位一样，主板也起着连接各个元件的作用

主板上有芯片组、数据线、各种各样的接口，主板通过这些来连接不同的元件并且和外部环境交流

<img src="C:\Users\wnhheu\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04onWindows_79rhkp1fndgsc\LocalState\rootfs\home\wnhheu\computer_assemble\ALP\image\main_board.jpg" alt="差不多长这样" style="zoom: 50%;" />

### 电源

电源很简单，就是用来给主板供电的，没错，是给主板供电的

电源给主板供电之后主板再去给各个硬件进行供电

<img src="C:\Users\wnhheu\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu20.04onWindows_79rhkp1fndgsc\LocalState\rootfs\home\wnhheu\computer_assemble\ALP\image\power.png" alt="ram" style="zoom:50%;" />

### 机箱

机箱分为ATX，M-ATX，ITX三种，对应从大到小

ITX是迷你机箱，对于散热、元件尺寸有比较大的限制

M-ATX是中等大小的机箱（在选购时需要稍微注意一下尺寸）

而ATX是大机箱（没什么不好的，除了占地方，给人的感觉就是机箱大的不行）

主板也有这三种情况，需要注意的是大机箱可以装小主板，小主板不可以装大机箱（这很正常）

(机箱的样子应该大家都见过，就不放图了

---

到这里，我们差不多对一个计算机的最基本的组成有一个了解了，至少你知道装一台电脑需要哪些硬件，这些硬件分别有什么样的用途



















