# 1. 目标

Target

    At least one of these options has to be provided to define the target(s)
    
    -d DIRECT           Connection string for direct database Connection 	
    					直接连接数据库
    -u URL, --url=URL   Target URL (e.g. "http://www.site.com/vuln.php?id=1")	
    					目标url
    -l LOGFILE          Parse target(s) from Burp or WebScarab proxy log file 	
    					解析来自burp或webscarab代理的日志
    -x SITEMAPURL       Parse target(s) from remote sitemap(.xml) file 	
    					解析远程站点目标
    -m BULKFILE         Scan multiple targets given in a textual file 	
    					扫描给出的文件，进行多目标扫描，批量检测注入
    -r REQUESTFILE      Load HTTP request from a file 	
    					从文件中读取http请求
    -g GOOGLEDORK       Process Google dork results as target URLs 	
    					将Google dork结果作为目标网址处理
    -c CONFIGFILE       Load options from a configuration INI file 	
    					从ini配置文件中读取选项