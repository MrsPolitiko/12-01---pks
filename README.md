# Домашнее задание к занятию 12-01 "Базы данных" - Политико Ксения

Легенда
Заказчик передал вам файл в формате Excel, в котором сформирован отчёт.
На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

● какие данные хранятся в этих таблицах;

● какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

● идентификатор, первичный ключ, serial,

● фамилия varchar(50),

● ...

● идентификатор структурного подразделения, внешний ключ, integer).

#### Ответ:
Адрес

● address_id индентификатор (первичный ключ, integer)
● address адрес (varchar(100))
● branch_region идентификатор региона (внешний ключ, integer)
● branch_city идентификатор города (внешний ключ, integer)

Регион

● region_id (первичный ключ, integer)
● name_region (varchar(100))

Город

● city_id (первичный ключ, integer)
● name_city (varchar(100))

Тип подразделения

● dep_type_id (первичный ключ, integer)
● name_dep название типа подразделения (varchar(50))

Структурные подразделения

● department_id идентификатор подразделения (первичный ключ, integer)

● dep_to_type идентификатор типа (внешний ключ, integer)

● department_name название подразделения (varchar(100))

Сотрудники

● employee_id идентификатор должности сотрудника (первичный ключ, integer)

● title_id идентификатор должности (внешний ключ, integer)

● last_name Фамилия сотрудника (varchar(50))

● first_name Имя сотрудника (varchar(30))

● middle_name Отчество (varchar(30))

● salary Оклад (numeric)

● hire_data Дата найма (date)

● structural_dep_id индентификатор стурктурного подразделения (внешний ключ, integer)

● address_id идентификатор адреса (внешний ключ, integer)

Должность

● title_id: идентификатор должности (первичный ключ, integer)

● title должность (varchar(100))

Проекты

● project_id идентификатор проекта (первичный ключ, integer)

● project_name название проекта (varchar(100))

● project_description описание проекта (text)

● start_date Дата начала проекта (date)

● end_date Дата окончания проекта (date)

Назначения на проект

● employee_id идентификатор сотрудника (внешний ключ, integer)

● project_id идентификатор проекта (внешний ключ, integer)

Дополнительные задания (со звёздочкой*)

### Задание 2*
Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.

● Тип подразделения и структурное подразделение - функциональные зависимости;

●  Поле "проект" привести в атомарный вид, выделить в отдельную таблицу адрес филиала, создать первичный ключ для первой таблицы.
