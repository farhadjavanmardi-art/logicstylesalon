# 💇 پکیج کامل انتقال — Logic Style (نرم‌افزار شبیه‌سازی)

> این سند همهٔ چیزهای لازم برای ادامهٔ کار روی **نرم‌افزار Logic Style** است (نه یک آرایشگاه، بلکه محصول نرم‌افزاری که به آرایشگاه‌ها فروخته می‌شود).

---

## بخش ۱ — کلیدها و دسترسی‌ها

### Supabase (دیتابیس اصلی نرم‌افزار)
- **Project ID:** `owgfhhkmlkdpjqlwavsx`
- **Project URL:** `https://owgfhhkmlkdpjqlwavsx.supabase.co`
- **Region:** eu-central-1
- **Publishable Key:** `sb_publishable_xGeaZikMQI8MclH3CnClBg_INoBJ7F-`
- **Anon JWT:** `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im93Z2ZoaGttbGtkcGpxbHdhdnN4Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzQ1MTUyNDgsImV4cCI6MjA5MDA5MTI0OH0.arQzSmczsZX6re-mfC6EcvAs9p3Uf1LdG3AfjjgsZvM`
- **ادمین user id (جدول users):** `89746ed5-14e1-4f0d-9728-24c908ad429c`

### جداول موجود
| جدول | نقش |
|------|-----|
| `users` | کاربران سالن (مشتریان نرم‌افزار) |
| `sessions` | نشست‌های ورود |
| `style_ref_map` | نگاشت عکس مرجع بی‌نام → کد مدل (بخش ریش + کوتاهی زنانه) |
| `store_packages` ⭐جدید | پکیج‌های فروش (Basic €49، Professional €99، Salon €199 — ماهانه/سالانه) |
| `store_orders` ⭐جدید | سفارش‌های اشتراک از سایت فروش |
| `store_messages` ⭐جدید | لاگ پیام‌های پشتیبانی تلگرام (فعلاً باگ دارد، ذخیره نمی‌شود) |

### باکت‌های Storage
- `ref-style beard` (با فاصله) — ۳۴ عکس مرجع ریش، نگاشت‌شده و تست‌شده
- `ref-woman-cut` (با خط تیره) — ۷۳ عکس کوتاهی زنانه، **هنوز نام‌گذاری نشده** (منتظر جدول تطبیق کاربر)
- `style-refs` — عکس‌های مرجع با نام `{کد}.png`

### GitHub
- **Repo:** `github.com/farhadjavanmardi-art/logicstyle` (Public, main)
- ⚠️ **توکن PAT فعلی از کار افتاده** (`Bad credentials`). قبل از هر push جدید باید توکن تازه بسازی:
  GitHub → Settings → Developer settings → Personal access tokens → Generate new token (scope: Contents read/write)
- فایل‌های اصلی: `ls-app.js`, `ls-data.js`, `admin.html` (یا معادل), کاتالوگ کامل مدل‌ها

### Vercel / دامنه
- **دامنه:** `logicstyle-salon.de`
- ⚠️ **پروژه در اکانت Vercel متصل به کلود دیده نمی‌شود.** باید چک کنی این دامنه با کدام لاگین/اکانت Vercel وصل شده — احتمالاً اکانت دیگری است یا اتصال GitHub↔Vercel قطع شده.

### Anthropic Claude API
- `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`

### n8n
- Instance: `javanmardi.app.n8n.cloud` · Project: `PeYANjkEYMUnm9do`

---

## بخش ۲ — کتاب آکادمی (تحویل‌شده)
۴ بخش کامل PDF فارسی: مردانه (۴۰ مدل)، زنانه (۷۲ مدل)، ریش (۳۴ مدل)، رنگ (۸۱ رنگ + مبانی). مجموعاً ۲۲۷ مدل، ۲۶۹ صفحه. اگر فایل‌ها را نداری، بگو دوباره می‌سازم.

## بخش ۳ — فروشگاه Logic Store (تازه ساخته‌شده، جدا از نرم‌افزار اصلی)
- `index.html` — سایت فروش سه‌زبانه (fa/en/de)، پکیج‌ها، فرم سفارش → Supabase
- `admin_store.html` — پنل مدیریت سفارش‌ها
- **workflow n8n «Logic Store — ربات پشتیبانی تلگرام»** (ID: `2a6xNF6HsMl5E7Wb`) — فعال، تست‌شده، پاسخ طبیعی سه‌زبانه با Claude
  - ⚠️ لاگ پیام در `store_messages` کار نمی‌کند (باگ رفع‌نشده)

## بخش ۴ — کارهای باز و ناتمام
1. **نگاشت ۷۳ عکس کوتاهی زنانه** — منتظر جدول تطبیق از کاربر
2. **توکن GitHub منقضی** — باید جدید ساخته شود
3. **پروژهٔ Vercel گمشده** — باید اکانت درست پیدا/وصل شود
4. **لاگ تلگرام Logic Store** — باگ کوچک رفع‌نشده
5. **ایمیل و واتساپ برای Logic Store** — نیاز به اطلاعات دسترسی (Gmail OAuth / WhatsApp Business API) که نداریم
6. **درگاه پرداخت واقعی** — فرم سفارش فقط ثبت درخواست می‌کند، پرداخت واقعی وصل نیست

---

## 🚀 پرامپت شروع چت جدید

```
سلام کلود. می‌خواهم روی نرم‌افزار Logic Style (شبیه‌سازی مو/ریش/رنگ برای سالن‌ها) 
ادامه بدهم. فایل LOGIC_STYLE_HANDOFF.md را ضمیمه کردم — کلیدها، وضعیت جداول، و 
کارهای باز در آن است.

مهم‌ترین مشکلات باز که باید اول حل شوند:
۱) توکن GitHub منقضی شده — باید جدید بسازم و به من بگویی کجا.
۲) پروژهٔ Vercel که logicstyle-salon.de به آن وصل است در اکانت من دیده نمی‌شود.

لطفاً اول فایل را بخوان و خلاصه بده چه داری، بعد کمکم کن این دو مشکل را حل کنیم.
```
