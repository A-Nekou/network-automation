# Telegram Device Configurator for Network Teams 🔧🤖

این پروژه یک فلو حرفه‌ای در [n8n](https://n8n.io) است که به تیم‌های شبکه این امکان را می‌دهد تا **از طریق یک ربات تلگرام، تنظیمات اولیه دستگاه‌های شبکه** (مانند Mikrotik یا Cisco) را از راه دور انجام دهند.

---

## ✨ امکانات

- 🔐 **احراز هویت کاربر تلگرام** (فقط افراد مجاز)
- 📡 دریافت فرمان از تلگرام (`/config`)
- 🧠 پشتیبانی از مدل‌های مختلف:
  - `mikrotik` → با دستورات `/system identity set` و ...
  - `cisco` → با دستورات `enable`, `configure terminal`, `hostname` و ...
- 🖥 اجرای خودکار دستورات کانفیگ از طریق SSH
- 📬 پاسخ دقیق به کاربر در تلگرام پس از هر عملیات
- 📦 بدون وابستگی به Google Sheets یا دیتابیس خارجی

---

## 🧪 پیش‌نیازها

- سرور N8N روی Docker یا لوکال
- دسترسی به SSH روی تجهیزات (IP و credentials)
- یک [Telegram Bot](https://t.me/BotFather) + توکن آن
- تعریف Credential مربوط به Telegram در n8n

---

## 📤 دستور استفاده در تلگرام

ارسال پیام زیر به بات:


### پارامترها:

| پارامتر | توضیح |
|---------|--------|
| `ip` | آدرس تجهیز |
| `user` | نام کاربری SSH |
| `pass` | پسورد فعلی SSH |
| `hostname` | نام جدید تجهیز |
| `newpass` | رمز عبور جدید |
| `model` | یکی از: `mikrotik`, `cisco` |

---

## 🔐 محدودیت دسترسی

- فقط کاربری که username تلگرام او در whitelist است (مثل `Ali_Nekoo98`) مجاز به اجرای دستورات است.

---

## ⚠️ نکات امنیتی

- Credentialهای واقعی مثل توکن تلگرام، در فایل export نشده‌اند.
- از Credentialهای رمزگذاری‌شده در n8n استفاده کنید.
- توصیه می‌شود از VPN یا IP whitelist برای دسترسی به n8n استفاده شود.

---

## 📷 پیش‌نمایش فلو

![screenshot](images/screenshot.png)

---

## 📁 فایل‌ها

| فایل | توضیح |
|------|--------|
| `workflow/telegram_device_configurator.json` | فایل JSON قابل ایمپورت در n8n |
| `README.md` | همین فایل توضیحات |
| `images/screenshot.png` | نمایی از فلو در n8n (اختیاری) |

---

## 🧑‍💻 اجرا در n8n

1. وارد n8n شوید
2. از مسیر: **Workflows → Import from File**
3. فایل `telegram_device_configurator.json` را بارگذاری کنید
4. Telegram Credential را ست کنید

---

## 🪪 لایسنس

MIT License © 2025 [Your Name]
