# python_for_data_science

## 安装
在本地电脑上下载 Anaconda，以便在 Jupyter Notebook 上写 Python

下载 Anaconda：[链接](https://www.anaconda.com/distribution/)

什么是 Anaconda：[知乎](https://zhuanlan.zhihu.com/p/32925500)

什么是 Jupyter Notebook:[知乎](https://zhuanlan.zhihu.com/p/32320214)

## 使用
#### 常用模块
以下是在数据分析中常伴你的模块，不用害怕，记住它们的名字就好

* 数据处理：[pandas](https://pandas.pydata.org/docs/reference/index.html) numpy
* 数据可视化：matplotlib seaborn
* 机器学习：[scikit-learn](https://scikit-learn.org/stable/tutorial/index.html)

#### 简单句法
##### import

在开始处理数据前先载入需要用到的模块

e.g. 

import pandas as pd （按 shfit + enter 运行) 

意为「载入 pandas，以下简称 pd」

简称一般都是约定俗成的：
  pandas - pd
  
  numpy - np
  
  seaborn - sns
  ……

##### 函数
模块里充满了函数，函数是封装好的命令，事实上，这些函数跟《哈利波特》里的「除你武器」、「统统石化」等咒语没有什么差别

假设我们已经通过 import numpy as np 载入了 numpy 模块
并且通过 v = np.arange(10) 创建了一个向量
现在你可以使用不同的「咒语」来处理这个向量：
  v.sum() - 求和
  v.max() - 求最大值
  v.mean() - 求均值
  v.std() - 求标准差
  ……

##### 点
Python 使用点来连接对象和函数，点前面是对象，点后面是函数，执行顺序为从左往右，跟我们的阅读顺序一致

v = np.arange(10) # 创建对象
v.sum() # 执行求和
等同于
np.arange(10).sum() # 创造对象并执行求和

对令人眼花缭乱的操作：
df.drop_duplicates().groupby('a')['b'].sum().set_index('c')

可以分行写
df_unique = df.drop_duplicates()
df_b_sum = df_unique.groupby('a')['b'].sum()
df_c_index = df_b_sum.set_index('c')

事实上，你可以截取任一的从最左端开始的部分作为对象，使之后的语句变得简洁：
ob = df.drop_duplicates().groupby('a')['b'].sum() # 截取从最左端开始的一部分作为对象
ob.set_index('c') # 后续的操作变得简洁

## 学习
#### 搜索引擎
你问的问题搜索引擎都有答案

首选 google，如果不能用 google，就用 bing
baidu 搜索的内容质量较差，不建议使用

在搜索引擎搜索「pandas tutorial」、「sklearn tutorial」、「pandas 教程」、「sklearn 教程」之类的关键字
检索到的教程都大同小异，选择排在前面的开始学习即可

同样的，在遇到问题时，直接在搜索引擎询问「python 如何将时间戳转为年月日格式」、「python dataframe 按列求和」等等

再附上几个获取知识的站点，大多是大家耳熟能详的：
  google
  github
  stackoverflow
  youtube
  B 站
  知乎
  加入 tdu 社群抱团学习
  
#### 官方文档
在使用函数前建议仔细地阅读官方文档，因为官方文档详尽地说明了函数的功能、参数的选项、默认的模式、返回的结果和相关的例子，基本上能解决你在使用函数时99%的问题

比如
[pandas.DataFrame.drop_duplicates](
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop_duplicates.html)

简单列几个教程（相信我，你自己也能直接搜到的）：
[10 minutes to pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html)
[Pandas Exercises](https://github.com/guipsamora/pandas_exercises)
[Virgilio : Your new Mentor for Data Science E-Learning](https://github.com/virgili0/Virgilio/blob/master/zh-CN/README.md)

## 规范
#### 命名规范
命名的两种方式：下划线和驼峰式

* 下划线：单词均小写，单词间以下划线分隔
* 驼峰式：第二个单词开始首字母大写，其余小写，望之如驼峰

假设我们要对一个经历了一系列操作的数据框（类似于一张表）命名
因为它是个数据框（dataframe），我们一般先称它为 df
因为它经过了一系列操作，比如先复制再求和，于是我们可以命名为
* 下划线：df_copy_sum
* 驼峰式：dfCopySum

#### 写好注释
人的记忆有时候也只有7秒，写好注释，利人利已

一来可以避免回顾时忘记
二来增强了可读性，便于共享

注释一般在代码前或代码右
比如
```python
# 复制数据框
df_copy = df.copy()
```
或者
```python
df_copy = df.copy() # 复制数据框
```

## 避雷
#### 关于是否改变了原对象
在 jupyter 里写代码的新手常常搞不清有没有对原对象修改成功，因为它会即时地出结果

比如对数据框去重

df.drop_duplicates()

新手经常会以为这就去重完成了，实际上 jupyter 仅仅是展示了去重之后的结果而已，你的 df 并没有发生变化

如果真的要使 df 发生变化，要进行赋值

df = df.drop_duplicates()

或者指定一个新对象

df_clean = df.drop_duplicates()

新的 df 或者 df_clean 才是你需要的去重后的数据框

#### 关于路径
初学者经常在文件读取、保存时对路径感到困惑，因此简单说一下路径

假设你正在 Desktop （桌面）位置，桌面上有个名为 beauty（漂亮姐姐）的文件夹，那么这个文件夹的路径可表示为：

* 绝对路径 /Users/sherlock/Desktop/beauty （使用 macos 的同学，如果不知道一个文件的路径，可以直接将其拖到 terminal 中，即可看到路径）
* 相对路径 ./beauty （. 表示当前位置，当前你正在桌面）

在 Jupyter Notebook 中可以用命令行查看当前工作路径
pwd 
意为 present work directory

假设你现在在桌面的 beauty 文件夹，要查看文件夹里2019年漂亮姐姐的清单

import pandas as pd # 载入 pandas 模块，以下简称 pd
beauty_li_2019 = pd.read_excel('./beauty_list_2019.xlsx') # 使用 pandas 模块的 read_excel 函数读取清单

经过一番处理，你生成了2020年漂亮姐姐的清单，并将其保存到文件夹里
beauty_li_2020.to_excel('./beauty_list_2020.xlsx')

</end>
