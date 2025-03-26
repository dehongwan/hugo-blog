---
title: python-python-xlwings学习
date: 2025-03-26
description: 
tags:
  - python
slug:
---

<!--more-->
xlwings 中文学习笔记 

1. 安装
	对于windows, pip install xlwings
	安装依赖： 需要pywin32, comtypes
	对于windows系统，采用上述方式安装，会自动处理这些依赖
	对于NumPy, Pandas, Matplotlib, Pillow/PIL，推荐安装，
	xlwings与这些包联合使用，非常方便
	可以运行在Python 2.7和3.3+

2. 快速入门
	2.1 使用python脚本自动化与excel交互
		建立到工作簿的连接：
			>>>import xlwings as xw
			>>>wb = xw.Book() # 这会创建一个新的workbook
			>>>wb = xw.Book("FileName.xlsx") # 这会连接当前目录下已经存在的文件
			>>>wb = xw.Book(r"C:\path\to\file.xlsx") # 在Windwos上使用raw字符串转义反斜杠

		If you have the same file open in two instances of Excel, you need to fully qualify 
			it and include the app instance:
			>>>xw.apps[0].books['FileName.xlsx'] # 文档中的写法，事实是会出错，不知道为什么
			首先，不清楚什么情况下，需要在两个Excel实例中打开同一个文件，windows中打开Excel，
			只能打开一个实例。另外，如果使用xw的app实例，打开同一个excel文件，第一次打开的文件可读
			可写，第二次打开的实例，属于只读模式
			>>>app0 = xw.App(visible=True,add_book=False)
			>>>app1 = xw.App(visible=True,add_book=False)
			>>>print(xw.apps)
			>>>[] # 此时在任务管理器，可以看到两个EXCEL.EXE进程，但这里确是显示空，如果xw.App的参数为空，才会显示
			>>>app0.books["FileName.xlsx"] # 官网手册中提供的写法会报错，不知道为什么
			>>>wb0 = app0.books.open("FileName.xlsx")
			>>>wb1 = app1.books.open("FileName.xlsx") # 执行完上述两条指令后，文件FileName.xlsx显示在了两个excel实例中
												# 其中第一个可读可写，第二次打开，文件为只读模式

			>>>sht0 = wb0.sheets["Sheet1"] # 实例化一个sheet对象
			>>>sht0.range("A1").value = "Foo 1"
			>>>sht0.range("A1").value
			'Foo 1'

			有一些比较方便的特性可以用，比如说Range expanding：
			>>>sht0.range("A1").value = [['Foo 1', 'Foo 2', 'Foo 3'], [10.0, 11.0, 12.0]]
			上面指令执行的结果是，将二维数组放在了A1开始，C2结束的二维表格区域内，也就是
			Foo 1在A1格， F00 3在C1， 12.0在C2
			>>>sht0.range("A1").value
			'Foo 1'
			>>>sht0.range("A1").expand().value
			[['Foo 1', 'Foo 2', 'Foo 3'], [10.0, 11.0, 12.0]]

			为了完整性
			>>>wb0.save(FileSavePath)
			>>>wb0.close()
			>>>app0.quit()

			对于pandas， matplotlib也有很好的兼容性
			# 对于pandas，目前没怎么用到，这一段没有试
			>>>import pandas as pd
			>>>df = pd.DataFrame([[1, 2], [3, 4]], columns=['a', 'b'])
			>>>sht.range('A1').value = df
			>>>sht.range('A1').options(pd.DataFrame, expand='table').value
				a 	b
			0.0 1.0 2.0
			1.0 3.0 4.0

			可以把malplotlib的figures显示到excel中
			>>>import matplotlib.pyplot as plt
			>>>fig = plt.figure()
			>>>plt.plot([1, 2, 3, 4, 5])
			>>>sht.pictures.add(fig, name="MyPlot", update=True)

			# 当前活动sheet交互的快捷方式：xw.Range
			如果想快速的与当前的活动页进行交互，就不需要初始化一个workbook和sheet对象
			只是简单的如下:
			>>>import xlwings as xw
			>>>xw.Range("A1").value = "Foo"
			>>>xw.Range("A1").value
			'Foo'
			xw.Range只能用在与Excel交互时，如果在脚本中，就只能像上面那样通过book和sheet对象
			来进行

	2.2 宏： 从Excel调用Python
		可以使用RunPython函数从VBA中调用 Python函数
		Sub HelloWorld()
			RunPython("import hello; hello.world()")
		End Sub

		默认情况下，RunPython希望hello.py与Excel 文件在同一级目录下， 在python脚本中引用当前的Excel book,
		使用 xw.Book.caller
		# hello.py
		import numpy as np 
		import xlwings as xw

		def world():
			wb = xw.Book.caller()
			wb.sheets[0].range("A1").value = "Hello World!"

		？？？？这一块，需要根据以内容，总结出一个详细的使用说明和样例

	2.3 UDFs: User Defined Functions用户自定义函数(仅限windows)

		写一个自定义python函数:
		import xlwings as xw
		@xw.func
		def hello(name):
			return 'Hello {0}.format(name)'

		UDF同样可能使用接口转换函数
		import xlwings as xw
		import pandas as pd
		@xw.func
		@xw.arg('x', pd.DataFrame)
		def corr12(x):
			# x arrives as DataFrame
			return x.corr

		？？？？怎么调用这些自定义函数，还需要再仔细的看一下

3. Connect to a Book
	New book 	           xw.books.add()
	Book by (full) name    xw.books.open(r"C:/path/to/file.xlsx")
							or "C:\\path\\to\\file.xlsx"

4. 语法概述
	4.1 首先要先import xlwings as xw
	4.2 Active objects
		# Active app(i.e. Excel instance)
		>>>app = xw.apps.active

		# Active book
		>>>wb = xw.books.active # in active app
		>>>wb = app.books.active # in specific app

		# Active sheet
		>>>sht = xw.sheets.active # in active book
		>>>sht = wb.sheets.active # in specific book

		# Range on active sheet
		>>>xw.Range("A1") # on active sheet of active book of active app

		对于range区域的选择方法
		sht.range("A1")
		sht.range("A1:C1")等价于sht.range((1, 1), (1, 3))
		注意:采用坐标的形式，括号内是先纵坐标，再横坐标

	4.3 Full qualification(不知道怎么翻译)
		小括号是遵循了Excel的惯例，从1开始索引，中括号是遵循了python的惯例，
		从0开始索引，下面的表达式，都指向了同一个range
		xw.apps[0].books[0].sheets[0].range("A1")
		xw.app(1).books(1).sheets(1).range("A1")
		xw.apps[0].books["Book1"].sheets["Sheet1"].range("A1")
		xw.apps[1].books("Book1").sheets("Sheet1").range("A1")

	4.4 Range对象可以进行indexing/slicing
		>>>rng = sht.range("A1:D5")
		>>> rng[0, 0]
 			<Range [Workbook1]Sheet1!$A$1>
		>>> rng[1]
 			<Range [Workbook1]Sheet1!$B$1>
		>>> rng[:, 3:] # 第一个坐标为纵坐标，第二个坐标为横坐标(y, x)
			<Range [Workbook1]Sheet1!$D$1:$D$5>
		>>> rng[1:3, 1:3]
			<Range [Workbook1]Sheet1!$B$2:$C$3

	4.5 Range对象访问的快捷方法
		可以通过对Sheet对象进行索引或者切片，来访问range对象，这类似于
		sheet.range or sheet.cells
		>>> sht = xw.Book().sheets['Sheet1']
		>>> sht['A1']
		<Range [Book1]Sheet1!$A$1>
		>>> sht['A1:B5']
		<Range [Book1]Sheet1!$A$1:$B$5>
		>>> sht[0, 1]
		<Range [Book1]Sheet1!$B$1>
		>>> sht[:10, :10]
		<Range [Book1]Sheet1!$A$1:$J$10>

	4.6 对象层次结构
		>>> rng = xw.apps[0].books[0].sheets[0].range('A1')
		>>> rng.sheet.book.app
			<Excel App 1644>


5. 不同数据结构的处理

	5.1 Single Cells
		一个cell，默认可以返回的数据可以为float, unicode, None or datetime 对象，
		这取决这个cell包含什么数据
		>>> import datetime as dt
		>>> sht = xw.Book().sheets[0]
		>>> sht.range('A1').value = 1
		>>> sht.range('A1').value
		1.0
		>>> sht.range('A2').value = 'Hello'
		>>> sht.range('A2').value
		'Hello'
		>>> sht.range('A3').value is None
		True
		>>> sht.range('A4').value = dt.datetime(2000, 1, 1)
		>>> sht.range('A4').value
		datetime.datetime(2000, 1, 1, 0, 0)


	5.2 List

		5.2.1 一维列表(1d List)
		对于Range对象，其返回的多行或者多列数据，都会表现为一个列表，失去了是行还是列
		的形状信息
		>>> sht = xw.Book().sheets[0]

		# Column orientation (nested list)
		# 注意，如果需要将一个列表赋值到一列数据上，方法之一需要采用nested list
		>>> sht.range('A1').value = [[1],[2],[3],[4],[5]]  # 在列方向上的一个列表（采用嵌套链表的方式来表达列方向）
		>>> sht.range('A1:A5').value
			[1.0, 2.0, 3.0, 4.0, 5.0]

		>>> sht.range('A1').value = [1, 2, 3, 4, 5] # 行方向上的一个列表
		>>> sht.range('A1:E1').value
			[1.0, 2.0, 3.0, 4.0, 5.0]

		如果需要强制单个单元格的数据以列表的形式返回，采用如下的方式：
		>>>sht.range("A1").options(ndim=1).value
			[1.0]

		如果要将一个列表按列方向写入到Excel中，使用transpose选项：
		<<<sht.range("A1").options(transpose=True).value = [1,2,3,4]

		5.2.2 二维列表(2d List)
		如果想保持行或列 列表的形状，设置ndim选项，这样会返回三个nested lists(2d list)
		>>> sht.range('A1:A5').options(ndim=2).value
			[[1.0], [2.0], [3.0], [4.0], [5.0]]
		>>> sht.range('A1:E1').options(ndim=2).value
			[[1.0, 2.0, 3.0, 4.0, 5.0]]

		对于二维的Range，会自动以nested list 回返。如果需要将一个二维列表赋值给Excel中，只给
		出目标地址左上角的cell地址就可以。同时可以采用index索引的方式将数据读回python。
		>>> sht.range('A10').value = [['Foo 1', 'Foo 2', 'Foo 3'], [10, 20, 30]]
		>>> sht.range((10,1),(11,3)).value
			[['Foo 1', 'Foo 2', 'Foo 3'], [10.0, 20.0, 30.0]]

		为了降低与excel交互的次数，采用这种方式
		sht.range('A1').value = [[1,2],[3,4]] 比
		sht.range('A1').value = [1, 2] 和
		 sht.range('A2').value = [3, 4]的方式更有效率 


	5.3 Range expanding
		可以通过方法 expand或者options的选项关键字expand来获取excel中一块区域的维度。
		这两种方法，有区别，expand方法，返回一个将过扩展的Range对象。expand关键字，只是
		在获取Range对象的value时，才会生效。

		>>> sht = xw.Book().sheets[0]
		>>> sht.range('A1').value = [[1,2], [3,4]]
		>>> rng1 = sht.range('A1').expand('table')  # or just .expand()
		>>> rng2 = sht.range('A1').options(expand='table')
		>>> rng1.value
		[[1.0, 2.0], [3.0, 4.0]]
		>>> rng2.value
		[[1.0, 2.0], [3.0, 4.0]]
		>>> sht.range('A3').value = [5, 6]
		>>> rng1.value 
		[[1.0, 2.0], [3.0, 4.0]] # 因为rng1是expand函数返回的经过扩展之后的对象，所以，其值不变
		>>> rng2.value # rng2会重新根据expand关键字，来计算rng2的区域，所以，其包括新增加的值
		[[1.0, 2.0], [3.0, 4.0], [5.0, 6.0]]

		'table' expand方式，可以换成"down" 和"right"方向。

		结合给定左上角起始cell的Range对象来使用expand()函数，可以给我们提供一种灵活的建立
		excel的方式，我们可以随便的更改table的大小而不需要更改python 代码


	5.4 NumPy Arrays
		NumPy数组的工作方式类似于嵌套式数组，只不过空cells用nan表示 ，而不是用None.
		如果想把一个Range保存为数组，可以在options 选项中设置convert=np.array

		>>> import numpy as np
		>>> sht = xw.Book().sheets[0]
		>> sht.range('A1').value = np.eye(3)
		>>> sht.range('A1').options(np.array, expand='table').value
		array([[ 1.,  0.,  0.],
	       	   [ 0.,  1.,  0.],
	           [ 0.,  0.,  1.]])


    5.5 Pandas DataFrames
	    >>> sht = xw.Book().sheets[0]
		>>> df = pd.DataFrame([[1.1, 2.2], [3.3, None]], columns=['one', 'two'])
		>>> df
		   one  two
		0  1.1  2.2
		1  3.3  NaN
		>>> sht.range('A1').value = df
		>>> sht.range('A1:C3').options(pd.DataFrame).value
		   one  two
		0  1.1  2.2
		1  3.3  NaN
		# options: work for reading and writing
		>>> sht.range('A5').options(index=False).value = df
		>>> sht.range('A9').options(index=False, header=False).value = df


	5.6 Pandas Series
		>>> import pandas as pd
		>>> import numpy as np
		>>> sht = xw.Book().sheets[0]
		>>> s = pd.Series([1.1, 3.3, 5., np.nan, 6., 8.], name='myseries')
		>>> s
		0    1.1
		1    3.3
		2    5.0
		3    NaN
		4    6.0
		5    8.0
		Name: myseries, dtype: float64
		>>> sht.range('A1').value = s
		>>> sht.range('A1:B7').options(pd.Series).value
		0    1.1
		1    3.3
		2    5.0
		3    NaN
		4    6.0
		5    8.0
		Name: myseries, dtype: float64

		不论对于NumPy 数组还是Pandas 的DataFrame，只需要指定左上角cell的坐标就可以


6. xlwings 加载项(Add-in)
	xlwings加载项是使用RunPython和UDFs的首选方式，如果你只是想使用python通过xlwings
	来操作excel,那么你不需要了解xlwings加载项。

	适用版本是Excel>=2007 on windwos

	xlwings加载项被密码“xlwings”所保护，所以，如果你想调试或者加新的扩展，需要首先删除
	密码。


	6.1 安装 
		安装完xlwings后，在console下，采用:xlwings addin install，来安装xlwings 加载项
		
		安装完成后，打开一个Excel文件，右键点击"Sheet1"表单名，选择“查看代码”，就可以打开
		VBA编辑器。打开VBA编辑器之后，选择 工具->引用(R)，或者Alt+F11也可以。 就可以打开官方文档中提供的窗口，勾选xlwings。 在VBA 编辑器的左侧边栏，有xlwings项目，
		添入密码“xlwings”之后，就可以打开设置窗口，再删除掉密码，就可以进行其它操作了。


	6.2 全局设置

		6.2.1 Interpreter: 
			设置pyhton interpreter,如果为空，默认就是PATH中设置的python环境变量。

		6.2.2 PATHONPATH: 
			自定义函数等的源代码的路径，如果在和excel同级目录下没有找到自定义的
		脚本文件，就会在这个路径下找。

		6.2.3 UDF Modules: 
			python 模块文件的名字，也就是自定义函数所在的文件，注意没有.py扩展名，多
		个名字采用分号进行分隔。例如：UDF_MODULES = "common_udfs;myproject"。默认引入的文件是与
		excel文件同级目录下相同名字的.py文件。

		6.2.4 Debug UDFs:
			如果为了调试，你需要手动去运行xlwings COM server，勾选此选项

		6.2.5 Log File:
			空白或者添写完整的日志路径名称

		6.2.6 RunPython: Use UDF Server
			与UDFs使用相同的COM Server，这可以运行更快一些，因为每次函数调用完成后，不会关闭python
		解释器,不太懂COM Server，勾选此选项比较好

		6.2.7 Restart UDF Server:
			在下一次函数调用之前会重起python解释器，一般不需要勾选。


	6.3 全局配置: Ribbon/Config File
		全局的配置文件目录为：在user文件夹下.xlwings\xlwings.conf(试了一下，不行，好像不能手工设置)
		格式为：(关键字全部大写)
			"INTERPRETER","pythonw"
			"PYTHONPATH",""

		在windows console窗口，采用命令"xlwings quickstart myproject" 来生成一个xlwings工程，
		在此工程下会有一个配置文件，内部有详细说明。


7. VBA：RunPython
	
	7.1 xlwings add-in
		如果要想在VB程序中调用RunPython函数，需要添加xlwings add-in,上面已经讲过了。
		对于一个新项目，最简单的方法，就是在console中，使用quickstart命令，具体见Command
		Line Client.
		xlwings quickstart myproject
		在生成目录下，会有两个文件，一个是myproject.py,这个是脚本文件，我们可以在其中添加我们
		的功能，另一个myproject.xlsm，Sheet1是我们可以操作的表格，_xlwings.conf sheet是配置
		页。

	7.2 通过RunPython函数来调用Python函数
		使用xlwings quickstart 创建工程时，打开myproject.xlsm的VBA Eidtor(Alt+F11),已经添
		加了示例代码。
		Sub SampleCall()
    		mymodule = Left(ThisWorkbook.Name, (InStrRev(ThisWorkbook.Name, ".", -1, vbTextCompare) - 1))
    		RunPython ("import " & mymodule & ";" & mymodule & ".hello_xlwings()")
		End Sub

		import xlwings as xw

		在myproject.py中：
		def hello_xlwings():
    		wb = xw.Book.caller()
    		wb.sheets[0].range("A1").value = "Hello  yangkun xlwings!"

		@xw.func
		def hello(name):
    		return "hello {0}".format(name)

		注意： 需要将xw.Book.caller()函数内部，不能在函数外部调用，并将其返回结果作为
		全局变量使用。否则，当你使用了OPTIMIZED_CONNECTION = True设置时，
		它会阻止Excel正常的关闭，从而留下一个僵尸进程。

		对于需要参数和返回值的情况，建议使用UDFs，虽然UDFs只能在windows上使用。在RunPython
		中使用参数是非常不方便的，并且，RunPython不允许有返回值。


8. VBA: User Defined Functions(UDFs)
	UDFs目前只能在windows上使用
	如何控制参数和返回值的行为，参见11Converters and Options
	如果想对所提供的decorators 和选项有一个整体的理解，需要参建API docs: UDF decorators.

	8.1 对excel一次性的设置
		1. 使能"信任对VBA工程对象模型的访问"选项。在excel中文件->选项->信任中心->信任中心设置
			->宏设置
			Trust access to the VBA project object model
			File > Options > Trust Center > Trust Center Settings > Macro Settings

		2. 通过命令行安装add-in: xlwings addin install

	8.2 对于workbook的设置
		创建一个新工程最简单方便的方法就是在windows命令行使用"xlwings quickstart myproject"指令，
		这样可以自动在workbook中生成xlwings的reference.

	8.3 一个简单的UDF
		默认的addin 设置要求一个python文件
		此python文件与excel文件在同一级目录
		与Excel文件具有相同的名称，只是扩展名由.xlsm改为.py.
		当然，你可以通过xlwings ribbon的UDF Modules来设置特定的模块。(这一块没有试，
		我还是觉得采用推荐的quickstart就足够了。)

		假定，workbook为myproject.xlsm，那么你可以在myproject.py中添加如下代码：
		import xlwsings as xw

		@xw.func
		def double_sum(x, y):
			"""Returns twice the sum of the two arguments"""
			return 2 *（x + y）

		打开myproject.xlsx文件，修改_xlwings.conf配置页为 xlwings.conf,然后点击
		xlwings显示页上的Import Functions按钮
		否则为弹出Error对话框，显示"No command specified in the configuration, 
		cannot autostart server 1000"

		然后就可以在cell中输入公式了。
		文档中说，函数中加入的docstring(双三括号中的字符串)在Excel中会作为函数的说明出
		现，我这里没有显示出来，不知道为什么

		注意：
			1. 只需要在改变了函数的名称或者函数的参数的时候，才需要重新import自己写的函数；
			2. 当函数内部的代码发生改变时，要公式下次计算时，可以自动加载，但是modules的改变，
			却不会。这也正是python import 机制的工作方式。如果你想让一切处于一种正确的状态，可
			单击 Restart UDF Server.
			3. @xw.func这个decorator，会在函数被import 进Excel时被xwlings使用。这个decorator
			会告诉xlwings为哪个函数创建VBA封装函数，此decorator不会对python函数内部功能产生
			任何影响。

	8.4 数组公式
		对一个区域应用公式比对单个excel cell应用公式，要高效的多。你可以将一个Excel Range 
		作为参数传送给函数，对于python来说，你传入的就是一个list

		比如，你可以写一个函数，另Range中的每一个cell都加1
		@xw.func
		def add_one(data):
			return [[cell + 1 for cell in row] for row in data]

		单击Import Functions, 然后再A1:B2填充数值，选择另外一个同样形状的区域，然后在
		excel顶部的编辑栏输入公式 =add_one(A1:B2), 最后点击ctrl+shift+Enter生成数组公式
		如果所有的操作都正确的话，你在顶部的编辑栏里键入的公式会被一个大括号包围。

	8.5 Number of array dimensions: ndim
		上面的数组公式要求输入必须是2维的区域，也就是一个嵌入式的列表[[1, 2], [3, 4]]，因此，
		如果，你将公式应用到一个单独的cell上，就会得到TypeError:'float' object is not iterable.

		强制要求Excel传入一个二维的数组，而不管参数是一个单独的cell还是一个二维的range,可以加上如
		下语句：
			@xw.func
			@xw.arg('data', ndim=2) # 为了程序的稳定性，这句话就是必须要加的了
			def add_one(data):
				return [[cell + 1 for cell in row] for row in data]	

	8.6 Array formulas with NumPy and Pandas
		在UDF中采用numpy arrays或者Pandas，是很正常的需要。这样可能完全解锁python对于科学计算
		的支持。
		采用numpy arrays定义一个用于矩阵乘法的公式，我们可以这样定义函数:
		import xlwings as xw
		import numpy as np 

		@xw.func
		@xw.arg('x', np.array, ndim=2)
		@xw.arg('y', np.array, ndim=2)
		def matrix_mult(x, y):
			return x @ y

		注:如果你的python版本<3.5 并且numpy <1.10,需要用x.dot(y)代替x @ y

		对于Pandas的使用，计算基于数组的CORREL相关系数计算函数是一个很好的例子。Excel版本的
		CORREL只能计算两个数据集之间的相关系数，并且使用起来很麻烦。如果你想迅速的获取多个数据集
		之间相关系数矩阵，采用pandas来实现基于数组的CORREL2公式，只需要一句话就可以：
		import xlwings as xw
		import pandas as pd

		@xw.func
		@xw.arg("x", pd.DataFrame, index=False, header=False)
		@xw.ret(index=False, header=False)

		def CORREL2(x):
			"""
				Like CORREL, bus as array formula for more than 2 data sets
			"""
			return x.corr()

	8.7 @xw.arg and @xw.ret decorators
		当UDF处理的参数为Range对象时，我们可以用这两个装修器来进行修饰。可以应用 converters
		和options到函数的参数(@xw.arg)或者函数的返回值(@xw.ret).比如你想将输入参数转换为
		pandas的DataFrame类型，同时返回参数不需要有index(不清楚这样的做的意义)。可以这样
		写:
		@xw.func
		@xw.arg('x', pd.DataFrame)
		@xw.ret(index=False)
		def myfunction(x):
			# x in a DataFrame, do something with it.
			return x

	8.8 动态数组参数(Dynamic Array Formulas)
		使用Excel的array formulas，需要先指定结果数组的形状，然后再键入公式，最后点击：
		ctrl+shift+Enter,从保证数据完整性的角度，这是有意义的，但是让人觉得很麻烦。特别的，
		当采用的数组的数据是变化的情况时，这种限制就比较明显了。比如，所输入的数据是随时间
		而变化的。从v0.10开始 xlwings提供了dynamic UDF expansion.

		下面举例说明相关的语法和UDF 扩展的效果
		# r和c为输入的形状，np.random.randn的作用是从标准正态分布中取出采样值，并组合成
		r,c的形状。np.random.rand的作用类似，但要求采样值的范围[0, 1)
		@xw.func
		@xw.ret(expand="table")
		def dynamic_array(r, c):
			return np.random.randn(int(r), int(c)) 

		动态数组函数，不允许将动态的函数作为参数。
		另外，Expanding array formulas 是会在没有任何提示的情况下覆盖掉单元格的数据的。
		expanding的范围，就是数据开始到下，右两边出现空格的位置。如果空格后面还有数据，如
		果形状继续扩大，就会覆盖数据。
		Expanding array formulas will overwrite cells without prompting and leave an empty
		border around them, i.e. they will clear the row to the bottom and the column to the right of the array.

	8.9 Docstrings
		下面的例子来说明如何在python代码中添加文档字符串，这这些函数和参数的说明可以出现在Excel的
		提示中
		import xlwings as xw
		@xw.func
		@xw.arg('x', doc="This is x.")
		@xw.arg('y', doc="This is y.")
		def double_sum(x, y):
			"""Return twice the sum of the two arguments"""
			return 2 *（x + y）

		不清楚为什么，我这里没有任何显示。win10+excel2016

	8.10 "vba"
		It’s often helpful to get the address of the calling cell. Right now, one of the easiest ways to 
		accomplish this is to use the vba keyword. vba, in fact, allows you to access any available VBA 
		expression e.g. Application. Note, however, that currently you’re acting directly on the 
		pywin32 COM object:

		@xw.func
		@xw.arg("xl_app", vba="Application")
		def get_caller_address(xl_app):
			return xl_app.Caller.Address

		这一小节没有看太懂，Application是VBA里面的表达式？为什么需要获得这个地址？
 
	8.11 宏(Macros)
		这个需要看懂文档，再仔细试试


	8.12 用VBA来调用UDFs
		这些import进来的python函数，也是可以被VBA使用的。
		Sub MySub()

		Dim arr() As Variant
		Dim i As Long, j As Long

		    arr = my_imported_function(...)

		    For j = LBound(arr, 2) To UBound(arr, 2)
		        For i = LBound(arr, 1) To UBound(arr, 1)
		            Debug.Print "(" & i & "," & j & ")", arr(i, j)
		        Next i
		    Next j
		End Sub

		对于VBA不是很熟悉，这部分内容就是为了内容的完整性而加上的。


9. Debugging
	分两种情况debug xlwings，
	一、在RunPython的情况下，这种情况下，通过设置mock_caller，
	可以很方便的在Excel中和python中来回切换进行调试
	二、在UDFs下，对于debug UDFs,xlwings供了一个方便调试服务器

	当然，不管哪种方式，只有程序存在错误，Excel都会显示一个Python错误的
	消息对话框。

	9.1 RunPython
		看一下下面的code.
		# my_module.py
		def my_macro():
		wb = xw.Book.caller()
		wb.sheets[0].range("A1").value = "Hello, debug Macro."

		if __name__ == "__main__":
			# expect the Excel file next to this source file, adjust accordingly.
			xw.Book("myproject.xlsm").set_mock_caller()
			my_macro()

		我们在python环境中debug此代码时，set_mock_caller()函数会打开Excel文件，然后我们的函数就可以
		以进行相关的操作。当我们通过RunPython调用此python函数时，不需要更改任何代码。

		Sub my_macro():
			RunPython("import my_module; my_module.my_macro()")
		End Sub

	9.2 UDF debug server
		注：这部分，我采用的是eclpse+pydev的环境，没有测试通过，按本文的步骤，一直运行不到断点处，不知道
		为什么。pycharm还没有试。官方文档中给出的是pycharm社区版的截图。这部分需要继续完善
		在windows上，调试UDFs，只面要在Excel的xlwings选项卡中勾选Debug UDFs选项，然后再python 代码
		的最后加上如下代码:
		if __name__ == "__main__":
			xw.serve()

		当你在Excel中按ctrl+Alt+F9，对相关的函数进行重新计算时，在Python环境中，就会运行到相应的断点
		处或者运行到print函数位置。


10. Matplotlib
	使用pictures.add()方法，可以很容易将Matplotlib 图表作为一张图片插到Excel中

	10.1 直观感受一下
		最简单的例子如下所示：
		>>>import matplotlib.pyplot as plt
		>>>import xlwings as xw

		>>>fig = plt.figure()
		>>>plt.plot([1, 2, 3])

		>>>sht = xw.Book().sheets[0]
		>>>sht.pictures.add(fig, name="MyPlot", update=True)

		如果你设置update=True, 你可以改变图像的大小和位置而更新图像的内容。同时，如果其它具有相同名称的
		pictures.add()也将会更新此图像的内容，而不需要更改其大小和位置。这个参数，主要是用于相关图像的内
		容具有相关性的时候情况。

	10.2 与Excel的全面集成
		通过RunPython的方式绑定一个按钮，是可以跨平台处理的最常见的一种方式。
		在windows上，通过UDF的方式，可以集成的更好一些
		如下例子所示：
			@xw.func
			def myplot(n):
			    sht = xw.Book.caller().sheets.active
			    fig = plt.figure()
			    plt.plot(range(int(n)))
			    sht.pictures.add(fig, name="MyPlot", update=True)
			    return 'Plotted with n={}'.format(n)

		调试一下即可，可以很容易的得到与官方文档一致的结果。

	10.3 Properties(属性)
		图片的大小，位置和其它的属性信息，都可以作为pictures.add()函数的参数，或者通过访问图片对象
		(sht.pictures.add函数的返回的对象)来进行控制。
		如下代码所示：
			>>>sht = xw.Book().sheets[0]
			>>>sht.pictures.add(fig, name="MyPlot", update=True, 
					left=sht.range("B5").left, top=sht.range("B5").top)

		或者:
			>>>plot = sht.pictures.add(fig, name="MyPlot", update=True)
			>>>plot.height /= 2
			>>>plot.width /=2

	10.4 获取Matplotlib 图片对象的途径
		下面是一些如何得到matplotlib figure对象的例子

		10.4.1 通过PyPlot 接口
			import matplotlib.pyplot as plt
			fig = plt.figure()
			plt.plot([1, 2, 3, 4, 5])

			或者
			import matplotlib.pyplot as plt
			plt.plot([1, 2, 3, 4, 5])
			fig = plt.gcf()

		10.4.2 通过面向对象的接口
			from matplotlib.figure import Figure
			fig = Figure(figsize=(8, 6))
			ax = fig.add_subplot(111)
			ax.plot([1, 2, 3, 4, 5])

		10.4.3 通过Pandas
			import pandas as pd
			import numpy as np 

			df = pd.DataFrame(np.random.rand(10, 4), columns=['a', 'b', 'c', 'd'])
			fig = ax.get_figure()


11. Converters and Options

	Converter的设置通过Opentions中convert参数来指定。
	具体格式如下：
	>>>import xlwings as xw
					xw.Range                                                     UDFs
	reading 	xw.Range.options(convert=None, **kargs).value               @arg("x", convert=None, **kargs)
	writing     xw.Range.options(convert=None, **kargs).value=myvalue       @ret(convert=None, **kargs)

	kwargs(keyword arguments关键字参数)控制是特定的converter或者默认的converter的行为。例如:
	为默认converter 设置ynumbers选项，为DataFrame converter设置 index选项
	xw.Range("A1:C3").options(pd.DataFrame, index=False, numbers=int).value

	options函数的第一个参数指定converter，其后的参数来规定converter的行为。

	Converters are explicitely set in the options method when manipulating Range objects or 
	in the @xw.arg and @xw.ret decorators when using UDFs. If no converter is specified, 
	the default converter is applied when reading. When writing, xlwings will automatically
	apply the correct converter (if available) according to the object’s type that is being 
	written to Excel. If no converter is found for that type, it falls back to the default converter.


	11.1 默认Converter

		如果不设定options的参数(xw.Range.options(convert=None, **kargs).value),对数据的处理采用
		如下方式：
		a) 对于读入的单一cell，如果cell中保存的是数字，读入后按floats处理；如果保存的是text，按unicode
			字符串处理；如果读的是时间，按datetime类型处理；如果cell为空，读入的是None.
		b) 多行/列，读入之后认为是列表，e.g.[None, 1.0, 'a string']
		c) 二维的ranges，读入之后会被认为是嵌入式列表， e.g.
			[[None, 1.0, 'a string'], [None, 2.0, 'another string']]


		对于默认的converter，可以设置如下参数来控制其行为:

		a) ndim
			不论读入的Range的形状， 强制读的数据为1维或者2维,只是针对读入的数据，
			控制其读入到程序中的形状，无法控制写入的格式 
			>>>import xlwings as xw
			>>>sht = xw.Book().sheets[0]
			>>>sht.range('A1').value = [[1, 2], [3, 4]]
			>>>sht.range('A1').value
			1.0
			>>>sht.range("A1").options(ndim=1).value
			[1.0]
			>>>sht.range("A1").options(ndim=2).value
			>>>[[1.0]]
			>>>sht.range("A1:A2").value
			[1.0 3.0]
			>>>sht.range("A1:A2").options(ndim=2).value
			[[1.0], [3.0]]

			注意，对于
			>>>sht.range("A1:B2").options(ndim=1).value
			会报异常
			>>>sht.range("A1:B2").options(ndim=2).value
			[[1.0, 2.0], [3.0, 4.0]]
			>>>sht.range("A1:B2").value
			[[1.0, 2.0], [3.0, 4.0]]

		b) numbers
			默认情况下，cell中的数字会被解析为float类型，但可以将其指定为int，
			>>>sht.range('A1').value = 1
			>>>sht.range('A1').value
			1.0
			>>>sht.range('A1').options(numbers=int).value
			1
			或者，可以将具体单个参数的函数的float类型参数指定为int
			对于UDFs中，可以这样指定
			@xw.func
			@xw.arg('x', numbers=int)
			def myfunction(x):
				# all numbers in x arrive as int
				return x

			Note: Excel always stores numbers internally as floats, which is the reason
			why the int converter rounds numbers first before turning them into integers. 
			Otherwise it could happen that e.g. 5 might be returned as 4 in case it is 
			represented as a floating point number that is slightly smaller than 5. Should
			you require Python’s original int in your converter, use raw int instead.

			这段话的大意是说，在Excel内部存储数据，都是按float来存，对于int converter来说，先对数据
			做round操作（取数据最接近的整数），然后取整。最后一句没看懂是什么意思。Should
			you require Python’s original int in your converter, use raw int instead.

		c) dates
			默认情况下，cell中的dates数据类型会被解析为datetime.datetime，但可以更改为datetime.date
			Range情况下:
				>>>import datetime as dt
				>>>sht.range("A1").options(dates=dt.date).value

			UDFs:@xw.arg("x", dates=dt.date)
			    UDFs: @xw.arg('x', dates=dt.date)

				Alternatively, you can specify any other function or type
				which takes the same keyword arguments as datetime.datetime, 
				for example:
					>>> my_date_handler = lambda year, month, day, **kwargs: 
						"%04i-%02i-%02i" % (year, month, day)
					>>> sht.range('A1').options(dates=my_date_handler).value
					'2017-02-20'
				或者，在可以传入datetime.datetime的场合，都可以指定自定义的类型

		d) empty
			空的cell将会被解析为None,也可以按下面的方式进设定:
			Range: >>>sht.range("A1").options(empty="NA").value
			UDFs: @xw.arg("x", empty="NA")

		e) Transpose转置
			这个设置可以使我们将一个列表按列的方式写入到excel中
			Range: sht.range("A1").options(transpose=True).value=[1,2,3]
			UDFs:
				@xw.arg("x", transpose=True)
				@xw.ret(transpose=True)
				def myfunction(x):
					# x will be returned unchanged as transposed both 
					# when reading and writing 
					return x
					
		f) expand
			这个设置与Range对象的table, vertical, horizontal属性类似，但只有在获取
			Range的值是，才进行计算 
			>>>sht.range("A1").value = [[1, 2], [3, 4]]
			>>>rng1 = sht.range("A1").expand()
			>>>rng2 = sht.range("A1").options(expand="table")
			>>>rng1.shape
			(2, 2)
			>>>rng2.shape
			(1, 1)
			>>>rng1.value
			[[1.0, 2.0], [3.0, 4.0]]
			>>>rng2.value
			[[1.0, 2.0], [3.0, 4.0]]

			>>>sht.range("A3").value = [5, 6]
			>>>rng1.value
			[[1.0, 2.0], [3.0, 4.0]]

			>>>rng2.value
			>>>[[1.0, 2.0], [3.0, 4.0], [5.0, 6.0]]

			注：采用 sht.range('A1').expand()这种方式，会返回一个Range对象，此时
			Range的内容就已经确定了，shape也就确定了。
			如果采用options的方式rng2 = sht.range('A1').options(expand='table')，
			每次调用时，rng2的值，都会重新计算，此方式适用数据会动态改变的情况，
			数据改变时，不需要更改code.但如果需要计算Range的shape，就得采用第一种方式。

	11.2 内置converters
		xlwings提供了一些针对特定应用场合的converters，比如转换为dictionaries,
		Numpy arrays, Pandas Series 和DataFrames.这些converters基于上面上默认
		converters,所以，在大多数情况下，上面的选项设置对于本节也都是适用的，除非
		有一些设置根本没有意义，比如对于dictionary 来说ndim选项就没有意义。

		下面的例子，对于xlwings.Range和UDFs都是适用的，虽然只是展示了一种用法。

		11.2.1 Dictionary converter
			这个converter可以将两列的数据，转换为字典，如果数据按row来排列，需要
			使用transpose

			a   1       
			b   2       
			>>>sht.range("A1:B2").options(dict).value
			{"a": 1.0, "b": 2.0}

			a   b
			1   2
			>>>sht.range("A1:B2").options(dict, transpose=True).value
			{"a": 1.0, "b": 2.0}

		11.2.2 Numpy array converter
			options: dtype=None, copy=True, order=None, ndim=None
			前三个参数，与直接使用np.array()时的设置是一样的，ndim的使用与上面描述一样
			可以返回 numpy scalars, 1维数组，或者2维数组
			例如：  写入excel，是可以自动选择converter的
				>>>import numpy as np 
				>>>sht.range("A1").options(transpose=True).value = np.array([1, 2, 3])
				>>>sht.range("A1:A3").options(np.array, ndim=2).value
				array([[1.], 
					   [2.], 
					   [3.])
				>>>sht.range("A1:A3").options(np.array, ndim=1).value
				array([1., 2., 3.])
				>>>sht.range("A1:A3").options(np.array).value
				array([1., 2., 3.])

		11.2.3 Pandas Series converter
			options: dtype=None, copy=False, index=1, header=True
			前两个参数的使用与直接应用 pd.Series()一样，ndim对于Pandas
			series没有影响，因为series一直都是按列方向运算的。

			index: int or Boolean
    			When reading, it expects the number of index columns shown in Excel.
    			When writing, include or exclude the index by setting it to True or False.
			header: Boolean
    			When reading, set it to False if Excel doesn’t show either index or series 
    			names.When writing, include or exclude the index and series names by
    			setting it to True or False.

				For index and header, 1 and True may be used interchangeably.
				没看懂index的使用，>>> sht = xw.Book().sheets[0]
				>>> s = sht.range('A1').options(pd.Series, expand='table').value
				>>> s
				date
				2001-01-01    1
				2001-01-02    2
				2001-01-03    3
				2001-01-04    4
				2001-01-05    5
				2001-01-06    6
				Name: series name, dtype: float64
				>>> sht.range('D1', header=False).value = s

		11.2.4 Pandas DataFrame Converter (和上面一样，没看太懂参数的意义)
			options: dtype=None, copy=False, index=1, header=1

			The first 2 options behave the same as when using pd.DataFrame() directly. 
			dim doesn’t have an effect on Pandas DataFrames as they are automatically 
			read in with ndim=2.

			index: int or Boolean
    			When reading, it expects the number of index columns shown in Excel.
    			When writing, include or exclude the index by setting it to True or False.
			header: int or Boolean
    			When reading, it expects the number of column headers shown in Excel.
    			When writing, include or exclude the index and series names by setting it
    			 to True or False.

			For index and header, 1 and True may be used interchangeably.

			Example:


			>>> sht = xw.Book().sheets[0]
			>>> df = sht.range('A1:D5').options(pd.DataFrame, header=2).value
			>>> df
			    a     b
			    c  d  e
			ix
			10  1  2  3
			20  4  5  6
			30  7  8  9

			# Writing back using the defaults:
			>>> sht.range('A1').value = df

			# Writing back and changing some of the options, e.g. getting rid of the index:
			>>> sht.range('B7').options(index=False).value = df

			The same sample for UDF (starting in Range('A13') on screenshot) looks like this:

			@xw.func
			@xw.arg('x', pd.DataFrame, header=2)
			@xw.ret(index=False)
			def myfunction(x):
			   # x is a DataFrame, do something with it
			   return x

		11.2.5 xw.Range and ‘raw’ converters
			Technically speaking, these are “no-converters”.

   			If you need access to the xlwings.Range object directly, you can do:

		    @xw.func
		    @xw.arg('x', xw.Range)
		    def myfunction(x):
		       return x.formula

    		This returns x as xlwings.Range object, i.e. without applying any 
    		converters or options.

    		The raw converter delivers the values unchanged from the underlying 
    		libraries (pywin32 on Windows and appscript on Mac), i.e. 
    		no sanitizing/cross-platform harmonizing of values are being made. 
    		This might be useful in a few cases for efficiency reasons. E.g:

		    >>> sht.range('A1:B2').value
		    [[1.0, 'text'], [datetime.datetime(2016, 2, 1, 0, 0), None]]

		    >>> sht.range('A1:B2').options('raw').value  # or sht.range('A1:B2').raw_value
		    ((1.0, 'text'), (pywintypes.datetime(2016, 2, 1, 0, 0, tzinfo=TimeZoneInfo('GMT Standard Time', Tru

	11.3 Custom Converter
		实现自定义的converter的步骤如下：
			a) 定义一个继承自xlwings.conversion.Converter的类；
			b) 以static或者是类方法实现 read_value 和 有write_value两个方法; 
				在read_value中， value参数是基类的converter的返回值，因此，如果没有指定base,
				返回值将使用默认的converter返回(不清楚说的base在哪指定)

				在write_value中，value是即将写入到Excel中的值，必须以默认的converter希望的格式
				返回。 同样的，如果没有指定base，将使用默认的converter.

			在通过xw.Range.options方法指定的options字典中将包含所有的关键字参数。
			例如: 调用 xw.Range("A1").options(myoption="some_value")或者通过 
			@arg 和@ret装修器来指定。
			下面是基本的结构:

			from xlwings.conversion import Converter
			class MyConverter(Converter):

				@staticmethod
				def read_value(value, options):
					myoption = options.get("myoption", default_value) #不知道这样有没有问题
					return_value = value # Impoement your conversion here
					return return_value

				@staticmethod
				def write_value(value, options):
					myoption = options.get("myoption", default_value)
					return_value = value # Implement your conversion here
					return return_value 

			可选设置一: 设置base converter(base就是一个类名),在已经有base基类基础上创建一个新的
			converter.例如那些内置的转换器: DictConverter, NumpyArrayConverter, 
			PandasDataFrameConverter, PandasSeriesConverter等。

			可选设置二: 注册converter: 你可以先自定义一个类型，使你的自定义的converter成为其默认
			converter， 同时，你也可以给你的converter注册一个别名，这样就可以通过别名而不是通过
			类名来调用你的自定义converter.

			接下来的例子能更清楚的阐明整个自定义converter的过程。这个自定义的converter自定义了一个
			DataFrame converter。通过支持丢弃nan数据的功能来扩展内置的converter.

			from xlwings.conversion import Converter, PandasDataFrameConverter

			class DataFrameDropna(Converter):
				base = PandasDataFrameConverter

				@staticmethod
				def read_value(builtin_df, options):
					dropna = options.get("dropna", False) # set default to False
					if dropna:
						converted_df = buildin_df.dropna()
					else:
						converted_df = builtin_df

					# This will arrive in Python when using the DataFrameDropna converter for reading
					return converted_df

				@staticmethod
				def write_value(df, options):
					dropna = options.get("dropna", False)
					if dropna:
						converted_df = df.dropna()
					else:
						converted_df = df
					# This will be passed to the build-in PandasDataFrameConverter when writing 
					return converted_df

			下面看看如何使用：
				默认DataFrames的converter：
					# Write
					sht.range("A").value = df

					# Read
					sht.range("A1:C4").options(pd.DataFrame).value

				DataFrameDropna converter:
					# Write
					sht.range("A7").options(DataFrameDropna, dropna=True).value = df

					# Read
					sht.range("A1:C4").options(DataFrameDropna, dropna=True).value 

				注册一个别名:
					DataFrameDropna.register("df_dropna")

					# Write
					sht.range("A12").options("df_dropna", dropna=True).value = df

					# Read
					sht.range("A1:C4").options("df_dropna", dropna=True).value 

				将DataFrameDropna 注册为DataFrames类型的默认converter
					DataFrameDropna.register(pd.DataFrame)

					# Write
					sht.range("A13").options(dropna=True).value = df

					# Read
					sht.range("A1:C4").options(pd.DataFrame, dropna=True).value

		这些例子对于UDFs同样适用:
			@xw.func
			@arg("x", DataFrameDropna, dropna=True)
			@ret(DataFrameDropna, dropna=True)
			def myfunction(x):
				# ...
				return x 
	注： python 对象需要经过转换流水线上的多个stages才能被写入到Excel中，同样将Excel/COM对象
		读入到python中，也需要经过多个stages.
		转换流水线，在Accessor classes类中定义。一个Converter 是一个在默认的流水线中加入了特殊
		类型处理的stages之后的Accessor类.

		Converter 类为编写自定义的Converter类提供了一个基本的框架，方便自定义Converter的编写。
		如果你需要对Converter有更多的控制，那么你需要直接去继承Accessor类，这需要做更多的工作，
		而且，目前没有文档说明。



12. Command Line Client 

	12.1 快速入门
		在windows Console中，使用xlwings quickstart myproject来创建工程。
		这是目前最快捷的方式。这个命令会创建myproject的文件夹，里面有一个Excel
		workbook已经包含了对于xlwings add-in的引用，同时包含一个python文件，可 
		以立刻使用。
		myproject
			|--myproject.xlsm
			|--myproject.py

		如果你想通过VBA模块而不是addin的方式使用xlwings，使用--standalone或者-s
		xlwings quickstart myproject -standalone
		(目前不太清楚，VBA模块的方式，具体指啥)

	12.2 加载项(Add-in)
		与add-in相关的命令行命令，可以方便在在windows上安装或者卸载addin.
		注意，通过命令行来安装或者更新add-in时，需要关闭掉Excel。如果还有错误，那么你需要打开任务管理器
		杀掉所有的EXCEL.EXE进程

		xlwings addin install: 拷贝xlwings add-in 到XLSTART文件夹
		xlwings addin update: 用最新的xlwings add-in 更新当前的版本
		xlwings addin remove: 从XLSTART文件夹删除xlwings add-in
		xlwings addin status: 如果add-in已经安装的话，显示安装路径

		一旦add-in安装完成，在Excel的功能区(Excel Ribbon)就会显示xlwings选项卡


13. 当xwlings不能满足您的需求时怎么办?

	如果xlwings中没有支持某些功能，执行以下操作
	首先，可以在github上开一个feature request的话题；
	其次，在windwos上，xlwings本质上是一层比较友好精巧的pywin32的封装，
	你可以通过api属性来访问底层对象。
		>>>sht = xw.Book().sheets[0]
		>>>sht.api

	这些对象和sht.range('A1').api是一致的。
	底层对象将使用pywin32(感觉很像VBA)和appscript(感觉不像VBA)的语法为您提供使用VBA可以做的几乎所有事情。
	但是，除了看起来很难看之外，请记住，它使您的代码平台相关，也就是说，即使您选择了选项2)，
	您也应该遵循选项1)并打开一个问题，以便该特性能够进入库(跨平台的，带有python语法的)。


14. Extnesions(扩展)
	使用自己的代码(采用udf或RunPython宏的方式)扩展xlwings addin的功能很容易，你可以部署它们，
	而无需最终用户自己导入或编写函数。只需在xlwings插件中添加另一个VBA模块和相应的代码即可。
	可以从每个工作簿中使用UDF扩展，而无需设置引用。

	In-Excel SQL
	xlwings插件附带了一个内置扩展，增加了excel SQL语法:
	=sql(SQL Statement, table a, table b, ...)

	具体参见官方文档中的例子
	可以从每个工作簿中使用UDF扩展，而无需设置引用。


15. Troubleshooting(故障排除)

	一般的问题是"dll not found"

	15.1 dll丢失问题
		xwwings32-<version>.dll和xwwings64-<version>.dll与python.exe在同一目录下，如果安装过程出错了
		采用pip 重新安装

	15.2 检查设置
		检查add-in 中的Interpreter设置和config页。
		如果这部分有问题，你可以先确定本机是否安装好了python，如果有，可能是路径没有设置对
		在Interpreter中或者config sheet中设置python.exe的完整路径即可。


16. API Documentation

	16.1 顶层函数(Top-level functions)
		xlwings.view(obj, sheet=None)
		功能： 打开一个新的workbook并且默认在第一个sheet显示参数中的obj
		如果提供了一个sheet对象，这个函数会先清空这个sheet然后才会显示对
		象。如果没有提供sheet对象，会打开一个新的workbook对象，并对第一个
		sheet显示此对象。
		obj包含numbers, strings, lists, numpy arrays, pandas dataframe
		具有内置converter的对象。

		>>>import xlwings as xw 
		>>>import pandas as pd
		>>>import numpy as np 
		>>>df  = pd.DataFrame(np.random.rand(10, 4), columns=['a', 'b', 'c', 'd'])

	16.2 对象模型(Object model)

		16.2.1 Apps
			class xlwings.main.Apps(impl)
			 一个app对象的集合
			 >>>import xlwings as xw
			 >>>xw.apps
			 Apps([<Excel App 1668>, <Excel App 1644>])
			 >>>xw.apps.count
			 2
			 >>>xw.apps.active
			 <Excel App 1668>

			 active: 返回当前活动的app，这个是属性

			 add() # 这个是函数 
			 创建一个新的App,并且使新的App成为活动的那个，返回一个App 对象

			 count: # 这个是属性
			 	返回apps中app的个数

		16.2.2 App
			class xlwings.App(visible=None, spec=None, add_book=True, impl=None)
			>>>import xlwings as xw
			>>>app1 = xw.App()
			>>>app2 = xw.App()
			一个App对应一个Excel实例，
			参数说明:
			visible: 第一次创建App的时候，此值应为True,否则无法创建App对象。
			如果不设置这个值，那么默认会设置为None,此时，也就是会保持App的状态，如果
			App不存在，就设置为True.

			activate(steal_focus=False)
				激活Excel App,
				steal_focus(bool, default False)
				将Excel设置为最前端的程序，并且焦点转移到Excel.

			api
				返回正在使用的引擎的本机对象(pywin32, appscript obj)

			books:
				返回当前打开的Books对象的集合

			calculate()
				Calculates all open books.不知道什么意思，没看懂.

			calculation: (同样没看懂)
				Returns or sets a calculation value that represents 
				the calculation mode. Modes: 'manual', 'automatic', 'semiautomatic'

				Examples

				>>> import xlwings as xw
				>>> wb = xw.Book()
				>>> wb.app.calculation = 'manual

			display_alerts:
			    The default value is True. Set this property to False to 
			    suppress prompts and alert messages while code is running; 
			    when a message requires a response, Excel chooses the default response.
			    当code运行的时候，可以防止出现报错的行为，没使用过呀。

			hwnd:
				返回windows 句柄

			kill()
				杀掉Excel app的进程，使app强制退出.

			macro(name)

			    Runs a Sub or Function in Excel VBA that are not part 
			    of a specific workbook but e.g. are part of an add-in.
			    Parameters:	name (Name of Sub or Function with or without 
			    module name, e.g. 'Module1.MyMacro' or 'MyMacro') –

			    Examples

			    This VBA function:

			    Function MySum(x, y)
			        MySum = x + y
			    End Function

			    can be accessed like this:

			    >>> import xlwings as xw
			    >>> app = xw.App()
			    >>> my_sum = app.macro('MySum')
			    >>> my_sum(1, 2)
			    3

			pid:
				返回app的进程句柄PID

			quit:
				Quits the application without saving any workbooks.

			range(cell1, cell2=None):
				Range object from the active sheet of the active 
				book, see Range().

			screen_updating:
			    Turn screen updating off to speed up your script. 
			    You won’t be able to see what the script is doing, 
			    but it will run faster. Remember to set the 
			    screen_updating property back to True when your script ends.

			selection:

			    Returns the selected cells as Range.

			version:

			    Returns the Excel version number object.

			    Examples

			    >>> import xlwings as xw
			    >>> xw.App().version
			    VersionNumber('15.24')
			    >>> xw.apps[0].version.major
			    15

			visible:
			    Gets or sets the visibility of Excel to True or False.
			    注: 将这个属性设置为False，app实例仍然存在，只是隐藏，而在
			    生成app=xw.App()的时候，如果设置visible=False,是生不成
			    App实例的.

		16.2.3 Books

			 class xlwings.main.Books(impl)

			    A collection of all book objects:

			    >>> import xlwings as xw
			    >>> xw.books  # active app
			    Books([<Book [Book1]>, <Book [Book2]>])
			    >>> xw.apps[0].books  # specific app
			    Books([<Book [Book1]>, <Book [Book2]>])

			    active

			        Returns the active Book.

			    add()

			        Creates a new Book. The new Book becomes the active Book. Returns a Book object.

			    open(fullname)

			        Opens a Book if it is not open yet and returns it. If it is 
			        already open, it doesn’t raise an exception but simply 
			        returns the Book object.
			        Parameters:	fullname (str) – filename or fully qualified 
			        filename, e.g. r'C:\path\to\file.xlsx' or 'file.xlsm'. Without 
			        a full path, it looks for the file in the current working directory.
			        Returns:	Book
			        Return type:	Book that has been opened.

		16.2.4 Book

			class xlwings.Book(fullname=None, impl=None)

		    A book object is a member of the books collection:

		    >>> import xlwings as xw
		    >>> xw.books[0]
		    <Book [Book1]>

		    The easiest way to connect to a book is offered by xw.Book: 
		    it looks for the book in all app instances and returns an error, 
		    should the same book be open in multiple instances. To connect 
		    to a book in the active app instance, use xw.books and to refer 
		    to a specific app, use:

		    >>> app = xw.App()  # or something like xw.apps[0] for existing apps
		    >>> app.books['Book1']

		    			xw.Book 	xw.books
		    New book 	xw.Book() 	xw.books.add()
		    Unsaved book 	xw.Book('Book1') 	xw.books['Book1']
		    Book by (full)name 	xw.Book(r'C:/path/to/file.xlsx') 	
		    xw.books.open(r'C:/path/to/file.xlsx')
		    Parameters:	fullname (str, default None) – Full path or 
		    name (incl. xlsx, xlsm etc.) of existing workbook or name 
		    of an unsaved workbook. Without a full path, it looks for 
		    the file in the current working directory.

		    activate(steal_focus=False)
		        Activates the book.
		        Parameters:	steal_focus (bool, default False) – If True, 
		        make frontmost window and hand over focus from Python to Excel.

		    api
		        Returns the native object (pywin32 or appscript obj) of the engine being used.

		    app

		        Returns an app object that represents the creator of the book.

			    classmethod caller()

			        References the calling book when the Python function is called 
			        from Excel via RunPython. Pack it into the function being 
			        called from Excel, e.g.:

			        To be able to easily invoke such code from Python for debugging, 
			        use xw.Book.set_mock_caller().

		    close()

		        Closes the book without saving it.
		        调用此方法之前，要先保存workbook.

		    fullname

		        Returns the name of the object, including its path on disk, 
		        as a string. Read-only String.

		    macro(name)

		        Runs a Sub or Function in Excel VBA.
		        Parameters:	name (Name of Sub or Function with or without module 
		        name, e.g. 'Module1.MyMacro' or 'MyMacro') –

		        Examples

		        This VBA function:

		        Function MySum(x, y)
		            MySum = x + y
		        End Function

		        can be accessed like this:

		        >>> import xlwings as xw
		        >>> wb = xw.books.active
		        >>> my_sum = wb.macro('MySum')
		        >>> my_sum(1, 2)
		        3

		        See also: App.macro()

		    name

		        Returns the name of the book as str.

		    names

		        Returns a names collection that represents all the names in the 
		        specified book (including all sheet-specific names).

		    static open_template()

		        Creates a new Excel file with the xlwings VBA module already 
		        included. This method must be called from an interactive Python shell:

		        >>> xw.Book.open_template()

		        See also: Command Line Client

		        New in version 0.3.3.

		    save(path=None)

		        Saves the Workbook. If a path is being provided, this works 
		        like SaveAs() in Excel. If no path is specified and if the file
		        hasn’t been saved previously, it’s being saved in the current
		        working directory with the current filename. Existing files 
		        are overwritten without prompting.
		        Parameters:	path (str, default None) – Full path to the workbook

		        Example

		        >>> import xlwings as xw
		        >>> wb = xw.Book()
		        >>> wb.save()
		        >>> wb.save(r'C:\path\to\new_file_name.xlsx')

		    selection

		        Returns the selected cells as Range.

		    set_mock_caller()

		        Sets the Excel file which is used to mock xw.Book.caller() when 
		        the code is called from Python and not from Excel via RunPython.

		        Examples

		        # This code runs unchanged from Excel via RunPython and from Python directly
		        import os
		        import xlwings as xw

		        def my_macro():
		            sht = xw.Book.caller().sheets[0]
		            sht.range('A1').value = 'Hello xlwings!'

		        if __name__ == '__main__':
		            xw.Book('file.xlsm').set_mock_caller()
		            my_macro()

		    sheets

		        Returns a sheets collection that represents all the sheets in the book.

		16.2.5 Sheets

			class xlwings.main.Sheets(impl)

		    A collection of all sheet objects:

		    >>> import xlwings as xw
		    >>> xw.sheets  # active book
		    Sheets([<Sheet [Book1]Sheet1>, <Sheet [Book1]Sheet2>])
		    >>> xw.apps[0].books['Book1'].sheets  # specific book
		    Sheets([<Sheet [Book1]Sheet1>, <Sheet [Book1]Sheet2>])

		    New in version 0.9.0.

		    active
		        Returns the active Sheet.

		    add(name=None, before=None, after=None)

		        Creates a new Sheet and makes it the active sheet.
		        Parameters:	
		            name (str, default None) – Name of the new sheet. If None,
		            will default to Excel’s default name.
		            before (Sheet, default None) – An object that specifies the 
		            sheet before which the new sheet is added.
		            after (Sheet, default None) – An object that specifies the 
		            sheet after which the new sheet is added.

		16.2.6 Sheet
			class xlwings.Sheet(sheet=None, impl=None)

		    A sheet object is a member of the sheets collection:

		    >>> import xlwings as xw
		    >>> wb = xw.Book()
		    >>> wb.sheets[0]
		    <Sheet [Book1]Sheet1>
		    >>> wb.sheets['Sheet1']
		    <Sheet [Book1]Sheet1>
		    >>> wb.sheets.add()
		    <Sheet [Book1]Sheet2

		    activate()
		        Activates the Sheet and returns it.

		    api
		        Returns the native object (pywin32 or appscript obj) of the engine being used.


		    autofit(axis=None)

		        Autofits the width of either columns, rows or both on a whole Sheet.
		        Parameters:	axis (string, default None) –

		            To autofit rows, use one of the following: rows or r
		            To autofit columns, use one of the following: columns or c
		            To autofit rows and columns, provide no arguments

		        Examples

		        >>> import xlwings as xw
		        >>> wb = xw.Book()
		        >>> wb.sheets['Sheet1'].autofit('c')
		        >>> wb.sheets['Sheet1'].autofit('r')
		        >>> wb.sheets['Sheet1'].autofit()

		    book
		        Returns the Book of the specified Sheet. Read-only.

		    cells
		        Returns a Range object that represents all the cells on the Sheet 
		        (not just the cells that are currently in use).

		    charts
		        See Charts


		    clear()
		        Clears the content and formatting of the whole sheet.

		    clear_contents()
		        Clears the content of the whole sheet but leaves the formatting.

		    delete()
		        Deletes the Sheet.

		    index
		        Returns the index of the Sheet (1-based as in Excel).

		    name
		        Gets or sets the name of the Sheet.

		    names
		        Returns a names collection that represents all the sheet-specific 
		        names (names defined with the “SheetName!” prefix).

		    pictures
		        See Pictures


		    range(cell1, cell2=None)
		        Returns a Range object from the active sheet of the active book, see Range().

		    select()

		        Selects the Sheet. Select only works on the active book.

		    shapes
		        See Shapes


		16.2.7 Range

			class xlwings.Range(cell1=None, cell2=None, **options)
			    Returns a Range object that represents a cell or a range of cells.
			    Parameters:	
			        cell1 (str or tuple or Range) – Name of the range in the upper-left corner 
			        in A1 notation or as index-tuple or as name or as xw.Range object. It can 
			        also specify a range using the range operator (a colon), .e.g. ‘A1:B2’
			        cell2 (str or tuple or Range, default None) – Name of the range in the 
			        lower-right corner in A1 notation or as index-tuple or as name or as xw.Range object.

			    Examples

			    Active Sheet:
				    import xlwings as xw
				    xw.Range('A1')
				    xw.Range('A1:C3')
				    xw.Range((1,1))
				    xw.Range((1,1), (3,3)) # 可以采用坐标的形式，每一个坐标是一个tuple.
				    xw.Range('NamedRange')
				    xw.Range(xw.Range('A1'), xw.Range('B2')) # 也可以采用range的方式，指定左上与右下的方格range.

					Specific Sheet:
					xw.books['MyBook.xlsx'].sheets[0].range('A1')


			add_hyperlink(address, text_to_display=None, screen_tip=None)
			    Adds a hyperlink to the specified Range (single Cell)
			    Parameters:	

			        address (str) – The address of the hyperlink.
			        text_to_display (str, default None) – The text to be displayed for the hyperlink. 
			        Defaults to the hyperlink address.screen_tip (str, default None) – 
			        The screen tip to be displayed when the mouse pointer is paused over the hyperlink. 
			        Default is set to ‘<address> - Click once to follow. Click and hold to select this cell.’

				>>>sht.range("A1").add_hyperlink("www.baidu.com", "百度", "baidu")

			address
    			Returns a string value that represents the range reference. 
    			Use get_address() to be able to provide paramaters.

    			>>>sht.range("A1").get_address("B1")
				'$A$1'

			api
    			Returns the native object (pywin32 or appscript obj) of the engine being used.

			autofit()
			    Autofits the width and height of all cells in the range.
			        To autofit only the width of the columns use 	
			        	xw.Range('A1:B2').columns.autofit()
			        To autofit only the height of the rows use 
			        	xw.Range('A1:B2').rows.autofit()

			    >>>sht.ragne("A1").value = "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"
			    >>>sht.range("A1").columns.autofit()

			clear()
			    Clears the content and the formatting of a Range.
			    >>>sht.range("A1").clear()

			clear_contents()
			    Clears the content of a Range but leaves the formatting.
			    >>>sht.range("A2").clear_contents()

			color
			    Gets and sets the background color of the specified Range.

			    To set the color, either use an RGB tuple (0, 0, 0) or a color constant.
			    To remove the background, set the color to None, see Examples.
			    Returns:	RGB
			    Return type:	tuple

			    Examples
				    >>> import xlwings as xw
				    >>> wb = xw.Book()
				    >>> xw.Range('A1').color = (255,255,255)
				    >>> xw.Range('A2').color
				    (255, 255, 255)
				    >>> xw.Range('A2').color = None
				    >>> xw.Range('A2').color is None
				    True

			column
			    Returns the number of the first column in the in the specified range. Read-only.
			    Returns:	
			    Return type:	Integer
				>>> sht.range("C1:F3").column
				3

			column_width
			    Gets or sets the width, in characters, of a Range. One unit of column width is equal 
			    to the width of one character in the Normal style. For proportional fonts, 
			    the width of the character 0 (zero) is used.
			    If all columns in the Range have the same width, returns the width. 
			    If columns in the Range have different widths, returns None.
			    column_width must be in the range: 0 <= column_width <= 255

			    Note: If the Range is outside the used range of the Worksheet, 
			    and columns in the Range have different widths, returns the width of the first column.
			    Returns:	
			    Return type:	float
			    >>>sht.range("A1").column_width
			    8.38

			columns
			    Returns a RangeColumns object that represents the columns in the specified range.
			    >>>sht.range("A1").columns
				RangeColumns(<Range [abc.xlsx]Sheet1!$A$1>)

			count
			    Returns the number of cells.
			    >>>sht.range("A1").count
				1
				>>> sht.range("A1:C5").count
				15

			current_region
			    This property returns a Range object representing a range bounded by 
			    (but not including) any combination of blank rows and blank columns 
			    or the edges of the worksheet. It corresponds to Ctrl-* on Windows and Shift-Ctrl-Space on Mac.
			    Returns:	
			    Return type:	Range object
			    返回由空行和空列或者worksheet边界确定的连续Range的对象
			    对于D5->F6这样的区域
				>>> sht.range("D5").current_region.value
				[[10.0, 20.0, 30.0], [21.0, 11.0, 31.0]]
				>>> sht.range("E5").current_region.value
				[[10.0, 20.0, 30.0], [21.0, 11.0, 31.0]]
				>>> sht.range("F6").current_region.value
				[[10.0, 20.0, 30.0], [21.0, 11.0, 31.0]]

			end(direction)
			    Returns a Range object that represents the cell at the end of the region that contains 
			    the source range. Equivalent to pressing Ctrl+Up, Ctrl+down, Ctrl+left, or Ctrl+right.
			    Parameters:	direction (One of 'up', 'down', 'right', 'left') –

			    Examples
			    >>> import xlwings as xw
			    >>> wb = xw.Book()
			    >>> xw.Range('A1:B2').value = 1
			    >>> xw.Range('A1').end('down')
			    <Range [Book1]Sheet1!$A$2>
			    >>> xw.Range('B2').end('right')
			    <Range [Book1]Sheet1!$B$2>

				>>> sht.range("D5").end("right").value
				30.0
				>>> sht.range("D5").end("down").value
				21.0

			expand(mode='table')
			    Expands the range according to the mode provided. Ignores empty top-left cells
			     	(unlike Range.end()).
			    Parameters:	mode (str, default 'table') – One of 'table' (=down and right), 'down', 'right'.
			    Returns:	只有三种模式，table, down和right三种扩展方式，默认为table方式
			    Return type:	Range

			    Examples
			    >>> import xlwings as xw
			    >>> wb = xw.Book()
			    >>> xw.Range('A1').value = [[None, 1], [2, 3]]
			    >>> xw.Range('A1').expand().address
			    $A$1:$B$2
			    >>> xw.Range('A1').expand('right').address
			    $A$1:$B$1

			    >>>sht.range("A1").value = [[3,4,5], [6,7,8]]
				>>>A = sht.range("A1").expand()
				>>>type(A)
				<class 'xlwings.main.Range'>
				>>> A.shape
				(2, 3)
				>>> B=sht.range("A1")
				>>> B.shape
				(1, 1)
				>>> C=sht.range("A1").expand("right")
				>>> C.shape
				(1, 3)

			formula
			    Gets or sets the formula for the given Range.
			    >>>sht.range("A1").formula="=SUM(B1:B5)"
			    	个人感觉，这个等价于直接往cell中写入公式的字符串呀。
			    >>>sht.range("A2").value ="=SUM(B1:B5)"

			formula_array
			    Gets or sets an array formula for the given Range.
				>>>sht.range("A1:C5").formula_array="=3"
				>>>sht.range("A1:C5").value="=3"
				>>>sht.range("A1:C5").value="=6"
				没试出来怎么用
				>>>sht.range("A12:C12").formula_array="=SUM(E4G4:E5G5)" 这种用法错误 


			get_address(row_absolute=True, column_absolute=True, include_sheetname=False, 
						external=False)
			    Returns the address of the range in the specified format. address can be used 
			    instead if none of the defaults need to be changed.
			    Parameters:	
			        row_absolute (bool, default True) – Set to True to return the row part of 
			        the reference as an absolute reference. column_absolute (bool, default True) 
			        – Set to True to return the column part of the reference as an absolute reference.
			        include_sheetname (bool, default False) – Set to True to include the Sheet name 
			        in the address. Ignored if external=True.external (bool, default False) – Set to 
			        True to return an external reference with workbook and worksheet name.

			    Returns:	

			    Return type:	
			    str

			    Examples
			    >>>import xlwings as xw
			    >>>wb = xw.Book()
			    >>>xw.Range((1,1)).get_address()
			    '$A$1'
			    >>>xw.Range((1,1)).get_address(False, False)
			    'A1'
			    >>>xw.Range((1,1), (3,3)).get_address(True, False, True)
			    'Sheet1!A$1:C$3'
			    >>>xw.Range((1,1), (3,3)).get_address(True, False, external=True)
			    '[Book1]Sheet1!A$1:C$3'

			height
			    Returns the height, in points, of a Range. Read-only.
			    Returns:	
			    Return type:	float
			    >>>sht.range("A1").height
				14.25

			hyperlink
			    Returns the hyperlink address of the specified Range (single Cell only)
			    add_hyperlink(address, text_to_display=None, screen_tip=None)
			    Examples:
			    >>>import xlwings as xw
			    >>>wb = xw.Book()
			    >>>xw.Range('A1').value
			    'www.xlwings.org'
			    >>>xw.Range('A1').hyperlink
			    'http://www.xlwings.org'

			    >>>sht.range("A1").add_hyperlink("www.baidu.com", "百度", "baidu")
				>>>sht.range("A1").value
				'百度'
				>>>sht.range("A1").hyperlink
				'http://www.baidu.com'

			last_cell
			    Returns the bottom right cell of the specified range. Read-only.
			    Returns:	
			    Return type:	Range
			    Example
			    >>>import xlwings as xw
			    >>>wb = xw.Book()
			    >>>rng = xw.Range('A1:E4')
			    >>>rng.last_cell.row, rng.last_cell.column
			    (4, 5)

			left
			    Returns the distance, in points, from the left edge of column A 
			    to the left edge of the range. Read-only.
			    Returns:	
			    Return type:	float
			    >>>sht.range("C1:F1").value = 5
				>>>sht.range("C1:F1").left
				108.0
				>>>sht.range("A1").width
				54.0
				>>>sht.range("A1:B1").width
				108.0

			name
			    Sets or gets the name of a Range.
			    >>>sht.range("A1:B1").name = "Excel"
				>>>sht.range("A1:B1").name
				<Name 'Excel': =Sheet1!$A$1:$B$1>

			number_format
			    Gets and sets the number_format of a Range.
			    Examples
			    >>>import xlwings as xw
			    >>>wb = xw.Book()
			    >>>xw.Range('A1').number_format
			    'General'
			    >>>xw.Range('A1:C3').number_format = '0.00%'
			    >>>xw.Range('A1:C3').number_format
			    '0.00%'

			    >>>sht.range("A1").number_format = "0.00%"			
				>>>sht.range("A1").value = 0.1532
				15.32%

			offset(row_offset=0, column_offset=0)
			    Returns a Range object that represents a Range that’s offset from the specified range.
			    Returns:	Range object
			    Return type:	Range
			    >>>sht.range("A1").offset(3,4).value = 10
			    将10写到了E4的位置，也就是(row=1+3, col=1+4)

			options(convert=None, **options)
			    Allows you to set a converter and their options. Converters define how Excel Ranges 
			    and their values are being converted both during reading and writing operations. 
			    If no explicit converter is specified, the base converter is being applied, 
			    see Converters and Options.

			    Parameters:	
			    convert (object, default None) – A converter, e.g. dict, np.array, pd.DataFrame, 
			    pd.Series, defaults to default converter

			    Keyword Arguments:  	
			        ndim (int, default None) – number of dimensions
			        numbers (type, default None) – type of numbers, e.g. int
			        dates (type, default None) – e.g. datetime.date defaults to datetime.datetime
			        empty (object, default None) – transformation of empty cells
			        transpose (Boolean, default False) – transpose values
			        expand (str, default None) –

			        One of 'table', 'down', 'right'
			        => For converter-specific options, see Converters and Options.

			    Returns:	
			    Return type:	
			    Range object

			raw_value
			    Gets and sets the values directly as delivered from/accepted by the engine that 
			    is being used (pywin32 or appscript) without going through any of xlwings’ data 
			    cleaning/converting. This can be helpful if speed is an issue but naturally will
			    be engine specific, i.e. might remove the cross-platform compatibility.

			resize(row_size=None, column_size=None)
			    Resizes the specified Range
			    Parameters:	

			        row_size (int > 0) – The number of rows in the new range (if None, the number of rows in the range is unchanged).
			        column_size (int > 0) – The number of columns in the new range (if None, the number of columns in the range is unchanged).

			    Returns:	

			    Range object
			    Return type:	

			    Range

			    >>>a = sht.range("A1:C2")
			    >>>a.shape
				(2, 3)
				>>>b = a.resize(4, 8)
				>>>b.shape
				(4, 8)

			row
			    Returns the number of the first row in the specified range. Read-only.
			    Returns:	
			    Return type:	Integer
			    >>>c = sht.range("C1:F2")
				>>>c.row
				1
			    >>>c = sht.range("C3:F5")
				>>>c.row
				3

			row_height
			    Gets or sets the height, in points, of a Range. If all rows in the Range 
			    have the same height, returns the height. If rows in the Range have different heights, returns None.

			    row_height must be in the range: 0 <= row_height <= 409.5

			    Note: If the Range is outside the used range of the Worksheet, and rows in the Range have 
			    different heights, returns the height of the first row.
			    Returns:	
			    Return type:	float

			rows
			    Returns a RangeRows object that represents the rows in the specified range.

			select()
			    Selects the range. Select only works on the active book.
			    不知道怎么用，有什么用呀。

			shape
			    Tuple of Range dimensions.

			sheet
			    Returns the Sheet object to which the Range belongs.
			    >>>c.sheet
				<Sheet [abc.xlsx]Sheet1>

			size
			    Number of elements in the Range.
			    >>>a = sht.range("A1:C2")
				>>> a.size
				6

			top
			    Returns the distance, in points, from the top edge of row 1 to the top edge of the range. Read-only.
			    Returns:	
			    Return type:	float
			    >>>c.top
				28.5

			value
			    Gets and sets the values for the given Range.
			    Returns:	object
			    Return type:	returned object depends on the converter being used, see xlwings.Range.options()
			    >>>c.value = 10

			width
			    Returns the width, in points, of a Range. Read-only.
			    Returns:	
			    Return type:	float

		16.2.8 RangeRows

			class xlwings.RangeRows(rng)
			    Represents the rows of a range. Do not construct this class directly, use Range.rows instead.

			    Example:
			    import xlwings as xw
			    rng = xw.Range('A1:C4')
			    assert len(rng.rows) == 4  # or rng.rows.count
			    rng.rows[0].value = 'a'
			    assert rng.rows[2] == xw.Range('A3:C3')
			    assert rng.rows(2) == xw.Range('A2:C2')
			    for r in rng.rows:
			        print(r.address)
			    autofit()
			        Autofits the height of the rows.
			    count
			        Returns the number of rows.

				>>>c
				<Range [abc.xlsx]Sheet1!$C$3:$F$5>
				>>>b = c.rows
				>>>b[0]
				<Range [abc.xlsx]Sheet1!$C$3:$F$3>
				>>>b[1]
				<Range [abc.xlsx]Sheet1!$C$4:$F$4>
				>>>b[2]
				<Range [abc.xlsx]Sheet1!$C$5:$F$5>
				>>>len(b)
				3

		16.2.8 Shapes

			class xlwings.main.Shapes(impl)

			    A collection of all shape objects on the specified sheet:

			    >>> import xlwings as xw
			    >>> xw.books['Book1'].sheets[0].shapes
			    Shapes([<Shape 'Oval 1' in <Sheet [Book1]Sheet1>>, <Shape 'Rectangle 1' in <Sheet [Book1]Sheet1>>])

			    api
			        Returns the native object (pywin32 or appscript obj) of the engine being used.
			    count
			        Returns the number of objects in the collection.

		16.2.9 Shape (循环定义啊?没搞明白shape是什么东东)

			class xlwings.Shape(*args, **options)
			    The shape object is a member of the shapes collection:

			    >>> import xlwings as xw
			    >>> sht = xw.books['Book1'].sheets[0]
			    >>> sht.shapes[0]  # or sht.shapes['ShapeName']
			    <Shape 'Rectangle 1' in <Sheet [Book1]Sheet1>>

			    activate()

			        Activates the shape.

			    delete()

			        Deletes the shape.

			    height

			        Returns or sets the number of points that represent the height of the shape.

			    left

			        Returns or sets the number of points that represent the horizontal position of the shape.

			    name

			        Returns or sets the name of the shape.

			    parent

			        Returns the parent of the shape.

			    top

			        Returns or sets the number of points that represent the vertical position of the shape.

			    type

			        Returns the type of the shape.

			    width

			        Returns or sets the number of points that represent the width of the shape.

		16.3.0 Charts

			class xlwings.main.Charts(impl)
				charts作为sht的默认子象存在，要想创建chart，用sht.charts.add()来添加chart,然后
				用chart对象的属性和方法来设置相关的属性值。

			    A collection of all chart objects on the specified sheet:

			    >>> import xlwings as xw
			    >>> xw.books['Book1'].sheets[0].charts
			    Charts([<Chart 'Chart 1' in <Sheet [Book1]Sheet1>>, <Chart 'Chart 1' in <Sheet [Book1]Sheet1>>])

			    add(left=0, top=0, width=355, height=211)

			        Creates a new chart on the specified sheet.
			        Parameters:	

			            left (float, default 0) – left position in points
			            top (float, default 0) – top position in points
			            width (float, default 355) – width in points
			            height (float, default 211) – height in points

			        Returns:	

			        Return type:	

			        Chart

			        Examples

			        >>> import xlwings as xw
			        >>> sht = xw.Book().sheets[0]
			        >>> sht.range('A1').value = [['Foo1', 'Foo2'], [1, 2]]
			        >>> chart = sht.charts.add()
			        >>> chart.set_source_data(sht.range('A1').expand())
			        >>> chart.chart_type = 'line'
			        >>> chart.name
			        'Chart1'

			    api

			        Returns the native object (pywin32 or appscript obj) of the engine being used.

			    count

			        Returns the number of objects in the collection.

		16.3.1 Chart

			class xlwings.Chart(name_or_index=None, impl=None)

			    The chart object is a member of the charts collection:

			    >>> import xlwings as xw
			    >>> sht = xw.books['Book1'].sheets[0]
			    >>> sht.charts[0]  # or sht.charts['ChartName']
			    <Chart 'Chart 1' in <Sheet [Book1]Sheet1>>

			    api

			        Returns the native object (pywin32 or appscript obj) of the engine being used.

			    chart_type

			        Returns and sets the chart type of the chart.也没说清楚都有什么类型

			    delete()

			        Deletes the chart.

			    height

			        Returns or sets the number of points that represent the height of the chart.

			    left

			        Returns or sets the number of points that represent the horizontal position of the chart.

			    name

			        Returns or sets the name of the chart.

			    parent

			        Returns the parent of the chart.

			        New in version 0.9.0.

			    set_source_data(source)

			        Sets the source data range for the chart.
			        Parameters:	source (Range) – Range object, e.g. xw.books['Book1'].sheets[0].range('A1')

			    top

			        Returns or sets the number of points that represent the vertical position of the chart.

			    width

			        Returns or sets the number of points that represent the width of the chart.


		16.3.2 Pictures

			class xlwings.main.Pictures(impl)

			    A collection of all picture objects on the specified sheet:

			    >>> import xlwings as xw
			    >>> xw.books['Book1'].sheets[0].pictures
			    Pictures([<Picture 'Picture 1' in <Sheet [Book1]Sheet1>>, <Picture 'Picture 2' 
			    in <Sheet [Book1]Sheet1>>])

			    add(image, link_to_file=False, save_with_document=True, left=0, top=0, width=None, 
			    height=None, name=None, update=False)

			        Adds a picture to the specified sheet.
			        Parameters:	

			            image (str or matplotlib.figure.Figure) – Either a filepath or a Matplotlib figure object.
			            left (float, default 0) – Left position in points.
			            top (float, default 0) – Top position in points.
			            width (float, default None) – Width in points. If PIL/Pillow is installed, it defaults to 
			            the width of the picture. Otherwise it defaults to 100 points.
			            height (float, default None) – Height in points. If PIL/Pillow is installed, it defaults 
			            to the height of the picture. Otherwise it defaults to 100 points.
			            name (str, default None) – Excel picture name. Defaults to Excel standard name if not 
			            provided, e.g. ‘Picture 1’.update (bool, default False) – Replace an existing
			            picture with the same name. Requires name to be set.

			        Returns:	

			        Return type:	

			        Picture

			        Examples

			            Picture

			        >>> import xlwings as xw
			        >>> sht = xw.Book().sheets[0]
			        >>> sht.pictures.add(r'C:\path\to\file.jpg')
			        <Picture 'Picture 1' in <Sheet [Book1]Sheet1>>
			        如果路径设置为"D:/1.jpg"的形式，就会报错
			        >>> sht.pictures.add("D:\\1.jpg")
					<Picture 'Picture 2' in <Sheet [abc.xlsx]Sheet1>>

			            Matplotlib

			        >>> import matplotlib.pyplot as plt
			        >>> fig = plt.figure()
			        >>> plt.plot([1, 2, 3, 4, 5])
			        >>> sht.pictures.add(fig, name='MyPlot', update=True)
			        <Picture 'MyPlot' in <Sheet [Book1]Sheet1>>

			    api

			        Returns the native object (pywin32 or appscript obj) of the engine being used.

			    count

			        Returns the number of objects in the collection.

		16.3.3 Picture

			class xlwings.Picture(impl=None)

			    The picture object is a member of the pictures collection:

			    >>> import xlwings as xw
			    >>> sht = xw.books['Book1'].sheets[0]
			    >>> sht.pictures[0]  # or sht.charts['PictureName']
			    <Picture 'Picture 1' in <Sheet [Book1]Sheet1>>

			    api

			        Returns the native object (pywin32 or appscript obj) of the engine being used.

			    delete()

			        Deletes the picture.

			    height

			        Returns or sets the number of points that represent the height of the picture.

			    left

			        Returns or sets the number of points that represent the horizontal position of the picture.

			    name

			        Returns or sets the name of the picture.

			    parent

			        Returns the parent of the picture.

			    top

			        Returns or sets the number of points that represent the vertical position of the picture.

			    update(image)

			        Replaces an existing picture with a new one, taking over the attributes of the existing picture.
			        Parameters:	image (str or matplotlib.figure.Figure) – Either a filepath or a Matplotlib figure object.

			    width

			        Returns or sets the number of points that represent the width of the picture.

		16.3.4 Names

			class xlwings.main.Names(impl)

			    A collection of all name objects in the workbook:

			    >>> import xlwings as xw
			    >>> sht = xw.books['Book1'].sheets[0]
			    >>> sht.names
			    [<Name 'MyName': =Sheet1!$A$3>]

			    add(name, refers_to)

			        Defines a new name for a range of cells.
			        Parameters:	

			            name (str) – Specifies the text to use as the name. Names cannot include spaces and cannot be formatted as cell references.
			            refers_to (str) – Describes what the name refers to, in English, using A1-style notation.

			        Returns:	

			        Return type:	

			        Name

			    api

			        Returns the native object (pywin32 or appscript obj) of the engine being used.

			    count

			        Returns the number of objects in the collection.

			    >>> sht.names.add("baidu", "A1")
				<Name 'Sheet1!baidu': ="A1">
				>>> sht.names
				[<Name 'Sheet1!baidu': ="A1">]


		16.3.5 Name

			class xlwings.Name(impl)

			    The name object is a member of the names collection:

			    >>> import xlwings as xw
			    >>> sht = xw.books['Book1'].sheets[0]
			    >>> sht.names[0]  # or sht.names['MyName']
			    <Name 'MyName': =Sheet1!$A$3>

			    api

			        Returns the native object (pywin32 or appscript obj) of the engine being used.

			    delete()

			        Deletes the name.

			    name

			        Returns or sets the name of the name object.

			    refers_to

			        Returns or sets the formula that the name is defined to refer to, 
			        in A1-style notation, beginning with an equal sign.

			    refers_to_range

			        Returns the Range object referred to by a Name object.

	16.4 UDF decorators

		xlwings.func(category="xlwings", volatile=False, call_in_wizard=True)

		    Functions decorated with xlwings.func will be imported as Function to 
		    Excel when running “Import Python UDFs”.

		    category : int or str, default “xlwings”

		        1-14 represent built-in categories, for user-defined categories use strings

		    volatile : bool, default False

		        Marks a user-defined function as volatile. A volatile function must be recalculated 
		        whenever calculation occurs in any cells on the worksheet. A nonvolatile function 
		        is recalculated only when the input variables change. This method has no effect 
		        if it’s not inside a user-defined function used to calculate a worksheet cell.

		    call_in_wizard : bool, default True

		        Set to False to suppress the function call in the function wizard.

		xlwings.sub()

		    Functions decorated with xlwings.sub will be imported as Sub 
		    (i.e. macro) to Excel when running “Import Python UDFs”.

		xlwings.arg(arg, convert=None, **options)

		    Apply converters and options to arguments, see also Range.options().

		    Examples:

		    Convert x into a 2-dimensional numpy array:

		    import xlwings as xw
		    import numpy as np

		    @xw.func
		    @xw.arg('x', np.array, ndim=2)
		    def add_one(x):
		        return x + 1

		xlwings.ret(convert=None, **options)

		    Apply converters and options to return values, see also Range.options().

		    Examples

		        Suppress the index and header of a returned DataFrame:

		    import pandas as pd

		    @xw.func
		    @xw.ret(index=False, header=False)
		    def get_dataframe(n, m):
		        return pd.DataFrame(np.arange(n * m).reshape((n, m)))

		        Dynamic array:

		    expand='table' turns the UDF into a dynamic array. Currently you must not use 
		    volatile functions as arguments of a dynamic array, e.g. you cannot use =TODAY() 
		    as part of a dynamic array. Also note that a dynamic array needs an empty row 
		    and column at the bottom and to the right and will overwrite existing data without warning.

		    Unlike standard Excel arrays, dynamic arrays are being used from a single cell like 
		    a standard function and auto-expand depending on the dimensions of the returned array:

		    import xlwings as xw
		    import numpy as np

		    @xw.func
		    @xw.ret(expand='table')
		    def dynamic_array(n, m):
		        return np.arange(n * m).reshape((n, m))