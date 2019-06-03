# 第一章

# sqlmap目前支持MySQL，Oracle，PostgreSQL，Microsoft SQL Server，Microsoft Access，IBM DB2，SQLite，Sybase和SAP MaxDB等数据库类型。

# 采用五种独特的SQL注入技术，分别是：

	1. 基于布尔(bool)的盲注，即可以根据返回页面判断条件真假的注入
	2. 基于时间(time)的盲注，即不能根据页面返回内容判断任何信息，用条件语句查看时间延迟，语句是否执行（即页面返回时间是否增加）来判断
	4. 基于报错(error)注入，即页面会返回错误信息，或者把注入的语句的结果直接返回在页面上
	5. 联合查询(union)注入，可以使用union的情况下的注入
	6. 堆查询注入，可以同时执行多条语句的执行时的注入

# sqlmap功能

	开源sql注入漏洞检测、利用工具
	检测动态页面中get/post参数、cookie、http头
	数据榨取
	文件系统访问
	操作系统命令执行
	引擎强大、特性丰富
	XSS漏洞检测