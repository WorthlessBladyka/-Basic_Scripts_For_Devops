## psql
`$ sudo -u <postges> psql` - открыть psql
`$ psql -U bban -d database -W` - подключиться на localhost md5
## Setting Authentication **`pg_hba.conf`**
`$ cd /etc/posgresql/15/main/pg_hba.conf` - file conf Authentication
Method_auth:
- password - пароль в открытом виде
- md5
- scram-sha-256
- trust - без аунтификации
- peet - по логину на localhost
- ident - ???

## CREATE ROLE and DROP ROLE

``` sql
SELECT rolname FROM pg_roles;

or 

\du
```

`CREATE ROLE name LOGIN;`
Атрибуты:
- LOGIN
- SUPERUSER
- CREATEDB
- CREATEROLE
- PASSWORD 'string'
- CREATE ROLE name REPLICATION LOGIN - дает доступ роли к потоковой репликации

`DROP ROLE name;`

`CREATE USER name` == `CREATE ROLE name LOGIN;`

`$ createuser name` or `dropuser name`

## ALTER
`ALTER ROLE <user_name> <параметр>` - редактировать роль после создания
атрибуты:
- `ALTER ROLE name SET my_custom_value = 10000;` - задать нестандартное значение параметра ..
- `ALTER ROLE name WITH PASSWORD '123345566';` - set password
- `ALTER ROLE name WITH PASSWORD NULL;` - delete password
- `ALTER ROLE name VALID UNTIL 'infinity';` - сделать пароль действительным вечно
- `ALTER ROLE name VALID UNTIL 'May 4 12:00:00 2015 +1';` 
- SUPERUSER, NOSUPERUSER, CREATEDB, NOCREATEDB, CREATEROLE...

## GRANT and REVOKE
П. Система с избирательным доступом
GRANT - определяет РАЗРЕШЕНИЯ для доступа
REVOKE - отзывает разрешения

```
-- Право создавать объекты в конкретной схеме
GRANT CREATE ON SCHEMA schema_name TO role_name;
```

```
-- Дать право на COPY FROM (импорт)
GRANT pg_read_server_files TO username;

-- Дать право на COPY TO (экспорт)  
GRANT pg_write_server_files TO username;
```

П. Выдаваемое разрешение привязывается к файлам, а не к конкретному user. Такой подход не применяется в чистом виде. Такой подход усложняет жизнь безопаснику
П. Разрешения выдаются на ресурсы, а права выдаются субъектам

##
Существует два вида групп ролей: серверные группы и просто группы.
В серверные группы входят группы и пользователи, которые администрируют DB
В "просто" группы входят остальные users.

**Разработчик** создает группы ролей, а **администратор** добавляет в эти группы людей.

Плохим тоном будет выдавать разрешения на ресурсы, так как это усложняет security администратору. Также, не желательно выдавать права напрямую Users. Для правильной организации безопасности для предоставления прав на ресурсы, пользователей необходимо добавлять в группы с необходимыми правами.