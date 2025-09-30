# umami-installation-guide
Installation guide for Umami Analytics on Ubuntu with Docker
باشه، این نسخه آماده برای **Paste کردن مستقیم توی GitHub** هست. کافیه بعد از ساخت ریپو و باز کردن فایل `README.md` روی GitHub، کل محتوا رو جایگزین کنی و **Commit changes** بزنی.

````markdown
# نصب و راه‌اندازی Umami Analytics

این راهنما توضیح می‌دهد که چگونه سرویس **Umami** را برای آنالیز وب‌سایت خود نصب و پیکربندی کنید.  
Umami یک جایگزین سبک، متن‌باز و بدون محدودیت تحریم برای Google Analytics است.

---

## پیش‌نیازها
- یک سرور لینوکسی (Ubuntu 20.04 یا بالاتر)
- دسترسی SSH
- نصب بودن Docker و Docker Compose

---

## مرحله 1: به‌روزرسانی سرور

```bash
sudo apt update && sudo apt upgrade -y
````

---

## مرحله 2: دریافت سورس Umami

```bash
git clone https://github.com/umami-software/umami.git
cd umami
```

---

## مرحله 3: تنظیم متغیرهای محیطی

یک فایل `.env` بسازید و مقادیر زیر را وارد کنید:

```yaml
DATABASE_URL=postgresql://umami:password@db:5432/umami
HASH_SALT=رمز_تصادفی_خودتون
```

---

## مرحله 4: اجرای Docker Compose

```bash
docker-compose up -d
```

این دستور سرویس Umami و دیتابیس PostgreSQL را بالا می‌آورد.

---

## مرحله 5: دسترسی به پنل مدیریتی

پس از بالا آمدن سرویس، در مرورگر خود آدرس زیر را باز کنید:

```
http://YOUR_SERVER_IP:3000
```

* نام کاربری پیش‌فرض: `admin`
* رمز عبور پیش‌فرض: `umami`

---

## مرحله 6: اتصال به وب‌سایت

کد اسکریپت Umami را داخل تگ `<head>` سایت خود قرار دهید:

```html
<script async src="http://YOUR_SERVER_IP:3000/umami.js" data-website-id="SITE_ID"></script>
```

---

## نکات پایانی

* برای امنیت بیشتر، پشت Nginx یا Caddy قرار دهید.
* می‌توانید دامنه اختصاصی روی Umami ست کنید.
* مستندات کامل‌تر در [وب‌سایت رسمی Umami](https://umami.is) موجود است.

---

✍️ این داکیومنت توسط من نوشته شده و در اختیار جامعه آزاد قرار می‌گیرد.
خوشحال می‌شم اگر باگ یا پیشنهادی داشتید Pull Request بزنید!

```

---

اگر بخوای، می‌تونم همین فایل رو برات **یک فایل آماده برای دانلود (`README.md`) بسازم** تا مستقیم آپلود کنی بدون اینکه Paste کنی. می‌خوای بسازم؟
```
