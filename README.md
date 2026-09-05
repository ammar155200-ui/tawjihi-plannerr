# خطة التوجيهي — بناء APK

## الطريقة الأسرع (بدون تثبيت أي شي) — GitHub Actions

1. اعمل حساب على github.com إذا ما عندك.
2. اضغط **New repository** → سمّيه `tawjihi-planner` → **Public** → Create.
3. اضغط **uploading an existing file** وارفع كل محتويات هذا المجلد
   (`www/`, `package.json`, `capacitor.config.json`, `.github/`) → Commit.
4. افتح تبويب **Actions** → اختر **بناء APK** → **Run workflow**.
5. استنى 5–10 دقائق، وبعدها من نفس الصفحة نزّل **tawjihi-planner-apk**.
6. فك الضغط، وحوّل الملف `app-debug.apk` لهاتفك وثبّته
   (لازم تفعّل «تثبيت من مصادر غير معروفة»).

## الطريقة المحلية (إذا عندك Android Studio)

```bash
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
# الناتج: android/app/build/outputs/apk/debug/app-debug.apk
```

## بدون APK أصلًا — تثبيت كتطبيق (PWA)

افتح `www/index.html` من أي استضافة (أو GitHub Pages)، وبعدها من متصفح
كروم على الأندرويد: القائمة ⋮ → **تثبيت التطبيق / إضافة إلى الشاشة الرئيسية**.
بيصير عنده أيقونة ويفتح بملء الشاشة بدون شريط متصفح، ويشتغل بدون إنترنت.

## ملاحظات

- كل بياناتك بتنحفظ على جهازك (localStorage) — ما في سيرفر ولا حساب.
- تبويب «مساعد» بده مفتاح Anthropic API تحطه مرة وحدة من:
  الإعدادات ← مفتاح المساعد الذكي. باقي التطبيق بيشتغل بدونه عادي.
- التطبيق هو نفسه بالضبط بدون أي تغيير في الميزات.
