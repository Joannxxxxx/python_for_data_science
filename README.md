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

事实上，你可以截取任一从最左端开始的部分作为对象，使之后的语句变得简洁：
ob_1 = df.drop_duplicates().groupby('a')['b'].sum() # 
ob_1.set_index('c')




