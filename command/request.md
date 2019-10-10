# 2. 请求包

Request

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
                        "import hashlib;id2=hashlib.md5(id).hexdigest()") 	
                        在请求之前评估提供的Python代码