

# Домашнее задание по лекции 13.1 «Уязвимости и атаки на информационные системы » Аюпов



---

### Задание №1 

1) 3306/tcp open  mysql   MySQL 5.0.51a-3ubuntu5 = MySQL 5.0.x - [Single Row SubSelect Remote Denial of Service](https://www.exploit-db.com/exploits/29724)


2) 21/tcp open  ftp     vsftpd 2.3.4 = [vsftpd 2.3.4 - Backdoor Command Execution](https://www.exploit-db.com/exploits/49757)

3) 5432/tcp open  postgresql PostgreSQL DB 8.3 = [PostgreSQL 8.2/8.3/8.4 - UDF for Command Execution](https://www.exploit-db.com/exploits/7855)


---


### Задание №2
SYN-сканирование:
    Открытые порты: Nmap покажет порты, которые отвечают на SYN-пакеты. Это означает, что эти порты, скорее всего, открыты и на них работают службы.

FIN-сканирование:
    Открытые порты: Nmap покажет порты, которые не отвечают на FIN-пакеты. Это означает, что эти порты, скорее всего, открыты.

Xmas-сканирование:
    Открытые порты: Nmap покажет порты, которые не отвечают на Xmas-пакеты. Это означает, что эти порты, скорее всего, открыты.

UDP-сканирование:
    Открытые порты: Nmap покажет порты, которые отвечают на UDP-пакеты. Это означает, что эти порты, скорее всего, открыты и на них работают UDP-службы.
