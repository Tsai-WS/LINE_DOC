
資訊來源：https://developers.line.biz/en/docs/liff/release-notes/

------------

# 2019/10/16 LIFF v2 released
Use the latest version of LIFF
>LIFF v1 will be deprecated.

參考 LIFF SDK 說明文件
**LINE Front-end Framework**
https://developers.line.biz/en/reference/liff/


## LIFF apps now run in external browsers
- LIFF 功能可以外部瀏覽器運作
- 有限制使用，無法開啟 QR cdoe 讀取器與發送訊息

## Get user profile and email
- 在建立 LIFF 中可以設定
- 使用 liff.getProfile() 方式無法獲得 email 


## Read QR codes
- 必須在 LIFF 設定中，啟用 ScanQR 才能使用
- 必須在 LINE app 內開啟 LIFF 才能使用
- 會開啟 LINE app 加入好友掃描器

## Get LIFF app environment information
- 可以獲得開啟 LIFF 統資訊,liff.getOS()
- 可以獲得開啟 LIFF 是否在 LINE app 內,liff.isInClient()
- 可以獲得用戶語系,liff.getLanguage()

-----

## LIFF 設定頁面更新
![](https://github.com/Tsai-WS/LINE_DOC/blob/master/LIFF/img/1571236877634.jpg)

新增項目
- Scope
- Bot_prompt
- Option

Scope , Bot_prompt 設定與LINE login 設定相同，參考LINE Login 說明文件

**Scope,Bot_prompt** 參數說明
https://developers.line.biz/en/docs/line-login/web/integrate-line-login/

**特別注意 liff.sendMessages() 功能**
- 需要在 LIFF 設定中打開 Scope.chat_message.write 權限且用戶同意後才能使用

**特別注意 liff.scanCode() 功能**
- 需要在 LIFF 設定中打開 Option.ScanQR 權限且用戶同意後才能使用

------------

## 實際測試 LIFF 2.0 新功能 Read QR codes
參考: https://developers.line.biz/en/docs/liff/
> Trying the LIFF starter app
Follow the instructions in the README.md for the line-liff-v2-starter GitHub repository.
https://github.com/line/line-liff-v2-starter/blob/master/README.md

![](https://github.com/Tsai-WS/LINE_DOC/blob/master/LIFF/img/317998.jpg)
官方測試工具是使用 nodejs 運作，如果不想安裝 nodejs 直接跑前端的話
只需要使用到 **/line-liff-v2-starter/public/** 資料夾內的檔案即可

### 使用說明使用說明

#### 使用 nodejs 運作
請設定環境變數 **MY_LIFF_ID={liffId}**

##### 什麼是 LIFFID ?
建立 LIFF app 後，會獲得 LIFF app 網址
LIFF URL line://app/{liffId}

#### 直接使用 public 檔案
請修改 liff-starter.js 內
```javascript
    const useNodeJS = false;   // 設定 false
    const defaultLiffId = "";   // 填寫 LIFF ID
```
