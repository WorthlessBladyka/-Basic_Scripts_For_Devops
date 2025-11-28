## CREATE and ALTER TABLE

`CREATE DATABASE <name>;` - create database

Типы: 
- VARCHAR, 
- NUMERIC, 
- BIGSERIAL - генерирует последоваетльность чисел
- DATE
![[Снимок экрана 2025-11-23 в 2.00.50 PM.png]]
![[Снимок экрана 2025-11-23 в 2.19.40 PM.png]]
`\d` - list table
`\d <name_table>` - input target table
`\dt <name_table>` - вывести количество полей
### DROP and DELETE
`DROP TABLE <name_table>;` - delete table
`DELETE FROM <name_table> WHERE id = 1;` - удалить поле со значением id 1
### ALERT
```sql
		-- Добавить колонку в конец таблицы tabletest
ALTER TABLE tabletest
ADD COLUMN testColumn VARCHAR(10);
```

```sql
		-- Изменить тип колонки с явным указанием на тип
ALTER TABLE tabletest1 
ALTER COLUMN testLink TYPE bigint 
USING testLink::bigint;
```

```sql
		--RENAME table
ALTER TABLE old_name RENAME TO new_name;
```




## Выборка данных (таблица)
| name     | value                 |
| -------- | --------------------- |
| SELECT   | вывести               |
| ORDER BY | сорт                  |
| DISTINCT | хотя-бы раз           |
| WHERE    | по условию            |
| AND      | и                     |
| OR       | или                   |
| LIMIT    | сколько?              |
| OFFSET   | начиная с             |
| FETCH    | ???                   |
| IN       | в чем?                |
| BETWEEN  | промежуток            |
| LIKE     | шаблон                |
| iLIKE    | шаблон без регистра   |
| GROUP BY | сгруппировать         |
| HAVING   | имеет столько то..    |
| ALIAS    | заменить на псевдоним |
| COALESCE | not-null              |
| COUNT    | посчитай              |
## Базовая выборка данных
SELECT, ORDER BY, DISTINCT, WHERE, AND, OR, LIMIT, OFFSET, FETCH
### SELECT - вывести
`SELECT * FROM <name_table>;` - вывести все поля

`SELECT FROM <name_table>;` - вывести количество записей

`SELECT <first_name>, <last_name> FROM <name_table>;` - вывести все значения из указанных колонок
### DISTINCT - вывести один раз, если упоминается
`SELECT DISTINCT <col_name> FROM <name_table>;` - хотя-бы раз
### ORDER BY - сорт
`SELECT * FROM <name_tabel> ORDER BY <name_col> ASC`; - вывести все поля и отсортировать от алфавита отталкиваясь от указанной колонки
`SELECT * FROM <name_tabel> ORDER BY <name_col> DESC`; - вывести все поля и отсортировать в обратном порядке отталкиваясь от указанной колонки
### WHERE - по условию
`SELECT * FROM <name_table>` ==WHERE== `<gender = 'Female'>;` - вывести только те поля, которые имеют колонку gender со значением Female

`SELECT * FROM <name_table> WHERE <gender = 'Female'>` ==AND== `<country = 'Argentina'>;` - вывести только те поля, которые имеют колонки gender со значением female и country со значением Argentina

`SELECT * FROM <name_table> WHERE <gender = 'Female'> AND (<country = 'Argentina'>` ==OR== `<country = 'Slovakia'>);` - вывести только те поля, которые имеют колонки gender со значением female и country со значением Argentina или Slovakia
### LIMIT - ограничить выборку OFFSET - позиция
`SELECT * FROM <name_table> OFFSET 20 LIMIT 10;` - вывести все строки начиная с 21 позиции с лимитом 10
### FETCH 
`SELECT * FROM <name_table> OFFSET 20 FETCH FIRST 5 ROW ONLY;` вывести все строки начиная с 21 позиции с лимитом 10
## Базовая выборка данных 2 
IN, BETWEEN, LIKE, iLIKE, GROUP BY, HAVING, ALIAS, COALESCE, COUNT

### IN - в чем?

`SELECT * FROM <name_table> WHERE country` ==IN== `('US', 'Russia', 'China');` - вывести все столбцы, в которых имеется в поле country с US или Russia ил China
### BEYWEEN - промежуток
`SELECT * FROM <name_table> WHERE data BEYWEEN '2010-01-20' AND '2020-01-19';` - вывести все строки в промежутке по условию data
### LIKE - шаблон для поиска с учетом регистра
`SELECT * FROM <name_table> WHERE email LIKE '%gmail.%';` - вывести все колонки, в которых имеется email с указаным шаблоном
### iLIKE - шаблон
``SELECT * FROM <name_table> WHERE first_name LIKE '%b'` - вывести все колонки, в которых фамилия начинается с b or B
### COUNT - посчитать и GROUP BY - сгруппировать
`SELECT country, COUNT(*) FROM <name_table> GROUP BY country;` - посчитай все и выведи страны предварительно сгруппировав их по странам
### HAVING - имеют
`SELECT country, COUNT(*) FROM <name_table> GROUP BY country HAVING COUNT(*) > 10;` - посчитай все, сгруппируй по странам и выведи только те, которых больше 10
### AS - элиас(alias) псевдоним
![[Снимок экрана 2025-11-23 в 3.46.06 PM.png]]
\- вывести все поля, но имена колонок замени указанными псевдонимами 
### COALESCE - функция, которая возвращает первое не-NULL значение из списка переданных ей аргументов

![[Снимок экрана 2025-11-23 в 3.50.39 PM.png]]
![[Снимок экрана 2025-11-23 в 3.50.59 PM.png]]


## Агрегаты и базовая арифметика
### MAX, MIN, AVG and ROUND
`SELECT MAX(prise) FROM name_table;` - вывести макс прайс
`SELECT MIN(prise) FROM name_table;` - вывести мин прайс
`SELECT AVG(prise) FROM name_table;` - вывести среднее значение
`SELECT ROUND(AVG(prise)) FROM name_table;` - вывести среднее значение и округлить
### SUM
`SELECT SUM(prise) FROM name_table;` - сумма всей колонки prise


## Date and time
### NOW()
`SELECT NOW();` - вернёт текущее время и дату
`SELECT NOW()::TIME;` - вернёт текущее время
`SELECT NOW()::DATE;` - вернёт текущюю дату
### INTERVAl
`SELECT NOW() - INTERVAL '1 YEAR';` - вернёт дату и время на 1 год меньше от текущего времени 
`SELECT NOW() + INTERVAL '10 MONTHs';` - вернёт дату и время на 10 месяцев больше от текущего времени
- YEAR
- MONTHs
- DAYS
### EXTRACT
`SELECT EXTRACT(YEAR FROM NOW());` - вернет текущий год
- YEAR
- MONTH
- DAY
- DOW - день недели
### AGE - считает интервал по времени
`SELECT id, first-name, last-name, gender, data-of-brirt AGE(NOW(), data-of-birth) AS age FROM <name_table>` - вернет таблицу с новой колонкой, в которой будет указан возраст
### TO_CHAR() формат времени
`SELECT (col_time, 'YYYY-MM-DD HH24:MI:SS')`


## PRIMARY KEY
### Delete key
![[Снимок экрана 2025-11-23 в 6.15.37 PM.png]]
`ALTER TABLE <name_table> DROP CONSTRAINT <name_key>;` - удаление primary key
### Create key and update sequences
`ALTER TABLE <name_table> ADD PRIMARY KEY(id);` - назначение ключа на колонку id

`SELECT setval('employee_id_seq', 1001, true);` - используется для управления последовательностями (sequences)
- `'employee_id_seq'` - имя последовательности
- `1001` - новое значение, которое будет установлено
- `true` - флаг, указывающий как обрабатывать следующее значение
```sql
SELECT setval('sequence_name', new_value, is_called);
```
##### `is_called`:
- `true` - следующее значение будет `1002` (новое значение + 1)
- `false` - следующее значение будет `1001` (точно установленное значение)
### Create Composite primary key
```
CREATE TABLE course_grades (
    quarter_id INTEGER,
    course_id TEXT,
    student_id INTEGER,
    grade INTEGER,
    PRIMARY KEY(quarter_id, course_id, student_id)
);
```


## Unique and check
### Ограничение уникальности (unique)
``` sql
ALTER TABLE <name_table> ADD CONSTRAINT <name_unique_email_address> UNIQUE (email);
```
\- добавляет ограничение, которое гарантирует, что в столбце email не будет повторений
- **Гарантирует уникальность** значений в столбце
- **Запрещает дубликаты** email адресов
- Автоматически создает индекс для быстрой проверки
### Ограничение проверки (check)
```sql
ALTER TABLE <name_table> ADD CONSTRAINT gender_constraint CHECK (gender = 'Male' or gender = 'Female');
```
- Проверяет значения перед вставкой/обновлением
- **Разрешает только** 'Male' или 'Female' в столбце gender
- Блокирует любые другие значения
### Удаление ограничений
`ALTER TABLE users DROP CONSTRAINT unique_email_address;`
