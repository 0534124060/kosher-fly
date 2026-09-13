כשר פליי — אתר עם מערכת ניהול מלאה
========================================

מה יש בחבילה
-------------
index.html               האתר
content/site.json        כל הטקסטים והמידע של האתר
admin/index.html         מערכת הניהול בכתובת /admin/
images/                  לוגו ותמונות שתעלו דרך מערכת הניהול
netlify.toml             הגדרות Netlify

אחרי ההקמה הראשונית, אין צורך להעלות ZIP בכל שינוי.
מערכת הניהול שומרת שינוי ב-GitHub, ו-Netlify מפרסם אותו אוטומטית.

שלב 1 — יצירת מאגר GitHub
--------------------------
1. היכנסו ל-GitHub וצרו Repository חדש, למשל: kosher-fly
2. חלצו את קובץ ה-ZIP הזה במחשב.
3. העלו ל-Repository את כל תכולת התיקייה, כולל:
   admin
   content
   images
   index.html
   netlify.toml
4. ודאו שענף ברירת המחדל נקרא main.

שלב 2 — חיבור האתר ל-Netlify
-----------------------------
חשוב: לגרסה עם מערכת ניהול לא משתמשים ב-Drag & Drop של ZIP.
האתר צריך להיות מחובר ל-GitHub.

1. ב-Netlify לחצו Add new project.
2. בחרו Import an existing project.
3. בחרו GitHub.
4. בחרו את repository של kosher-fly.
5. אין צורך ב-Build command.
6. Publish directory: .
7. לחצו Deploy.

מרגע זה כל commit ב-GitHub יעלה אוטומטית לאתר.

שלב 3 — הפעלת כניסה מאובטחת ל-CMS דרך GitHub
---------------------------------------------
המערכת משתמשת ב-Decap CMS עם GitHub backend.

ב-GitHub:
1. Settings של חשבון GitHub.
2. Developer settings.
3. OAuth Apps.
4. New OAuth App.
5. Application name: Kosher Fly Admin
6. Homepage URL: כתובת האתר שלכם ב-Netlify
7. Authorization callback URL:
   https://api.netlify.com/auth/done
8. צרו את האפליקציה.
9. העתיקו Client ID וצרו Client Secret.

ב-Netlify:
1. היכנסו לפרויקט.
2. Project configuration.
3. Access & security.
4. OAuth.
5. Authentication Providers / Install Provider.
6. בחרו GitHub.
7. הדביקו Client ID ו-Client Secret ושמרו.

שלב 4 — כניסה למערכת הניהול
----------------------------
1. פתחו:
   https://YOUR-SITE.netlify.app/admin/
2. בפעם הראשונה תתבקשו להזין:
   username/repository

דוגמה:
אם כתובת GitHub היא:
https://github.com/moshe/kosher-fly

יש להזין:
moshe/kosher-fly

3. לאחר מכן התחברו באמצעות GitHub.
4. תופיע קטגוריה: "תוכן האתר".
5. היכנסו ל-"כל הטקסטים וההגדרות".

מה אפשר לשנות במערכת
---------------------
- שם האתר והסלוגן
- הלוגו
- כל פס ההודעות העליון
- כל התפריט
- כל הכותרות והפסקאות
- תמונת הרקע הראשית
- דוגמת המחיר
- כל שלבי "איך זה עובד"
- מחיר השירות ליום
- כל טקסטי הטופס
- שמות שדות הטופס, Placeholder ואפשרויות הבחירה
- כתובת המייל שמקבלת את הטפסים
- הוספה / מחיקה / שינוי סדר של יעדים
- תמונה לכל יעד
- אטרקציות ומידע יהודי לכל יעד
- שאלות ותשובות
- טקסטים בתחתית האתר

איך מפרסמים שינוי
-----------------
1. משנים במערכת.
2. לוחצים Save / Publish.
3. Decap CMS שומר את content/site.json ב-GitHub.
4. Netlify מזהה את השינוי ומפרסם אוטומטית.
5. בדרך כלל תוך זמן קצר השינוי יופיע באתר.

שינוי תמונות
------------
בשדה תמונה לחצו Choose an image והעלו קובץ.
הקובץ נשמר ב-images/uploads ומפורסם עם האתר.

החלפת מחשב / שינוי Repository
------------------------------
מערכת הניהול זוכרת את שם ה-Repository בדפדפן.
אם נכנסים ממחשב חדש היא תשאל שוב.

כדי לשנות את ה-Repository:
פתחו:
https://YOUR-SITE.netlify.app/admin/?setup=1

הערה חשובה
-----------
אל תפרסמו Client Secret בתוך קבצי האתר.
הוא נשמר רק בתוך הגדרות OAuth של Netlify.
