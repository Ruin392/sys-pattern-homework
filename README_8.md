
# Домашнее задание по лекции 12.8 «Резервное копирование баз данных» Аюпов Е


---

### Задание №1 

1.1. Полное резервное копирование, все остальные виды копирования тоже подойдут, но скорей всего будут избыточны или недостаточными;

1.2. Дифференциальный

1.3. Конечно возможен, если у вас есть реплика, то возможно просто моментальное переключение.

---

### Задание №2 
`pg_dump -U {user_name} {database_name} > /tmp/{database_name}.dump`

`pg_restore -d {database_name} /tmp/{database_name}.dump`

Что касается автоматизации вариантов много, самый популярный это cronjob. Менее популярный (по крайней мере я такого не 
видел) - это по событию (сохранение, удаление, обновление).

---

### Задание №3

1. Активируем Binary Logging

`nano /etc/mysql/mysql.conf.d/mysqld.cnf`
```
log_bin = /var/log/mysql/mysql-bin.log
expire_logs_days = 10
```
2. Создаем базу с именем {database_name}
3. Делаем полную копию
```
mysqldump -u {user_name} -p --all-databases --single-transaction --flush-logs --master-data=2 > {dump_name}.sql
```


В целом реплика почти всегда будет лучше кроме вариантов когда она начала рассинхрон ловить или в какой то момент записала битые данные

---



