# گیمینو — آماده ساخت APK برای مایکت

ساختار این بسته:
- index.html — خود برنامه گیمینو
- manifest.json — مشخصات برنامه
- sw.js — Service Worker
- icon-192.png / icon-512.png / icon-maskable-512.png — آیکن‌ها
- .github/workflows/build-gamino.yml — ساخت APK Release و امضای آن

## مراحل

1. همه فایل‌های این بسته را در ریشه Repository گیت‌هاب قرار بده.
2. فایل workflow باید دقیقاً در `.github/workflows/build-gamino.yml` باشد.
3. در GitHub برو به:
   Settings → Secrets and variables → Actions
4. یک Repository Secret بساز:
   Name: `SIGNING_PASSWORD`
   Value: یک رمز قوی که فقط خودت می‌دانی.
5. برو به Actions → Build Gamino Release APK → Run workflow.
6. بعد از موفقیت، از بخش Artifacts فایل `Gamino-Release` را بگیر.
7. فایل `Gamino-release.apk` خروجی Release امضاشده است.

## لینک امتیاز مایکت

بعد از انتشار برنامه در مایکت، لینک صفحه برنامه را داخل `index.html` در مقدار `MYKET_URL` قرار بده:

const MYKET_URL='لینک صفحه گیمینو در مایکت';

سپس دوباره APK را بساز.

کلید امضای برنامه را حذف نکن؛ برای نسخه‌های بعدی باید همان کلید استفاده شود.
