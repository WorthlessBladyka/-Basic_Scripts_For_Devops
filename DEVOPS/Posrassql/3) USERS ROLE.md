## psql
`$ sudo -u <postges> psql` - открыть psql
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
GRANT - определяет права доступа
REVOKE - отзывает права доступа

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
