# Abrar Math Coaching — Android WebView + Google Apps Script Bundle

## 1. Setup Google Apps Script (`apps-script/Code.gs`)
1. Open [script.google.com](https://script.google.com) -> **New Project** -> paste `apps-script/Code.gs`.
2. Update `TEACHER_MOBILE` (`01616397272`) and `TEACHER_PIN` at the top of `Code.gs`.
3. Select `setupCoachingSheetAndForm` and click **Run** once. It creates **Abrar Math Coaching Sheet** and your structured **Google Form** automatically (check Execution Log for both URLs).
4. Click **Deploy -> New deployment -> Web app** (`Execute as: Me`, `Who has access: Anyone`) and copy the `/exec` URL.

## 2. Web Portal View (`web-portal/index.html`)
- **Teacher Login:** Mobile Number (`01616397272`) + Password (`abrar2026` in demo, or your `TEACHER_PIN`).
- **Student Login:** Guardian WhatsApp Number only (e.g. `01812001122`, `01711334455`, `01811445566` in demo).
- Paste your `/exec` URL in **Admission QR & Sync** to sync live with Google Sheets.

## 3. Android WebView App (`android-webview/`)
1. Create a new Android Studio project (`com.abrarmath.coaching`, minSdk 24).
2. Copy `MainActivity.kt`, `ExamAlarmReceiver.kt`, and `AndroidManifest.xml`.
3. Copy `web-portal/index.html` into `app/src/main/assets/index.html` (or point `webView.loadUrl(...)` to your GitHub Pages URL).
4. Build APK — includes **Print/Save PDF**, **WhatsApp `wa.me` deep links**, **Camera/Photo upload**, and **12-hour `AlarmManager` exam notifications**.
