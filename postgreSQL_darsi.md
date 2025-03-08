# postgreSQL darsini noldan urganish strategiyasi va kodlar bo`limi
## DARS BOSHLANDI

SQL Shel (pscl) ni ochib olamiz va enter bisib boramiz password degan joyigacha ,
keyin bitta DATABASE yaratamiz DATABASE ni yaratish uchun quidagicha kod kiritamiz:

```
CREATE DATABASE database_nomi;
```

database_nomi => buyerga yaratmoqchi bo`lgan DATABASE nomini kiratis masalan users deyish mumkin va hokazo:

# DATABASE ichida TABLE yaratish

Endi DATABASE  ni CREATE yani yaratganimizdan song << \c database_nomi >> deb yaratgan DATABASE ichiga kirib olamiz,
song yaratgan DATABASE ichida TABLE yaratamiz TABLE ni yaratish quidagicha bo`ladi kodi :

```
CREATE TABLE users(
        id BIGSERIAL NOT NULL PRIMARY KEY,
        name VARCHAR(60) NOT NULL,
        email VARCHAR(60) NOT NULL,
         birthday DATE NOT NULL );

```

Quidagicha kiritamiz va qisqa qilib TABLE yaratganimizni yozdik TABLE xuddi shunday yaratailadi.
tepadagi kodni kiritganimizdan keyin oynada:

```
CREATE TABLE
```

degan tozuv chiqadi shu yozuv chiqqandan keyin TABLE yaratilgan hisoblanadi:
va << \d >> qilib tekshirib olamz.
Agar << \d table_nomi  >> deb kiritsak bizga qanday yaratilganligi haqida chiqarib beradi ustunlari va qoshimchalarini:
table_nomi => bu biz tepada TABLE yaratganimizda << users >> degan edik shuning uchun table_nomi ni qo`yib ketamiz

# DATABASE va TABLE larni uchirish

DATABASE va TABLE larni uchirish uchun << DROP >> operatoridan foydalanamiz:
masalan:
DATABASE ni uchirish:

```
DROP DATABASE database_nomi;
```

TABLE ni uchirish:

```
DROP TABLE table_nomi;
```

# Jadvalga ma'lumot yozish:

Jadvallar yaratish va Jadvalga ma'lumotlarni kiritish uchun << INSERT INTO >> degan operatoridan foydalanamiz,

<< INSERT INTO table_nomi()  >>  deb kiritamiz va qavs ichiga kiritmoqchi bo`lgan jadval maluotlarimizni yozamiz:
<< VALUES () >> deb ochamiz va kiritmoqchi bo'lgan har bitta ma'lumotlarni yozamiz:

MISOL:

```
INSERT INTO users(name,email,birthday)
VALUES ('Akobir', 'akobir@gmail.com, '2004-02-18);
```

Xuddi shuday qilib malumotlar kiritamiz:
AGar yana malumot kritmoqchi bo`lsangiz xuddi shunday qilib kiritasiz:
MISOL:

```
INSERT INTO users(name,email,birthday)
VALUES ('Samandar', 'smandar@gmail.com, '2007-09-08);
```

Xuddi shunday qilib 2- ma;lumotni kiritamiz:

# Kiritgan ma'lumotlarni ko`rish.

Kiritgan malumotlarni ko`rish uchun quidagidek qilib kod yozamiz:
<< SELECT * FROM table_nomi >> deb kod kiritamiz table_nomi => degan joyimizga yaratga jadvalimizning nomi yani 
TABLE nomini kiritamiz:
MISOL:

```
SELECT * FROM users;
```

users deganimni boisi tepada users degan TABLE yaratganim uchun misol sifatida kirityabman siz ham xuddi shunday TABLE nomini yozasz.

# Xulosa:

Kiritgan malumotlarimizni FROM qilib olib ko`rishimiz mumkin


















