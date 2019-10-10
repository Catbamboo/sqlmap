# 4. 注入

Injection

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