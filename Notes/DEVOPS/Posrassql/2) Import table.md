## \i
`SHOW data_directory;` - select доступных директорий
`\i /tmp/file.sql;` - import file in DB
## .CSV

1) `CREATE table (id, first_name, last_name...)`
2) ```
   COPY <куда table1>(поля)
   FROM '/tmp/table.csv'
   DELIMITER ','
   CSV HEADER;
   ```
   