# 14. 通用

General

    These options can be used to set some general working parameters
    这些选项可用于设置一些常规工作参数
    
    -s SESSIONFILE      Load session from a stored (.sqlite) file
    					从存储的（.sqlite）文件加载session
    -t TRAFFICFILE      Log all HTTP traffic into a textual file
    					将所有HTTP流量记录到文本文件中
    --batch             Never ask for user input, use the default behavior
    					永远不要求用户输入，使用默认行为
    --binary-fields=..  Result fields having binary values (e.g. "digest")
    					具有二进制值的结果字段（例如“摘要”）
    --check-internet    Check Internet connection before assessing the target
    					在评估目标之前检查Internet连接
    --crawl=CRAWLDEPTH  Crawl the website starting from the target URL
    					从目标网址开始抓取网站
    --crawl-exclude=..  Regexp to exclude pages from crawling (e.g. "logout")
    					正则表达式从抓取中排除页面（例如“注销”）
    --csv-del=CSVDEL    Delimiting character used in CSV output (default ",")
    					分隔CSV输出中使用的字符（默认为“，”）
    --charset=CHARSET   Blind SQL injection charset (e.g. "0123456789abcdef")
    					盲SQL注入字符集（例如“0123456789abcdef”）
    --dump-format=DU..  Format of dumped data (CSV (default), HTML or SQLITE)
    					转储数据的格式（CSV（默认），HTML或SQLITE）
    --encoding=ENCOD..  Character encoding used for data retrieval (e.g. GBK)
    					用于数据检索的字符编码（例如GBK）
    --eta               Display for each output the estimated time of arrival
    					显示每个输出的预计到达时间
    --flush-session     Flush session files for current target
    					刷新当前目标的会话文件
    --forms             Parse and test forms on target URL
    					在目标URL上解析和测试表单
    --fresh-queries     Ignore query results stored in session file
    					忽略存储在会话文件中的查询结果
    --har=HARFILE       Log all HTTP traffic into a HAR file
    					将所有HTTP流量记录到HAR文件中
    --hex               Use hex conversion during data retrieval
    					在数据检索期间使用十六进制转
    --output-dir=OUT..  Custom output directory path
    					自定义输出目录路径
    --parse-errors      Parse and display DBMS error messages from responses
    					从响应中解析并显示DBMS错误消息
    --preprocess=PRE..  Use given script(s) for preprocessing of response data
    					使用给定的脚本来预处理响应数据
    --repair            Redump entries having unknown character marker (?)
    					具有未知字符标记的Redump条目（？）
    --save=SAVECONFIG   Save options to a configuration INI file
    					将选项保存到配置INI文件
    --scope=SCOPE       Regexp to filter targets from provided proxy log
    					正则表达式从提供的代理日志中过滤目标
    --test-filter=TE..  Select tests by payloads and/or titles (e.g. ROW)
    					按有效负载和/或标题选择测试（例如ROW）
    --test-skip=TEST..  Skip tests by payloads and/or titles (e.g. BENCHMARK)
    					按有效载荷和/或标题跳过测试（例如BENCHMARK）
    --update            Update sqlmap