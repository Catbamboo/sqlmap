# 5. 测试

Detection

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