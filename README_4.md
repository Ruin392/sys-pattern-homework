
# Домашнее задание по лекции 12.5 «Индексы» Аюпов Е

---

### Задание №1

С округлением
```sql
select sum(data_length) as data, sum(index_length) as index_l,round( (sum(index_length)/sum(data_length)) * 100 ) as percent from information_schema.TABLES
where table_name in (select TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA = 'sakila')
group by TABLE_SCHEMA
```

Без округления
```sql
select sum(data_length) as data_length, sum(index_length) as index_length,(sum(index_length)/sum(data_length)) * 100 as percent from information_schema.TABLES
where table_name in (select TABLE_NAME from information_schema.TABLES where TABLE_SCHEMA = 'sakila')
group by TABLE_SCHEMA
```

---

### Задание №2 ([Текст Задания](https://github.com/netology-code/sdb-homeworks/blob/main/12-05.md#%D0%B7%D0%B0%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-2))

Перечислите узкие места:

- `SELECT * FROM payment p, rental r, customer c, inventory i, film f `- зачем такое количество данных
- `p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id` - это что попытка в самопальный join
- `sum(p.amount) over (partition by c.customer_id, f.title)` - зачем делать тяжелые операции?

Оптимизация использовал индексы

```


```sql
create index payment_payment_date_index
    on payment (payment_date);


select concat(c.last_name, ' ', c.first_name) as name, sum(payment.amount) as total
from payment
         join customer c on c.customer_id = payment.customer_id
         join rental r on r.rental_id = payment.rental_id
         join inventory i on i.inventory_id = r.inventory_id
where payment_date >= '2005-07-30'
  and payment_date < DATE_ADD('2005-07-30', INTERVAL 1 DAY)
group by payment.customer_id

```

---



