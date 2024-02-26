***
[来自](https://zhuanlan.zhihu.com/p/335347908#:~:text=1%20%E7%BB%84%E7%BB%87%E7%BB%93%E6%9E%84%201%20Python%E9%A1%B9%E7%9B%AE%E7%9A%84%E7%BB%84%E7%BB%87%E7%BB%93%E6%9E%84%E4%B8%BB%E8%A6%81%E7%94%B1%20%E5%8C%85--%E6%A8%A1%E5%9D%97--%E7%B1%BB%20%E8%BF%99%E4%BA%9B%E9%83%A8%E5%88%86%E6%9E%84%E6%88%90%E3%80%82%202%20%E5%8C%85%EF%BC%9A,%E4%B8%80%E4%B8%AA%E6%A8%A1%E5%9D%97%E4%B8%8B%E9%9D%A2%E4%B9%9F%E5%8F%AF%E4%BB%A5%E5%8C%85%E5%90%AB%E5%A4%9A%E4%B8%AA%E7%B1%BB%E3%80%82%20%E6%A8%A1%E5%9D%97%E4%B8%8B%E9%9D%A2%E4%B9%9F%E5%8F%AF%E4%BB%A5%E7%9B%B4%E6%8E%A5%E5%86%99%E5%87%BD%E6%95%B0%E3%80%82%204%20%E7%B1%BB%EF%BC%9A%20%E7%B1%BB%E4%B8%AD%E5%AE%9A%E4%B9%89%E4%BA%86%E5%8F%98%E9%87%8F%E5%92%8C%E5%87%BD%E6%95%B0%E3%80%82%205%20%E5%87%BD%E6%95%B0%EF%BC%9A%20%E7%94%A8%E4%BA%8E%E5%AE%9E%E7%8E%B0%E7%89%B9%E5%AE%9A%E5%8A%9F%E8%83%BD%EF%BC%8C)

# 1 组织结构
Python项目的组织结构主要由：**包--模块--类** 组成
1. **包**：等同于**文件夹**，可以包含多个**模块**。让普通文件夹变为Python包：在该文件夹下包含`__init__.py`文件。
2. **模块**：等同于**文件**，对应Python中的`.py`文件。**模块**下可以包含多个**类class**，也可以直接写**函数**。
3. **类**： 定义了变量和函数
4. **函数**： 略

# 2 导入
![](https://szltuchuang.oss-rg-china-mainland.aliyuncs.com/image/20240221163905.png)
此处:
1. `mytest`为**包(含有__init__.py的文件夹)**
2. `module1.py`和`module2.py`为**模块(文件)**
3. `main.py`为主函数


## 2.1 纯import导入

`import`可以导入**模块**和**包**.
不可以导入**变量**或**函数**.

### 2.1.1 导入包

可以只导入**包**, 此时等价于导入**包**的`__init__.py`文件(模块),这个模块用来导入这个包的全部模块:
	`__init__.py`里面用`from . import 模块名`来进行导入


![](https://szltuchuang.oss-rg-china-mainland.aliyuncs.com/image/20240221163957.png)

此处,如果`__init__.py`中没有`from`语句,那么`main.py`中的`mytest.module1.`就无法运行.~~盲猜标准库就是这样的~~

### 2.1.2 导入模块
示例: 在main.py文件中导入包mytest中的模块module1.py和module2.py:
![](https://szltuchuang.oss-rg-china-mainland.aliyuncs.com/image/20240221164940.png)

```python
 import mytest.module1
 import mytest.module2 as mm2   # 多层调用太长，可以重命名
 ​
 print(mytest.module1.var1)
 print(mm2.num1)
 
 # 输出
1
Go
```

## 2.2 from ... import 

该语法可以导入**模块(.py文件), 变量, 函数** 

### 2.2.1 导入模块
![[../../zpng/Pasted image 20240221231847.png]]
此时`main.py`文件可以直接调用模块. 

```python
from mytest import module1

from mytest import module2

  

print(module1.num1)

print(module2.var1)
```

```text
1
Python
```


### 2.2.2 导入变量或者函数
![[../../zpng/Pasted image 20240221232116.png]]

![[../../zpng/Pasted image 20240221232123.png]]

### 2.2.3 导入模块下所有内容

***
