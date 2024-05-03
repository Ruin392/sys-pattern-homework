
# Домашнее задание по лекции 12.4 «SQL. Часть 2»

---

### Задание №1 

```sql
select concat(s.first_name, " ", s.last_name) as staff,
       c.city                                 as city,
       count(c2.customer_id)                  as customres_count
from store
         join staff s on store.manager_staff_id = s.staff_id
         join address a on a.address_id = s.address_id
         join city c on a.city_id = c.city_id
         join customer c2 on store.store_id = c2.store_id
group by store.store_id
having customres_count > 300
```

---

### Задание №2

```sql
select count(*) as count_film from film
where length > (select AVG(length) from film)
```

---

### Задание №3

```sql
select month(payment_date) as p_date, SUM(amount) as amount, count(r.rental_id) as count_rental
from payment
         join rental r on r.rental_id = payment.rental_id
group by p_date
order by amount desc
limit 1
```

---


