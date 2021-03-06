---
layout: post
title: Python语法之函数
categories:
- Programming Language
tags:
- Python
---

## 函数
- 函数定义与调用
	- 函数定义：def fctname([paramname[=defaultvalue][,...]][,*args][,**kwargs]): instructions
	- 文档字符串：
		- 作为函数对象的注释说明，可通过对象的__doc__属性查看，或通过help()查看
		- 定义：函数体第一个字符串，且该字符串在函数体的最上面，一般采用三引号字符串
- 函数参数：
	- 参数传递是传递的引用(即绑定关系)，区别改变绑定的对象还是改变绑定关系
	- 关键参数：如say(say='hello,',something='world!')：
		- 定义时刻定义默认参数值
		- 调用时可不用顾忌定义时的参数顺序
	- 不定长参数：
		- 参数\*前缀声明一个匿名tuple参数，参数\**前缀声明一个dict参数
		- 调用时，要使用\*和\**放在关键字参数前
		- 符号(\*和\**)对元组和字典的作用只在定义函数和调用函数时才起作用
		- 函数print_params(x,y,z=3,\*pospar,\**keypar)，调用print_params(1,2,3,4,5,6,7,foo=1,bar=2)
			- pospar收集位置参数中除x,y,z外的剩余参数，并将其放入到元组中，即pospar引用(4,5,6,7)
			- keypar收集额外的关键字参数，并将其放入到字典中，即keypar引用{'foo':1,'bar':2}
		- 对于函数add(x,y),value1=(1,2),value2={'x':1,'y':2}，可如下调用：add(1,2),add(\*value1),add(\**value2)
	- 默认参数、赋值参数、不定长参数
- 函数返回值：
	- 即使没有明确调用return返回值，默认也返回None
	- 返回值可以返回多个值，如 return 1,2,3
- 特殊函数：
	- 递归函数
	- 嵌套函数：
		- 在函数中定义函数，可以多层嵌套
		- 内层函数可以访问外层函数中定义的变量,即闭包
		- 内部函数中对外层函数同名变量赋值操作时，隐藏了外部函数的同名变量，所以使用+=形式操作会报错
		- 默认内层函数的local namespace不包含外层函数定义的变量，但引用外层变量后会加入到内层local namespace中
	- 生成器：
		- 从语法上讲，生成器是一个使用yield的函数
		- yield语句返回一个值给调用者并暂停执行，在调用next()方法时再继续执行
	- 协同程序
	- 内置函数：
		- apply(fnc[,args][,kw])
		- filter(func,seq)
		- map(func,seq[,seq2...])
		- reduce(func,seq[,init])
	- lambda函数:
		- lambda param[,...]: expression
		- 如 f=lambda a,b:a+b 等价于 def f(a,b): return a+b
		- 其中expression不能包含循环和条件语句
	- 对象函数：通过定义__call__(self,args)可将类对象当成函数调用
	- 函数对象：函数作为对象，可用于赋值、函数参数、函数返回值等
- 作用域：
	- 除了全局作用域外，每个函数调用都会创建一个局部作用域
	- 局部变量会在局部作用域中屏蔽同名全局变量 -- 不推荐使用全局变量
	- 在局部作用域中引用全局变量使用关键字global