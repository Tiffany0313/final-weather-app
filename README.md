## 如何更新日出日落檔案

由於中央氣象局提供的日出日落時間資料有限（通常是兩年內），所以一旦過了這個時間就需要重新抓取。這裡已經寫好對應的指令來自動更新，使用者只需要：

在專案根目錄建立 .env 並且放入 API 授權碼
# .env
REACT_APP_API_AUTHORIZATION_KEY=CWB-***-***
接著即可透過下述指令自動更新資料：
$ npm run build:sunrise-sunset
如果想要手動更新檔案，則可以：

到中央氣象局網站抓取「日出日落時刻」的資料，並將資料存檔到 src/scripts/generateSunriseAndSunsetData/A-B0062-001.json

執行 npm run build:process-sunrise-sunset，執行完畢後，就可以在 src/utils/ 中有一份 sunrise-sunset.json 檔案，這檔案就是我們要的日出日落時間資料。
