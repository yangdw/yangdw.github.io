---
layout: post
title: 编程范型
categories:
- Programming Language
tags:
- programming language
---

# 发现编程范型
---
# 发现编程范型一：认识范型
---
## 什么是编程范型
- 缘起：  
上学的时候学习C/C++语言和Java语言，工作后又陆续接触了一些编程语言python/lua/objective-c等，  
发现每门语言开始学习的东西都是相似的，helloworld程序、类型与变量、操作符、表达式及面向对象的类、继承和多态等，  
这个时候就会发现这种重复就是一种规律--网上查找之后才知道这个叫做编程范型。  
- 网上释义：  
编程范型，是一类典型的编程风格，提供了(同时决定了)程序员对程序执行的看法。
- 编程语言的思考：  
程序设计语言，是一个有限的词汇与规则的集合，用于描述一个特定的问题。  
所有的编程语言最后都要编译成机器理解的二进制代码，理论上所有语言都是相等的。  
但多语言的出现是伴随不同问题领域出现的，所以不同语言的侧重点也不同，语法也不同。  
- 范型：  
一个连贯完整的词汇集以及组合规则，可以产生一种范型--定义出很大一部分的语言特质。  
范型的重要性，可生成简洁的、可读性强的代码，保持问题域和软件模型之间的一致性。  
- 语言的其他特性：  
语言的其他特质：类型种类(动态/静态)，句法及其他因素。  
- 使用多语言编程：
	- 将问题域分解为差异明显的多个部分 -- 分析问题，合理的将分解问题
	- 为子领域选择正确的/合适的语言/范型

## 编程范型简要体系
> 该体系结构摘录自：[编程范型wiki](http://zh.wikipedia.org/wiki/%E7%BC%96%E7%A8%8B%E8%8C%83%E5%9E%8B)，虽然很多看不太懂，但是感觉不明觉厉  
> 推荐相关书籍：《七周七语言：理解多种编程范型》

- 面向代理
- 基于组件(如OLE)
	- 基于流
	- 管道(Unix/Linux中的管道)
- 连续式
- 并发计算
- 声明式(对比：命令式)
	- 函数式
		- 数据流
			- 面向细胞(电子表格)(如Microsoft FoxPro)
			- 无功
	- 面向图形
	- 目标导向
		- 约束
			- 逻辑
				- 回答集编程
				- 约束逻辑
				- 溯因逻辑
				- 归纳逻辑
- 事件驱动
	- 面向服务
	- 时间驱动
- 功能导向
- 函数级(对比：价值级)
- 命令式(对比：声明式)
	- 非结构化
		- 阵列(对比：标量)
		- 迭代式
	- 结构化
		- 过程式
			- 模块化
			- 递归式
		- 面向对象
			- 基于类
			- 基于原型
			- 自动机
			- 根据关注分离：
				- 面向方面(如AspectJ)
				- 面向主题
				- 面向角色
- 元编程
	- 面向属性
	- 自动
		- 泛型
			- 模板
				- 基于原则
		- 面向语言
			- 领域特定
			- 面向语法
				- 方言化
			- 意图
	- 反射式
- 不确定
- 并行计算
	- 面向过程
- 大规模与小规模编程
- 价值级(对比：函数级)

# 发现编程范型二：基础语法
---
> 见解基于已熟悉的三种语言：C/C++,Python和Java。

## 语言信息
- 版本信息：语言版本变迁历史
- 源代码文件：文件后缀，中间文件形式，源文件常用格式--如文件头、入口函数定义等
- 编译与运行：开发工具(编译器、解释器、调试器及IDE等)、发布方式(原生文件还是打包程序)、调试工具

## 基础语法
### 注释
- 好的代码应该是自解释的，但有时也需要注释的帮助。
- 传统型注释方式：单行注释，多行注释
- 功能性注释：
	- 作为对象的一部分，如Python中对象的__doc__属性
	- Java中的注解

### 类型系统
- 类型的作用：
	- 对象或数据对应空间大小，存储时占用的空间、读取时解析的空间
	- 对象或数据自身的操作及适用于该类型的操作集合
- 标识符、变量、文字常量及常量
	- 文字常量：源代码中直接书写的数值、字符串、布尔值等，常用语赋值语句的右侧
	- 标识符，命名规则，是否大小写敏感，关键字集合
	- 变量，命名规则，与内存区、对象的绑定关系
	- 常量，定义方式，明明常用法--如全大写等
- 类型分类：
	- 基本类型
		- 主要包括数值类型(整型、浮点型及复数等)、字符及字符串类型、布尔类型等
		- 字符串类型：存储方式、支持的操作符、编码问题
	- 扩展类型
		- 枚举类型
		- 空类型：void/None/null
		- 指针类型
		- 类类型
	- 内置容器
		- 数组类型：数组定义、多维数组、数组索引及越界访问问题等
		- 其他语言级支持容器，如Python的tuple/list/dict
- 类型转换规则
	- 自动类型转换
	- 强制类型转换

### 操作符
- 操作符，是对计算机指令系统的抽象封装
- 基本操作符--一般语言都支持的操作符：
	- 赋值操作
	- 算术运算符
	- 比较运算符
	- 逻辑运算符
	- 位操作运算符
- 特殊操作符：
	- 判断：三元操作符(?:)，sizeof，类型判断(instance of)
- 操作符优先级

### 语句
- 源代码的组织形式，好的源代码是便于阅读的源代码
- 单行语句
	- 单行语句，是否需要分号做结尾符
	- 空语句块--如{}及关键字pass都可表示空语句
- 语句块
	- 语句块定义方式：中括号表示{}，及Python的缩进表示法
	- 语句块，对变量及对象的生命周期及可见性的影响

### 流程控制
- 代码执行顺序，常用包括条件、循环及跳转
	- 条件，if/else,switch
	- 循环，while,do/while,for,foreach
	- 跳转，return,break,continue,goto

### 函数及方法
- 函数是对功能的抽象，封装实现功能的细节
- 函数签名，由函数名及参数列表决定，不包括函数返回值
- 函数定义
	- 函数参数：
		- 传参方式：传值、传引用、传指针
		- 默认值参数、不定长参数(可变参数)
		- 不安参数顺序，采用参数赋值方式调用函数
	- 函数返回值：
		- 函数返回值数量
		- 尾调用
- 特殊函数：
	- 递归函数
	- 嵌套函数
	- 匿名函数，如lambda函数
- 函数特殊应用：
	- 函数指针，函数对象
	- 重载函数

### 异常处理
- 异常处理是错误处理的一种方式，其他方式比如C的返回值判断
- 异常作用：可以将正常流程代码与异常处理代码分开
- 异常系统：
	- 抛出异常：throw或raise关键字抛出异常
	- 捕获异常：try/catch捕获异常
		- 系统定义异常、自定义异常
		- 异常捕获顺序
		- 捕获所有异常
		- finally在异常中的应用
	- 异常声明：函数中声明可能抛出的异常

### 代码组织方式
- 代码组织的目标：
	- 避免名字冲突问题
	- 组织源代码文件，便于项目管理
- 代码组织方式：
	- 命名空间、包
	- 源文件管理

# 发现编程范型三：容器及标准库
---
### 容器
- 常用容器：
	- 动态数组、列表、集合、映射、散列等
- 容器概念：
	- 队列、堆、二叉树、图等

### I/O
- 输入输出
- 文件系统

### 网络
- 网络通信

### 图形
- 图形库

### 数据库
- 数据库支持

# 发现编程范型四：面向对象
---
## 面向对象
- 面向对象的三个基本特征：抽象与封装、继承和多态
- - 类：
	- 类定义，类实例化
	- 数据成员与成员函数(方法)
	- 类成员访问控制机制
	- 类范围属性：静态类成员、类数据与类方法
	- 特殊方法：构造函数、析构函数、复制函数、重载操作符函数
	- 函数对象
	- 内部类
- 继承
	- 单继承与多继承
	- 是否有祖类--如object类
	- 继承访问控制
	- 虚函数、纯虚函数
	- 构造函数、析构函数的调用顺序
- 多态
	- 类型转换
	- 类方法在继承关系中查找顺序

# 发现编程范型五：高级特性
## 迭代器与生成器
## 泛型