# 2022年夏季《移动软件开发》实验报告



<center></center>

| 姓名和学号？         |                 |
| -------------------- | -------------------------------- |
| 本实验属于哪门课程？ | 中国海洋大学22夏《移动软件开发》 |
| 实验名称？           | 实验5：第一个安卓应用          |
| 博客地址？           | https://www.cnblogs.com/amonologue/p/16618930.html                          |
| Github仓库地址？     | https://github.com/Acolasiasss/EX5-of-Mobile-software-development                          |

（备注：将实验报告发布在博客、代码公开至 github 是 **加分项**，不是必须做的）



## **一、实验目标**

模仿微信“发现”页创建列表布局，学习使用Textview imageview、LinearLayout



## 二、实验步骤

列出实验的关键步骤、代码解析、截图。
1.逻辑梳理：
页面上主要包含5组列表，每组列表包含1-2个列表项。
 具体内容解释如下： 
 • 列表组1：“朋友圈”单行列表项；
 • 列表组2：“扫一扫”和“摇一摇”两行列表项；
 • 列表组3：“看一看”和“搜一搜”两行列表项；
 • 列表组4：“购物”和“游戏”两行列表项；
 • 列表组5：“小程序”单行列表项。
如图：

![图片1](https://user-images.githubusercontent.com/111416724/186304688-79eba56b-faec-414d-8f48-e00961bcfda9.png)

首先设计一个外部总垂直布局,包含所有的列表组
写五个LinearLayout来构建这五个列表组
每个列表组的单独构建
列表组之间的间隔样式搭建

2.代码实现
1）首先我们创建他们的父布局，对父布局进行设置背景色，设置父布局的垂直方向

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:background="#e5e5e5"
    android:orientation="vertical"
    android:layout_height="match_parent">
```

![2](https://user-images.githubusercontent.com/111416724/186304715-5e8a4533-382e-439d-b393-97c0210debba.png)

2）然后构建第一个列表组，设置宽高，设置背景色，设置垂直方向
```
<LinearLayout
        android:background="#fff"
        android:orientation="horizontal"
        android:layout_width="match_parent"
        android:layout_height="60dp">
```

3）在第一个列表组里面创建第一个图标，设置宽高、背景色、与左边的距离和居中
```
<ImageView
            android:layout_marginLeft="15dp"
            android:layout_gravity="center_vertical"
            android:background="@mipmap/icon_pengyou"
            android:layout_width="40dp"
            android:layout_height="40dp"/>
```

4）继续在第一个列表中创建汉字，设置汉字宽高、字体颜色、字体样式、字体大小、与左侧的距离和字体居中
```
<TextView
            android:layout_marginLeft="10dp"
            android:textStyle="bold"
            android:textColor="#333"
            android:textSize="18dp"
            android:gravity="center_vertical"
            android:layout_weight="1"
            android:text="朋友圈"
            android:layout_width="0dp"
            android:layout_height="match_parent"/>
```

5）最后创建列表组右边的箭头，设置宽和高、背景、水平居中和与右边的距离
```
<ImageView
            android:layout_marginRight="15dp"
            android:layout_gravity="center_vertical"
            android:background="@mipmap/right"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>
```

![3](https://user-images.githubusercontent.com/111416724/186304747-0ecdb6e4-1975-4462-89da-8a07af0b6870.png)

6）重复以上步骤添加新的列表组，如遇中间间隔，则添加一个与背景色相同但是高略小的列表组

![4](https://user-images.githubusercontent.com/111416724/186304757-0d429ef7-2466-4639-8ddd-d8f5069d5deb.png)

## 三、程序运行结果

列出程序的最终运行结果及截图。

![5](https://user-images.githubusercontent.com/111416724/186304774-6cfac39a-277e-49de-a7cc-853a0e795992.jpg)

## 四、问题总结与体会

描述实验过程中所遇到的问题，以及是如何解决的。有哪些收获和体会，对于课程的安排有哪些建议。

本次实验较为简单，就是仿照格式写代码。个人觉得唯一难得的地方就是列表中间间隔的地方。可以设置与上一个列表组的距离，我选择直接插入一个与背景色相同的空白子列表，但是高度略小，就达到了间隔的效果。
