# 6. 注入技巧

Techniques

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