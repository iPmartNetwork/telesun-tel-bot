

 آموزش نصب و راه‌اندازی ربات تلگرام با Docker

## 1. نصب Docker و Docker Compose

### نصب Docker
برای نصب Docker دستورهای زیر را وارد کنید:

```bash
sudo apt update
sudo apt install docker.io
```

برای اطمینان از اینکه Docker به درستی نصب شده است:

```bash
sudo docker --version
```

### نصب Docker Compose
برای نصب Docker Compose:

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

برای اطمینان از نصب صحیح:

```bash
docker-compose --version
```

## 2. نصب پروژه از GitHub

برای دانلود پروژه از GitHub، ابتدا آن را کلون کنید:

```bash
git clone https://github.com/Mahtiw/telesun-tel-bot.git
cd telesun-tel-bot
```

## 3. وارد کردن توکن ربات و ادرس پنل ها
این اطلاعات را در فایل `login.py` تنظیم کنید.

برای ویرایش فایل `login.py` می‌توانید از ویرایشگرهای متنی مختلف استفاده کنید. در زیر چند روش معمول برای ویرایش فایل آورده شده است:

### 1. ویرایش با `nano` (در لینوکس)

اگر روی سرور لینوکس هستید، دستور زیر را وارد کنید:

```bash
nano login.py
```

پس از اتمام ویرایش، برای ذخیره تغییرات کلید `CTRL + O` را فشار دهید، سپس `Enter` را بزنید، و در نهایت با `CTRL + X` از ویرایشگر خارج شوید.

### 2. ویرایش با `vim` (در لینوکس)

اگر `vim` روی سرور نصب شده باشد، می‌توانید از آن استفاده کنید:

```bash
vim login.py
```

برای ورود به حالت ویرایش کلید `i` را فشار دهید. پس از اتمام ویرایش، کلید `ESC` را بزنید، سپس `:wq` را تایپ کنید و `Enter` بزنید تا تغییرات ذخیره و فایل بسته شود.

### 3. ویرایش با Notepad (در ویندوز)

اگر فایل را به سیستم خود انتقال داده‌اید، می‌توانید از Notepad یا دیگر ویرایشگرهای متنی استفاده کنید:

- فایل `login.py` را باز کنید.
- تغییرات لازم را انجام دهید و آن را ذخیره کنید.

**توجه:** حتما پس از ویرایش، فایل را به سرور برگردانید.

### تنظیم توکن ربات تلگرام

برای تنظیم توکن ربات تلگرام، به جای `'YOUR_BOT_TOKEN_HERE'`، توکن  ربات خود را وارد کنید. به این صورت:

```python
# توکن ربات
TOKEN = 'YOUR_BOT_TOKEN_HERE'
```

### تنظیم اطلاعات پنل‌ها

برای تنظیم اطلاعات پنل‌ها، آدرس URL و اطلاعات ورودی پنل‌ها را به شکل زیر وارد کنید:

```python
# اطلاعات پنل‌ها
panels = [
    {"url": "http://s1.example.com:1111/", "username": "user1", "password": "admin1"},
    {"url": "http://s1.example.com:2222/", "username": "user2", "password": "admin2"},
    {"url": "http://s1.example.com:3333/", "username": "user3", "password": "admin3"},
]
```

در اینجا:
- `url`: آدرس پنل‌ها
- `username`: نام کاربری پنل
- `password`: رمز عبور پنل


## 4. اجرای Docker Compose

برای راه‌اندازی ربات از طریق Docker Compose، دستور زیر را اجرا کنید:

```bash
docker-compose up -d
```

این دستور تمامی سرویس‌های لازم را راه‌اندازی کرده و ربات را در پس‌زمینه اجرا می‌کند.

## 5. بررسی وضعیت کانتینرها

برای مشاهده وضعیت کانتینرهای در حال اجرا، از دستور زیر استفاده کنید:

```bash
docker ps
```

این دستور لیستی از کانتینرهای در حال اجرا را نمایش می‌دهد.

## 6. توقف یا ریستارت کانتینرها

برای توقف کانتینرهای در حال اجرا:

```bash
docker-compose down
```

برای راه‌اندازی مجدد کانتینرها:

```bash
docker-compose up -d
```

## نکات تکمیلی

- در صورتی که سرور شما ریستارت شود، ربات به صورت خودکار با استفاده از Docker Compose راه‌اندازی خواهد شد.
- مطمئن شوید که اطلاعات توکن و پنل‌ها را به درستی وارد کرده‌اید تا ربات به درستی کار کند.

### اعمال تغییرات در کد
در صورت هرگونه تغییر در کد، برای اعمال تغییرات دستورات زیر را وارد کنید:

```bash
docker-compose down
docker-compose build --no-cache
docker-compose up -d
```

### تشکر از سروش عزیز
 [sorusham](https://github.com/sorusham)


