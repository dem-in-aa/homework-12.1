# Домашнее задание к занятию «Базы данных» Андрей Дёмин

### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

---

### <ins>Ответ</ins>:

Какие данные хранятся в этих таблицах :

A) фамилия имя и отчество сотрудника 

B) Заработная плата сотрудника

C) Занимаемая должность сотрудника

D) Отдел, департамент, группа

E) Название подразделения

F) Дата найма

G) Адрес нахождения подразделения

H) Наименование проекта для сотрудника.

---

Какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

A, C, D, E, G, H) - строковый (varchar)

B) Оклад - числовой (decimal/numeric)

F) Дата - дата (date)

---

<ins>Вид БД</ins>:

Сотрудники

```
    - staff_id primary_key
    
    - Фамилия, varchar
    - Имя, varchar
    - Отчество, varchar
    - Дата найма, date
    - Код должности, внешний ключ , integer
    - Идентификатор адреса ,внешний ключ, serial   
    - id Проекта,внешний ключ,serial
```

Должности
```
   - post_id, первичный ключ, integer 

   - Должность, varchar     
   - идентификатор структурного подразделения, внешний ключ, integer
   - id оклада ,внешний ключ, integer
```

Оклад
```
    - salary_id  (serial)
    - salary     (numeric)
    
```


Структурное подразделение
```
    - division_id

    - Название, varchar
    - тип подразделения, varchar
    
```    
Адрес
```
    - address_id primary_key (serial)   

    - address                (varchar)
    - region_id              (serial)
    
```    
Регион
```
    - region_id (serial)
    - region    (varchar)
```

Проект
```
   - project_id primary_key (serial)
   - project_type           (varchar)
```


staff (

 staff_id primary_key,

 FName VARCHAR(50) ,
 
 LName VARCHAR(50) ,
 
 Patronymic varchar(50),

 divisions_id varchar(50),
 
 Structura_id varchar(50),
 
 date_off_id datetime,
 
 position_id varchar(50),
 
 salary_id numeric,
 
 address_id VARCHAR(50),
 
 project_id VARCHAR(50),
 
)

position (

position_id primary_key

spethion_type

)

divisions (

divisions_id primary_key

department varchar(50)

Unit Group varchar(50)

Unit Group_type

department_type

)

Structura (

Structura_id primary_key

Group varchar(50)

Structura_type 

Structura_title

)


date_off_Employee )

date_off_id primary_key

date datetime



## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
