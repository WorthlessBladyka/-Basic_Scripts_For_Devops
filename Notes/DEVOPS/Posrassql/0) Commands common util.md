##
`\?` - help
`\! <пареметры>`  - запуск командной оболочки
`\l` - list database
`\dn` - list scheme
`\d` - list tables
`\d <name_table>` - input target table
`\dt <name_table>` - вывести количество полей
`\conninfo` - common setting DB

`\! pg_dump --version `       # проверить версию pg_dump
`\! du -sh /var/lib/postgresql`  # посмотреть размер данных PostgreSQL
`\! ps aux | grep postgres`   # найти процессы PostgreSQL

`\c <name_DB>` - connect database



[mockaroo](https://www.mockaroo.com/) - генератор таблиц
## WORK SESSION
```shell
		# connect postges and user
$ sudo -u postgres psql

$ psql -U bban -d <name_db>
```

``` sql
		-- exit session
CTRL + D
\d
```

```sql
		-- select activity session
SELECT * FROM pg_stat_activity;
```

```sql
		-- kill session
SELECT 
    pg_terminate_backend(procpid) 
FROM 
    pg_stat_activity 
WHERE 
	    -- don't kill my own connection!
    procpid <> pg_backend_pid()
	    -- don't kill the connections to other databases
    AND datname = 'database_name';

Перед выполнением этого запроса необходимо ОТОЗВАТЬ привилегии CONNECT, чтобы избежать новых подключений:

REVOKE CONNECT ON DATABASE dbname FROM PUBLIC, username;
```
