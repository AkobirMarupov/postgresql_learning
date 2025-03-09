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


# 2- dars.

Bu darsimizda 
```commandline
CREATE TABLE table_name();
```

qilib qo`lda kiritmasdan tayyor TABLE ni pastdagi yatdan tug'irlab olasak ham bo'ladi:

### Sayt ssilkasi => https://mockaroo.com/

Bu saytda TABLE ni tayyor holda olamiz va kodini PyCharm yoki VisualStudio da tug'irlab olamiz.
Quidagi telegram kanalda table yaratish deb qidirsangiz saytdan qanday qilib foydalanish haqida vedio darslik chiqadi.

### TELEGRAM KANAL: => https://t.me/sql_dars

```commandline
table yaratish
```
TABLE yaratgandan so'ng uni kuchirib olasz yani yuklab olasiz keyin u << download >>  bo'limiga tushadi
uni C: disk , D: disk yoki Desktop ga olib utsangiz ham bo'ladi va unga boradiga yulni quidagicha ko`rsatib SQL Shell ga kiritasz

MISOL:

```commandline
\i D:/users.sql
```

<< \i >> degani buyerda faylni ko'chirib kelishni bildiradigan funksiya.

##Biz tayyor TABLE kodini quidagicha uzgartirib tayyor holga keltiramiz:

MISOL:

```commandline
CREATE TABLE users (
    id BIGSERIAL NOT NULL PRIMARY KEY,
	first_name VARCHAR(50) NOT NULL,
	last_name VARCHAR(50) NOT NULL,
	email VARCHAR(50),
	birthday DATE NOT NULL,
	country VARCHAR(50) NOT NULL);

insert into users (first_name, last_name, email, birthday, country)
values ('Audra', 'Kleinhaus', 'akleinhaus0@sciencedaily.com', '2024/11/29', 'France');
insert into users (first_name, last_name, email, birthday, country)
values ('Haley', 'Owbridge', null, '2024/06/29', 'Portugal');
insert into users (first_name, last_name, email, birthday, country)
values ('Dodi', 'Spatig', 'dspatig2@wikipedia.org', '2024/06/03', 'Russia');
insert into users (first_name, last_name, email, birthday, country)
values ('Wynne', 'Parmby', null, '2024/10/21', 'China');
insert into users (first_name, last_name, email, birthday, country)
values ('Katharine', 'Wyld', null, '2024/11/20', 'Greece');
```

Bu kodda << email >> ga NOT NULL qo'ymaganligimiz sababi shundaki, bir nechta name lar uchun
emailllar qoyilmasdan yani emailsiz jadval yaratiladi.

Hamma qismini tayyor qilib bo`lgan quidagicha kod kiritib yaratilgan TABLE ni ishga tushiramiz:

```commandline
SELECT * FROM table_nomi;
```


MISOL:

```commandline
SELECT * FROM users;
```
Endi agar bizga birorta ustun kerak bo`lsa masalan: name > ustunini hammasi kerak va boshqa malumotlar chiqmasin degan malumot olish uchu
biz <<  *  >>   yulduzcha o`rnida ustun nomini yizamiz:

MISOL:

```commandline
SELECT name FROM users;
```

Ya'ni buyerda name degan ismlar ustunini chiqarib ber deyabmiz users bu yaratgan TABLE nomi yani yaratgan JADVAL nomi:
Bizga bir nechta ustunlar kerak bo'lsa agar ustunlar nomini vergul bilan yozib kiritib qo'yamiz:

MISOL:

```commandline
SELECT name,email,birthday FROM users;
```

Xuddi shunday qilib:...!









 







