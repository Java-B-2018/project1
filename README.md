# Project 1 : 俄罗斯方块 设计文档

## 项目目标
本项目中，同学们需要使用 Java 编程语言，结合课堂知识、lab 内容，实现一个简单的、可以在命令行下玩的俄罗斯方块，并按要求编写一份开发文档，介绍你的实现方式、开发思路等内容

>
>关于项目有任何疑问，可以在 Issue 或微信群中提出：
>[http://www.github.com/Java-B-2018/project1/issues](http://www.github.com/Java-B-2018/project1/issues)




## 项目实现

### 一、游戏界面

基本游戏界面包含以下内容，在游戏开局或每轮操作后打印输出在控制台，可以根据附加功能或自己的喜好增加拓展内容

 + 一个10 * 20容量的方格空间，空间中包含**已经下落**的方块
 
 + 即将下落的方块形态
 
*需要用到的制表符已经写在[template.txt](https://github.com/Java-B-2018/project1/blob/master/template.txt)*

一个简单的案例如下所示：


![figure](https://raw.githubusercontent.com/Java-B-2018/project1/master/images/ui.png)


### 二、游戏操作

本次Project**不强制要求**方块自动下落，只需要能够改变方块朝向和下落位置即可。

>
>对方格空间的10列从左到右依次编号
>```{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}```
>



|指令名称|指令内容|
|:-:|:-|
|```w```|将当前方块顺时针旋转90度|
|```1```|将当前方块的最左端对齐到位置1并下落|
|```2```|将当前方块的最左端对齐到位置2并下落|
|...|...|
|```10```|将当前方块的最左端对齐到位置10并下落|
|```r```|重新开始游戏|
|```q```|退出游戏|



游戏每轮进行的步骤如下：

1. 打印游戏界面

2. 用户改变方块朝向，重新打印游戏界面

3. 用户选定下落位置

3. 方块落在指定位置，若恰好占满某些方格行，则消除这些行。再**随机生成**一个下一轮要下落的方块，重新打印游戏界面

4. 进入下一轮



### 三、游戏分数

游戏初始分数为0，用户每消除一行，加10分。在游戏结束时，统计方格中“孔洞”（即由方块或空间边界构成的空隙）的数量，每出现一个“孔洞”扣1分


### 四、结束判定

当方格空间中方块最高处达到空间顶端（即>=20)时，游戏结束。此时游戏打印出结束信息**并不再接受方块下落的指令**，输入```r```重新开始游戏。



>
>注：上述功能是基础功能点，全部完成即可得到代码部分的满分。若完成了附加功能则可以在未达到满分的情况下给予加分
>

### 五、附加功能

**1.小道具**

+ 消除道具，消除最底部一行方块（此次消除不计入游戏分数）

+ 随机道具，将当前要下落的方块替换为随机的另一个方块

每次（重新）开始游戏时，给予用户5个消除道具与10个随机道具



**2.排行榜**

每次游戏结束后将分数纳入排行榜，在游戏中输入```i```将这些分数按由高到低打印出来



**3.方块自动下落**

每隔1s自动刷新将当前方块下落一格



## 项目评分

### 基础功能点

|功能点描述|分数|
|:-|:-:|
|方格空间：格式正确、不发生错位|5|
|游戏指令：方块旋转方向无误，不发生错位|10|
|游戏指令：正确读取并执行方块的下落指令|5|
|游戏指令：重新开始、退出游戏等指令正确执行|5|
|游戏指令：格式错误的指令不会导致程序奔溃，并给出提示|5|
|游戏规则：方块不能超出空间边界|5|
|游戏规则：方块下落后不与其他方块重叠|5|
|游戏规则：自动消除填满的方格行|5|
|游戏结算：正确计算游戏分数|10|
|游戏结算：正确判断游戏结束的条件|5|
|游戏运行总体正常，符合相关描述，不会异常退出|5|
|总计|65|


### 综合评价部分

|描述|分数|
|:-|:-:|
|设计文档（包括但不限于程序结构设计与分析，主要函数的功能，简要描述如何使用你的程序，编程中遇到的问题和解决策略）|15|
|代码风格（包括但不限于命名规范，缩进与换行，代码可读性）|5|
|面试情况（能否清晰地解释程序结构，能否回答助教的问题等）|15|
|总分|35|


### 附加功能部分

|描述|分数|
|:-|:-:|
|小道具|10|
|排行榜|10|
|方块自动下落|20|
|上传代码、文档至Github|1|


## 项目提交与面试

### 提交截止时间
本次课程项目提交截止时间为 **2018 年 11 月 18 日 23:59**。

建议同学们在截止时间前一周就将项目基本完成，以防来不及完成，或者来不及修正突然发现的 bug 。

### 提交方式
请提交源代码、文档。源代码应以项目的形式提交。如有必要可以提交其他材料。

在截止时间之前将提交材料压缩并上传到：

```
ftp://10.142.141.33/classes/18/181  程序设计A（陈荣华）/WORK_UPLOAD/Project1
```

压缩包请重命名为：```学号_姓名.zip```

如果发现之前提交的文件有问题，可以重新上传压缩包。ftp不允许删除或者覆盖文件，需要上传一个新的压缩包，命名格式为：```学号_姓名_第n次上传.zip```

### 迟交惩罚
每迟交一天，最终得分扣除20%。

如：11月19日 00:01 AM 提交，扣除20%，11月21日 11:30 PM 提交，扣除60%。

>
>注：如果提交多次，以面试时选择的提交文件的提交时间为准。评分亦以此文件为准。
>

### 面试注意事项
本次课程项目面试时间为2018年11月22日 下午13:30 - 17:00，地点为机房，即Lab课组织面试。如有调整会提前通知

原则上面试时不允许现场Debug，请确保你的程序能正常运行

### 抄袭惩罚

**严禁任何形式的抄袭。**

助教将检查每个同学的代码、文档等材料，如有发现抄袭现象，将严肃处理。

抄袭同学零分处理。被抄袭同学将视情况作出惩罚。
