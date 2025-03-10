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

### ORDER BY

Endi biz SELECT qilib olganimizda Alifbo tartibida va Alifboga teskari tartibda chiqarib beruvchi funksiyasi ham bor 
<<< ORDER BY >>>  Bu biz uchun eng kerakli funksiya Alifbo tartibida jadvallar yaratish uchun qo'llaniladi:
<<<  ASC  >>>  = Bu o'zi ko'rinishidan aytib turibdiki A harfidan boshlab yani Alifbo tartibida chiqarib beruvchi funksiya: 1 2 3 4 5
<<<  DESC  >>>  = Bu esa Alifbo tartibiga teskari yari teskari qilib chiqarib beradi => 5 4 3 2 1

MISOL:

```commandline
SELECT * FROM users ORDER BY first_name ASC;
```

Bu misolda Ismlarni Alifbo tartibida yozib beradi:


```commandline
SELECT * FROM users ORDER BY first_name DESC;
```

Bu misolda Ismlarni Alifbo tartibiga teskari holda chiqarib beradi :


Endi biz ORDER BY qilib Alifbo tartibida chiqarishi uchun 2 ta va undan ko'p ustunlarni kiritaolmaymiz
faqat 1 ta ustunni kiritib usha ustunni Alifbo tartibida yozishini bajarsak bo`ladi 

## ❌
 ❌ MISOL: ❌

```commandline
SELECT * FROM users ORDER BY first_name, email DESC;
```
❌ Bu xato misol ❌


# 3- Dars

Biz endi Yaratgan TABLE (Jadval) mizdan nechta davlat ishtirok etgan degan funksiyani ham ishlatsak bo`ladi.
Bu funsiya nomi: 
```commandline
DISTINCT
```
deb ataladi biz uni misol tariqasida ko'rmoqchi bo'lsak quidagi misoldek kiritamiz:

MISOL:

```commandline
SELECT DISTINCT country FROM users;
```
 
Bu misolda nechta davlat qatnashgan ya'ni o'zimizning O'zbekistonni misol qilib olib Viloyatlardan odamlar Jadvalini yozsak
biz DISTINCT qilib olib qaysi viloyatlardan odamlar borligini aniqlaymiz:

Endi bizda birorta yaratgan TABLE (Jadval)imizda << WHERE >> funksiyasidan foydalanib biror ustunning qaysi biri malumoti 
nechta qatnashgani va ufaqat usha malumotdagi Jadvaldagi malumotlarni chiqarib beruvchi funksiyani ishlatamiz:
Misol qilib aytganda AYOL va ERKAK lar bo`ladi bizga faqat erkaklar kerak shunday qilib << WHERE >> funksiyasidan foydalanib 
ishlatsak bo'ladi va yana davlatlar << country >> Masalan << Russia >> kerak bo'sa ham shu funksiyadan foydalanamiz;

MISOL:

```commandline
SELECT * FROM users WHERE country='Russia';
```
 Xuddi misoldagidek qilib kiritamiz men hozir Davlatlar uchun kiritdim sizda AYOL va ERKAK lar degan ustun bo`lsa 
ustun nomini yozasz orqasidan tenglik belgisini yozasz keyin esa bir tirnoqlarichida qaysi malumotdagi lar ro'yxati kerak bo'lsa ushani kiritasz

Endu biz << AND, OR >> degan funksiyalari ham bor bular bilan birga qaysi elementlar yani qaysi malumotlar kerakligini yozib kiritsangiz bo'ladi.

MISOL:

```commandline
SELECT * FROM usres WHERE country='Russia'AND jinsi='ERKAK' OR country='France';
```

Bizning tepadagi << users >> TABLE(Jadval)imizda << jinsi >> degan ustun yuq lekin misol tariqasida kiritib yozib ketdim
Bu misolda Russia va France dagi ERKAK lar ni chiqarib berishi haqidagi funksiyani ishlatdik
<< AND >> bu va deganini bildiradi, bu funksiya orqali bir nechta ustunlarni chiqarish mumkin:
<< OR >> bu yoki degani, bu funksiya orqali bir misolda ko'rinib turibdiki davlatlarning ichidagi Russia va France ning
erkaklarini chiqar deyabmiz OR yani YOKI degan funksiya bitta ustundagi U yoki BU malumotini bizga chiqarishini bildioradi



