# מחלץ הכתבות

אפליקציית דפדפן סטטית לחילוץ מדור "רבי אישי" של טמה חורושוכין מתוך עלון "מובילות".

## הפעלה מקומית
פתחו את התיקייה ב-VS Code והפעילו `index.html` דרך Live Server. דרוש חיבור לאינטרנט לטעינת PDF.js.

## פרסום ב-GitHub Pages
1. צרו מאגר GitHub חדש (למשל `article-extractor`).
2. העלו אליו את שלושת הקבצים `index.html`, `style.css`, `app.js` לשורש המאגר.
3. פתחו Settings → Pages → Build and deployment → Deploy from a branch.
4. בחרו `main` ו-`/(root)` ולחצו Save.
5. הכתובת תהיה `https://USERNAME.github.io/article-extractor/` (החליפו USERNAME בשם המשתמש שלכם).

## מגבלות
זיהוי העמוד מבוסס על שכבת הטקסט של PDF. החיתוך הראשוני מכוון לעיצוב הגיליון שסופק. במקרה של שינוי פריסה או PDF סרוק, יש לבחור את העמוד ולכוון את המסגרת ידנית. הקובץ אינו נשלח לשרת.
