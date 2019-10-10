# 8. 枚举

Enumeration

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