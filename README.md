# Домашнее задание к занятию 1 «Disaster recovery и Keepalived» - Аюпов Е


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)


### Задание 1

1. [Скриншот](https://github.com/Ruin392/sys-pattern-homework/assets/53511812/601a7eb0-ba42-4f68-8103-8d05e3d98b20)

---

### Задание 2

`Приведите ответ в свободной форме........`

1. [Настройка_Мастер_Слейв + vip](https://github.com/Ruin392/sys-pattern-homework/assets/53511812/0cc42340-4e4f-4244-ae6f-3a14dd7827ce)



2. [Интерфейсы](https://github.com/Ruin392/sys-pattern-homework/assets/53511812/ef4d7736-8a5c-419a-86ee-c8861fb6fbaa)

3. [Состоянии службы ](https://github.com/Ruin392/sys-pattern-homework/assets/53511812/ae28b564-df0b-4975-b3d6-c1a4799e5f41)

4. [Итоговая конфигурация](https://github.com/Ruin392/sys-pattern-homework/assets/53511812/8c010633-0d21-43a5-8bf6-085828691753)



```
Скрипт проверки порта и фала
check_port() {
    nc -z -w3 192.168.100.9 80
    return $?
}

check_index() {
    if [ -f "/var/www/html/index.nginx-debian.html" ]; then
        return 0
    else
        return 1
    fi
}

check_port
port_status=$?
check_index
index_status=$?

if [ $port_status -ne 0 ] || [ $index_status -ne 0 ]; then
    exit 1
else
    exit 0
fi
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`


