# FARDAR — Industrial Digital Lab

وب‌سایت چهارزبانه حمیدرضا فاردار به زبان‌های فارسی، انگلیسی، چینی و عربی.
این پروژه یک سایت استاتیک و مستقل است و برای اجرا به هاست ChatGPT، پایگاه داده یا
بک‌اند اختصاصی نیاز ندارد.

## اجرای محلی

```bash
npm install
npm run dev
```

نسخه نهایی و قابل انتشار داخل پوشه `dist` قرار دارد. برای یک بررسی سریع‌تر می‌توان
فایل `dist/index.html` را نیز مستقیماً باز کرد.

## ساختار فایل‌ها

- `dist/index.html` — ساختار اصلی صفحه
- `dist/assets/styles.css` و `dist/assets/refinements.css` — طراحی و واکنش‌گرایی
- `dist/assets/app.js` — محتوا و رفتار چهار زبان
- `dist/assets/portfolio.js` — کارت‌ها، آیکون‌ها و نمونه‌کارها
- `dist/assets/profile-000.jpg` — تصویر پروفایل
- `dist/assets/Hamidreza-Fardar-CV.pdf` — رزومه قابل دانلود
- `dist/favicon.svg` — فاویکون اختصاصی

## انتشار روی هاست مستقل

تنظیم مشترک همه سرویس‌ها:

- Build command: خالی یا `npm run build`
- Publish/Output directory: `dist`
- Production branch: `develop`

### Cloudflare Pages

در Cloudflare به `Workers & Pages` بروید، مخزن GitHub را متصل کنید و یک Pages
project بسازید. Framework preset را `None` و Output directory را `dist` بگذارید.

### Netlify

مخزن را از بخش `Add new site > Import an existing project` متصل کنید. فایل
`netlify.toml` تنظیمات انتشار را خودکار اعمال می‌کند.

### Vercel

مخزن را Import کنید. فایل `vercel.json` پوشه `dist` را به‌عنوان خروجی استاتیک
مشخص می‌کند.

### GitHub Pages

در تنظیمات مخزن، GitHub Pages را با GitHub Actions فعال کنید یا محتوای `dist` را
در ریشه شاخه مخصوص انتشار قرار دهید. برای دامنه اختصاصی، `fardar.ir` را به‌عنوان
Custom domain ثبت کنید.

## اتصال دامنه

تا قبل از آماده‌شدن هاست جدید، رکوردهای DNS فعلی را تغییر ندهید. بعد از موفقیت
اولین Deployment، دامنه `fardar.ir` را در سرویس جدید اضافه و فقط رکوردهای DNS
پیشنهادی همان سرویس را در Cloudflare جایگزین کنید.

توسعه اصلی پروژه روی شاخه `develop` انجام می‌شود. برای انتشار از شاخه `main`،
ابتدا تغییرات نهایی را از `develop` به `main` ادغام کنید.
