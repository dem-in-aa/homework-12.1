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

Сотрудник
```
   - staff_id                   (primary key, serial)
   - family_name                (varchar)
   - name                       (varchar)
   - patronymic                 (varchar)
   - date_of_hiring_id          (date)
   - post_id                    (serial)
   - division_id                (serial)
   - project_id                 (serial)
```
Дата найма
```
   - date_of_hiring_id          (primary key, serial)
   - date_of_hiring             (date)    
```
Должность
```
   - post_id                    (primary key, serial)
   - post_type                  (varchar)    
   - division_type_id           (serial)
   - salary_id                  (serial)
```
Оклад
```
    - salary_id                 (primary key, serial)
    - salary                    (numeric) 
```
Тип подразделения
```
    - division_type_id          (primary key, serial)
    - division_type             (varchar)    
```    
Структурное подразделение
```
    - division_id               (primary key, serial)
    - division_name             (varchar)
    - division_type_id          (serial)
    - address_id                (serial)
```    
Адрес
```
    - address_id                (primary key, serial)   
    - address                   (varchar)
    - region_id                 (serial)    
```    
Регион
```
    - region_id                 (primary key, serial)
    - region                    (varchar)
```

Проект
```
   - project_id                 (primary key, serial)
   - project_type               (varchar)
```

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
