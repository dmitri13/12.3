# Домашнее задание к занятию "`12.3 SQL`" - `Овчинников Дмитрий`


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

---

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

select distinct district from address

where district like 'K%a' and district not like '% %'

![sakila1](https://github.com/dmitri13/12.3/blob/main/img/sakila1.png)

---

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.

select payment_id, payment_date, amount

from payment

where payment_date between '2005-06-15 00:00:00' and '2005-06-18 23:59:59' and amount > 10.00

![sakila2](https://github.com/dmitri13/12.3/blob/main/img/sakila22.png)
---

### Задание 3

Получите последние пять аренд фильмов.

select rental_id , rental_date

from rental

order by rental_date desc

limit 5

![sakila3](https://github.com/dmitri13/12.3/blob/main/img/sakila3.png)

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie.

Сформируйте вывод в результат таким образом:

  -  все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
  -  замените буквы 'll' в именах на 'pp'.

select lower(last_name) last_name , replace ( lower(first_name), 'll', 'pp') first_name , active

from customer

where first_name = 'KELLY' or first_name = 'WILLIE' and active >0

![sakila4](https://github.com/dmitri13/12.3/blob/main/img/sakila4.png)
---
