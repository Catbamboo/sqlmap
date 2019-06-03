
# 命令介绍

## 目标：Target

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

请求包：Request

    These options can be used to specify how to connect to the target URL
    如何连接目标url
    
    --method=METHOD     Force usage of given HTTP method (e.g. PUT)  
    					put\post\get...
    --data=DATA         Data string to be sent through POST (e.g. "id=1")	
    					post传参
    --param-del=PARA..  Character used for splitting parameter values (e.g. &) 
    					指定分割参数的字符
    --cookie=COOKIE     HTTP Cookie header value (e.g. "PHPSESSID=a8d127e..") 	
    					cookie传参
    --cookie-del=COO..  Character used for splitting cookie values (e.g. ;) 	
    					指定分割cookie参数的字符
    --load-cookies=L..  File containing cookies in Netscape/wget format 	
    					包含Netscape / wget格式的Cookie的文件
    --drop-set-cookie   Ignore Set-Cookie header from response 	
    					忽视响应请求包的set-cookie
    --user-agent=AGENT  HTTP User-Agent header value 
    --random-agent      Use randomly selected HTTP User-Agent header value 	
    					随机User-Agent
    --host=HOST         HTTP Host header value
    --referer=REFERER   HTTP Referer header value
    -H HEADER, --hea..  Extra header (e.g. "X-Forwarded-For: 127.0.0.1")
    --headers=HEADERS   Extra headers (e.g. "Accept-Language: fr\nETag: 123")
    --auth-type=AUTH..  HTTP authentication type (Basic, Digest, NTLM or PKI) 	
    					HTTP身份验证类型
    --auth-cred=AUTH..  HTTP authentication credentials (name:password) 	
    					HTTP身份验证凭据
    --auth-file=AUTH..  HTTP authentication PEM cert/private key file 	
    					HTTP身份验证PEM证书/私钥文件
    --ignore-code=IG..  Ignore (problematic) HTTP error code (e.g. 401)
    					忽略（有问题的）HTTP错误代码
    --ignore-proxy      Ignore system default proxy settings
    					忽略系统默认代理设置
    --ignore-redirects  Ignore redirection attempts
    					忽略重定向尝试
    --ignore-timeouts   Ignore connection timeouts
    					忽略连接超时
    --proxy=PROXY       Use a proxy to connect to the target URL
    					使用代理连接到目标URL
    --proxy-cred=PRO..  Proxy authentication credentials (name:password)  
    					代理身份验证凭据
    --proxy-file=PRO..  Load proxy list from a file 	
    					从文件中读取代理列表
    --tor               Use Tor anonymity network 	
    					使用tor匿名网络
    --tor-port=TORPORT  Set Tor proxy port other than default 	
    					设置tor代理端口
    --tor-type=TORTYPE  Set Tor proxy type (HTTP, SOCKS4 or SOCKS5 (default)) 	
    					设置tor代理类型
    --check-tor         Check to see if Tor is used properly 	
    					检测tor是否正确使用
    --delay=DELAY       Delay in seconds between each HTTP request 	
    					每次请求延时设置
    --timeout=TIMEOUT   Seconds to wait before timeout connection (default 30) 	
    					等待延时秒数设置
    --retries=RETRIES   Retries when the connection timeouts (default 3) 	
    					连接超时时重新尝试次数
    --randomize=RPARAM  Randomly change value for given parameter(s) 	
    					随机更改给定参数的值
    --safe-url=SAFEURL  URL address to visit frequently during testing 	
    					在测试期间经常访问的地址
    --safe-post=SAFE..  POST data to send to a safe URL 	
    					发送POST数据到一个安全的url
    --safe-req=SAFER..  Load safe HTTP request from a file 		
    					从文件中读取http request请求包
    --safe-freq=SAFE..  Test requests between two visits to a given safe URL  
    					两次访问之间测试请求，给出安全的URL
    --skip-urlencode    Skip URL encoding of payload data  
    					跳过有效负载数据的URL编码
    --csrf-token=CSR..  Parameter used to hold anti-CSRF token 	
    					用于保存反CSRF令牌的参数
    --csrf-url=CSRFURL  URL address to visit for extraction of anti-CSRF token
    --force-ssl         Force usage of SSL/HTTPS 	
    					强制使用SSL / HTTPS
    --chunked           Use HTTP chunked transfer encoded (POST) requests 	
    					使用HTTP分块传输编码（POST）请求
    --hpp               Use HTTP parameter pollution method 	
    					使用http参数污染
    --eval=EVALCODE     Evaluate provided Python code before the request (e.g.
                        "import hashlib;id2=hashlib.md5(id).hexdigest()") 	在请求之前评估提供的Python代码

优化：Optimization

    These options can be used to optimize the performance of sqlmap
    优化sqlmap性能
    
    -o                  Turn on all optimization switches   
    					打开所有优化开关
    --predict-output    Predict common queries output 	
    					预测常见查询输出
    --keep-alive        Use persistent HTTP(s) connections 	
    					使用持久性HTTP（s）连接
    --null-connection   Retrieve page length without actual HTTP response body 		
    					检索页面长度而不使用实际的HTTP响应主体
    --threads=THREADS   Max number of concurrent HTTP(s) requests (default 1)		
    					最大并发HTTP请求数（默认值为1）

注入：Injection

    These options can be used to specify which parameters to test for, provide custom injection payloads and optional tampering scripts
    这些选项可用于指定要测试的参数，以提供自定义注入有效负载和可选的篡改脚本
    
    -p TESTPARAMETER    Testable parameter(s) 	
    					可测试参数
    --skip=SKIP         Skip testing for given parameter(s) 	
    					跳过给定参数的测试
    --skip-static       Skip testing parameters that not appear to be dynamic 	
    					跳过看似不动态的测试参数
    --param-exclude=..  Regexp to exclude parameters from testing (e.g. "ses") 	
    					利用正则表达式从测试中排除参数
    --dbms=DBMS         Force back-end DBMS to provided value 	
    					强制后端DBMS提供值
    --dbms-cred=DBMS..  DBMS authentication credentials (user:password) 	
    					DBMS身份验证凭据
    --os=OS             Force back-end DBMS operating system to provided value
    					强制后端DBMS操作系统提供值
    --invalid-bignum    Use big numbers for invalidating values
    					使用大数字表示值无效
    --invalid-logical   Use logical operations for invalidating values
    					使用逻辑运算使值无效
    --invalid-string    Use random strings for invalidating values
    					使用随机字符串使值无效
    --no-cast           Turn off payload casting mechanism
    					关闭有效负载铸造机制
    --no-escape         Turn off string escaping mechanism
    					关闭字符串转义机制
    --prefix=PREFIX     Injection payload prefix string
    					注入有效负载字符串前缀
    --suffix=SUFFIX     Injection payload suffix string
    					注入有效负载字符串后缀
    --tamper=TAMPER     Use given script(s) for tampering injection data
    					使用给定的脚本来修改注入数据

测试：Detection

    These options can be used to customize the detection phase
    这些选项可用于自定义检测阶段
    
    --level=LEVEL       Level of tests to perform (1-5, default 1)
    					要执行的测试级别
    --risk=RISK         Risk of tests to perform (1-3, default 1)
    					执行测试的风险
    --string=STRING     String to match when query is evaluated to True
    					查询计算为True时要匹配的字符串
    --not-string=NOT..  String to match when query is evaluated to False
    					查询计算为False时要匹配的字符串
    --regexp=REGEXP     Regexp to match when query is evaluated to True
    					当查询被评估为True时匹配的正则表达式
    --code=CODE         HTTP code to match when query is evaluated to True
    					查询评估为True时要匹配的HTTP代码
    --text-only         Compare pages based only on the textual content
    					仅根据文本内容比较页面
    --titles            Compare pages based only on their titles
    					仅根据标题比较页面

注入技巧：Techniques

    These options can be used to tweak testing of specific SQL injection techniques
    这些选项可用于调整特定SQL注入的测试技术
    
    --technique=TECH    SQL injection techniques to use (default "BEUSTQ")
    					sql注入技术：
    					B：基于布尔的盲SQL注入
    					E：基于错误的SQL注入
    					U：UNION查询SQL注入
    					S：Stacked查询SQL注入
    					T：基于时间的盲SQL注入
    --time-sec=TIMESEC  Seconds to delay the DBMS response (default 5)
    					数据库响应延时时长/秒
    --union-cols=UCOLS  Range of columns to test for UNION query SQL injection
    					union联合查询sql注入columns范围
    --union-char=UCHAR  Character to use for bruteforcing number of columns
    					用于暴力猜解列数的字符
    --union-from=UFROM  Table to use in FROM part of UNION query SQL injection
    					设置联合查询from处的表
    --dns-domain=DNS..  Domain name used for DNS exfiltration attack
    					用于DNS渗透攻击的域名
    --second-url=SEC..  Resulting page URL searched for second-order response
    					设置二阶响应的结果显示页面的 URL（该设置用于二阶SQL注入）
    --second-req=SEC..  Load second-order HTTP request from file
    					从文件中加载二阶HTTP请求

指纹：Fingerprint

    -f, --fingerprint   Perform an extensive DBMS version fingerprint
    					执行广泛的DBMS版本指纹

枚举：Enumeration

    These options can be used to enumerate the back-end database management system information, structure and data contained in the tables. Moreover you can run your own SQL statements
    这些选项可用于枚举表中包含的后端数据库管理系统信息，结构和数据。 此外，您可以运行自己的SQL语句
    
    -a, --all           Retrieve everything
    					检索一切
    -b, --banner        Retrieve DBMS banner
    					检索数据库版本
    --current-user      Retrieve DBMS current user
    					数据库当前用户
    --current-db        Retrieve DBMS current database
    					当前数据库名
    --hostname          Retrieve DBMS server hostname
    					当前数据库服务器主机名
    --is-dba            Detect if the DBMS current user is DBA
    					检测DBMS当前用户是否为DBA
    --users             Enumerate DBMS users
    					枚举DBMS所有用户
    --passwords         Enumerate DBMS users password hashes
    					枚举数据库所有用户密码hash值
    --privileges        Enumerate DBMS users privileges
    					枚举DBMS用户权限
    --roles             Enumerate DBMS users roles
    					枚举数据库用户角色
    --dbs               Enumerate DBMS databases
    					枚举所有数据库名
    --tables            Enumerate DBMS database tables
    					枚举数据库表
    --columns           Enumerate DBMS database table columns
    					枚举数据库中列名	
    --schema            Enumerate DBMS schema
    					枚举DBMS架构
    --count             Retrieve number of entries for table(s)
    					检索表的条目数
    --dump              Dump DBMS database table entries
    					转储DBMS数据库表条目
    --dump-all          Dump all DBMS databases tables entries
    					转储所有DBMS数据库表条目
    --search            Search column(s), table(s) and/or database name(s)
    					搜索列，表和/或数据库名称
    --comments          Check for DBMS comments during enumeration
    					在枚举期间检查DBMS注释
    -D DB               DBMS database to enumerate
    					指定数据库名
    -T TBL              DBMS database table(s) to enumerate
    					指定表名
    -C COL              DBMS database table column(s) to enumerate
    					指定列名
    -X EXCLUDE          DBMS database identifier(s) to not enumerate
    					指定数据库标识符
    -U USER             DBMS user to enumerate
    					指定用户	
    --exclude-sysdbs    Exclude DBMS system databases when enumerating tables
    					枚举表时排除DBMS系统数据库
    --pivot-column=P..  Pivot column name
    					指定主列
    --where=DUMPWHERE   Use WHERE condition while table dumping
    					表转储时使用WHERE条件
    --start=LIMITSTART  First dump table entry to retrieve
    					要检索的第一个转储表条目
    --stop=LIMITSTOP    Last dump table entry to retrieve
    					要检索的最后一个转储表条目
    --first=FIRSTCHAR   First query output word character to retrieve
    					首先查询要检索的输出字符
    --last=LASTCHAR     Last query output word character to retrieve
    					最后查询输出要检索的单词字符
    --sql-query=SQLQ..  SQL statement to be executed
    					要执行的SQL语句
    --sql-shell         Prompt for an interactive SQL shell
    					提示交互式SQL shell
    --sql-file=SQLFILE  Execute SQL statements from given file(s)
    					从给定文件执行SQL语句

暴力破解：Brute force

    These options can be used to run brute force checks
    这些选项可用于执行强力检查
    
    --common-tables     Check existence of common tables
    					检查公共表的存在
    --common-columns    Check existence of common columns
    					检查公共列的存在

用户自定义函数注入：User-defined function injection

    These options can be used to create custom user-defined functions
    这些选项可用于创建自定义用户定义的函数
    
    --udf-inject        Inject custom user-defined functions
    					注入自定义用户定义的函数
    --shared-lib=SHLIB  Local path of the shared library
    					共享库的本地路径

访问文件系统：File system access

    These options can be used to access the back-end database management system underlying file system
    这些选项可用于访问后端数据库管理系统底层文件系统
    
    --file-read=FILE..  Read a file from the back-end DBMS file system
    					从后端DBMS文件系统中读取文件
    --file-write=FIL..  Write a local file on the back-end DBMS file system
    					在后端DBMS文件系统上写一个本地文件
    --file-dest=FILE..  Back-end DBMS absolute filepath to write to
    					要写入的后端DBMS绝对文件路径

访问操作系统：Operating system access

    These options can be used to access the back-end database management system underlying operating system
    这些选项可用于访问底层操作系统的后端数据库管理系统
    
    --os-cmd=OSCMD      Execute an operating system command
    					执行一擦操作系统命令
    --os-shell          Prompt for an interactive operating system shell
    					提示交互式操作系统shell
    --os-pwn            Prompt for an OOB shell, Meterpreter or VNC
    					提示OOB shell，Meterpreter或VNC
    --os-smbrelay       One click prompt for an OOB shell, Meterpreter or VNC
    					单击提示输入OOB shell，Meterpreter或VNC
    --os-bof            Stored procedure buffer overflow exploitation
    					存储过程缓冲区溢出利用
    --priv-esc          Database process user privilege escalation
    					数据库进程用户权限升级
    --msf-path=MSFPATH  Local path where Metasploit Framework is installed
    					安装Metasploit Framework的本地路径
    --tmp-path=TMPPATH  Remote absolute path of temporary files directory
    					临时文件目录的远程绝对路径

访问Windows注册表：Windows registry access

    These options can be used to access the back-end database management system Windows registry
    这些选项可用于访问后端数据库管理系统Windows注册表
    
    --reg-read          Read a Windows registry key value
    					读取Windows注册表项值
    --reg-add           Write a Windows registry key value data
    					编写Windows注册表项值数据
    --reg-del           Delete a Windows registry key value
    					删除Windows注册表项值
    --reg-key=REGKEY    Windows registry key
    					指定Windows注册表项
    --reg-value=REGVAL  Windows registry key value
    					指定Windows注册表项值
    --reg-data=REGDATA  Windows registry key value data
    					指定Windows注册表项值数据
    --reg-type=REGTYPE  Windows registry key value type
    					指定Windows注册表项值类型

通用：General

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

杂项：Miscellaneous

    -z MNEMONICS        Use short mnemonics (e.g. "flu,bat,ban,tec=EU")
    					使用短助记符（例如“flu，bat，ban，tec = EU”）
    --alert=ALERT       Run host OS command(s) when SQL injection is found
    					找到SQL注入时运行主机OS命令
    --answers=ANSWERS   Set predefined answers (e.g. "quit=N,follow=N")
    					设置预定义的答案（例如“quit = N，follow = N”）
    --beep              Beep on question and/or when SQL injection is found
    					发现SQL注入问题时发出哔哔声
    --cleanup           Clean up the DBMS from sqlmap specific UDF and tables
    					从特定于sqlmap的UDF和表中清除DBMS
    --dependencies      Check for missing (optional) sqlmap dependencies
    					检查缺少（可选）sqlmap依赖项
    --disable-coloring  Disable console output coloring
    					禁用控制台输出着色
    --gpage=GOOGLEPAGE  Use Google dork results from specified page number
    					使用指定页码的Google dork结果
    --identify-waf      Make a thorough testing for a WAF/IPS protection
    					对WAF / IPS保护进行全面测试
    --list-tampers      Display list of available tamper scripts
    					显示可用篡改脚本的列表
    --mobile            Imitate smartphone through HTTP User-Agent header
    					通过HTTP User-Agent标头模仿智能手机
    --offline           Work in offline mode (only use session data)
    					在离线模式下工作（仅使用会话数据）
    --purge             Safely remove all content from sqlmap data directory
    					安全地从sqlmap数据目录中删除所有内容
    --skip-waf          Skip heuristic detection of WAF/IPS protection
    					跳过启发式检测WAF / IPS保护
    --smart             Conduct thorough tests only if positive heuristic(s)
    					只在积极启发式的情况下才进行彻底的测试
    --sqlmap-shell      Prompt for an interactive sqlmap shell
    					提示交互式sqlmap shell
    --tmp-dir=TMPDIR    Local directory for storing temporary files
    					用于存储临时文件的本地目录
    --web-root=WEBROOT  Web server document root directory (e.g. "/var/www")
    					Web服务器文档根目录（例如“/ var / www”）
    --wizard            Simple wizard interface for beginner users
    					初学者用户的简单向导界面



