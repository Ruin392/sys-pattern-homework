
# Домашнее задание по лекции 12.3 «SQL. Часть 1» Аюпов Е


---

### Задание №1 

```sql
select district
from address
where district like "K%a" and  district not like "% %"
```

---

### Задание №2

```sql
select amount, date(payment_date)
from payment
where day(payment_date) between 15 and 18
and  month(payment_date) = 6
and year(payment_date) = 2005
and amount >= 10.00
```
---

### Задание №3
```sql
select *
from rental
order by rental_date desc
limit 5
```
---

### Задание №4
```sql
select concat(first_name, " ", last_name) as origin,
       lower(concat(replace(lower(first_name), "ll", "pp"), " ", last_name)) as modify
from customer
where lower(first_name) in ('kelly', 'willie')
```
---
