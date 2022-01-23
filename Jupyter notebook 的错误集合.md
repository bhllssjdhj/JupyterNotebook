## No module named 'numpy'
### 1.为什么出现这种情况？
**未安装numpy 或 安装多个numpy（见2）**
通常，许多不同的IDE，如Jupyter Notebook，Spyder，Anaconda或PyCharm倾向于安装自己的python虚拟环境，以保持整洁并与全局python分开。因此我们只需要在我们使用的虚拟环境中（例如conda）`conda pip install numpy`即可。
又有一种情况是我们已经安装了numpy模块，但是jupyter仍然报错，可能是我们在不同环境下安装了多个numpy，需要删除所有版本后重新下载。
### 2.如何删除旧版本的numpy
通过`pip uninstall numpy`删除旧版numpy **需删除多次**​
![pip uninstall1.png](https://cdn.nlark.com/yuque/0/2022/png/25978259/1642867119751-5b0dc856-c1da-472c-bdd2-8a9670dd6d49.png#clientId=u10d16641-0449-4&crop=0&crop=0&crop=1&crop=0.9469&from=ui&height=562&id=ufd42f171&margin=%5Bobject%20Object%5D&name=pip%20uninstall1.png&originHeight=562&originWidth=891&originalType=binary&ratio=1&rotation=0&showTitle=false&size=110961&status=done&style=none&taskId=u51d74b52-8053-44f1-8fea-46a28ae7d9e&title=&width=891)
直至出现**it is not installed**
![pip uninstall2.png](https://cdn.nlark.com/yuque/0/2022/png/25978259/1642867336171-2527f626-c5bd-4df8-9c7f-66cf55e889a0.png#clientId=u10d16641-0449-4&crop=0&crop=0&crop=1&crop=0.8821&from=ui&height=412&id=u75aa8656&margin=%5Bobject%20Object%5D&name=pip%20uninstall2.png&originHeight=412&originWidth=906&originalType=binary&ratio=1&rotation=0&showTitle=false&size=68918&status=done&style=none&taskId=u949a9d00-33ab-4496-9932-6cb56e03d5a&title=&width=906)
### 3.如何在jupyter中重新安装
如果你已经从 conda 环境安装了 Jupyter，它将使用 Anaconda 的虚拟环境来执行 python 代码。
以下是在Jupyter Notebook中安装numpy的方法 ：

- 打开 Anaconda 提示符并输入 `conda install numpy`。
- 重新启动`Jupyter Notebook`和`Anaconda`。
### 4.在jupyter中检测是否解决问题
在`jupyter`中输入代码：
```
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
a = tf.random_normal([2,30])
sess = tf.Session()
out = sess.run(a)
x,y = out
plt.scatter(x, y)
plt.show()
```
运行结果如下图所示
![image.png](https://cdn.nlark.com/yuque/0/2022/png/25978259/1642906234431-4e9add98-f745-424b-9605-21aac045ecfd.png#clientId=u10d16641-0449-4&crop=0.0014&crop=0.0847&crop=0.9783&crop=0.8794&from=paste&height=381&id=uf0e0472c&margin=%5Bobject%20Object%5D&name=image.png&originHeight=487&originWidth=865&originalType=binary&ratio=1&rotation=0&showTitle=false&size=96974&status=done&style=none&taskId=u8a4aab6f-99f8-4dac-8a12-cca1c922f43&title=&width=676)
​

