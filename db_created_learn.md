# PostgreSQL Ma'lumotlar Bazasi Yaratish va Jadval Qo'shish

## 📌 Kirish
Ushbu hujjatda **PostgreSQL**-da yangi ma'lumotlar bazasini yaratish va unga jadval qo'shish bo'yicha bosqichma-bosqich ko'rsatmalar berilgan.

---

## 📋 Talablar
- 🛠 **PostgreSQL** o'rnatilgan bo'lishi kerak.
- 🖥 **psql** CLI vositasi mavjud bo'lishi kerak.

---

## 🏗 Ma'lumotlar Bazasini Yaratish
Ma'lumotlar bazasini yaratish uchun quyidagi **SQL** buyruqlaridan foydalanamiz:

```sql
CREATE DATABASE my_database;
```

So‘ng, ma'lumotlar bazasiga ulanish uchun:

```sql
\c my_database;
```

---

## 🗃 Foydalanuvchilar Jadvalini Yaratish
Foydalanuvchilar jadvalini yaratish uchun quyidagi **SQL** buyruqlarini bajaring:

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password_hash TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## ✅ Xulosa
Ushbu hujjat orqali **PostgreSQL**-da **ma'lumotlar bazasini yaratish** va **foydalanuvchilar jadvalini qo'shishni** o'rgandik. 

Agar qo'shimcha jadval yoki ustunlar qo'shish kerak bo'lsa, **`ALTER TABLE`** buyruqlaridan foydalanishingiz mumkin. 

🚀 **Muvaffaqiyatli kodlash!**