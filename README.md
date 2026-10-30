# מחלץ הכתבות

אפליקציית דפדפן סטטית לחילוץ מדור "רבי אישי" של טמה חורושוכין מתוך עלון "מובילות".

## הפעלה מקומית
פתחו את התיקייה ב-VS Code והפעילו `index.html` דרך Live Server. דרוש חיבור לאינטרנט לטעינת PDF.js.

## פרסום ב-GitHub Pages
1. צרו מאגר GitHub חדש (למשל `article-extractor`).
2. העלו אליו את הקבצים `index.html`, `style.css`, `app.js`, `google-drive-config.js` לשורש המאגר.
3. פתחו Settings → Pages → Build and deployment → Deploy from a branch.
4. בחרו `main` ו-`/(root)` ולחצו Save.
5. הכתובת תהיה `https://USERNAME.github.io/article-extractor/` (החליפו USERNAME בשם המשתמש שלכם).

## הודעת הורדה
לאחר יצירת התמונה, תופיע הודעת Snackbar בדף כשההורדה נשלחת לדפדפן. הדפדפן אינו מדווח לאתר אם הקובץ נשמר בפועל; אפשר לבדוק את מצב ההורדה בהתראות הדפדפן או בתיקיית ההורדות.

## חיבור Google Drive
העלאה ל־Drive משתמשת ב־Google Picker ובהרשאת `drive.file`, שמוגבלת לקבצים ולתיקיות שהמשתמשת בוחרת. נדרש להגדיר ב־Google Cloud פרויקט עם Google Drive API ו־Google Picker API פעילים, מסך הסכמה ל־OAuth, OAuth Client ID מסוג Web, API Key ו־Project Number.

1. ב־Google Cloud Console צרו או בחרו פרויקט והפעילו **Google Drive API** ו־**Google Picker API**.
2. הגדירו את מסך ההסכמה של OAuth. אם האפליקציה במצב Testing, הוסיפו את חשבון Google שלכם כ־Test user.
3. צרו OAuth Client ID מסוג **Web application**. הוסיפו תחת **Authorized JavaScript origins** את `https://klydigitaly.github.io` (ללא נתיב).
4. צרו API Key. הגבילו אותו ל־Websites עם `https://klydigitaly.github.io/*` וגם `https://docs.google.com/*`; הגבילו את ה־APIs ל־Google Picker API ול־Google Drive API.
5. מצאו את **Project Number** תחת Project info ב־Google Cloud.
6. מלאו את `apiKey`, `clientId`, ו־`appId` (Project Number) בקובץ `google-drive-config.js`. אין להוסיף Client Secret לקוד.
7. פרסמו את `google-drive-config.js` ואת יתר הקבצים ב־GitHub Pages. לחצו על "שמירה ב־Google Drive", התחברו ובחרו את תיקיית היעד בפעם הראשונה. הבחירה נשמרת בדפדפן.

ה־PDF מעובד מקומית. רק תמונת ה־PNG נשלחת ל־Drive אחרי בחירת המשתמשת. העלאה ל־Drive אינה נתמכת בפתיחת הקובץ ישירות מהמחשב (`file://`); יש להשתמש ב־GitHub Pages או בשרת מקומי דרך `localhost`.

## מגבלות
זיהוי העמוד מבוסס על שכבת הטקסט של PDF. החיתוך הראשוני מכוון לעיצוב הגיליון שסופק. במקרה של שינוי פריסה או PDF סרוק, יש לבחור את העמוד ולכוון את המסגרת ידנית.
