# 如何關閉OneDrive在Client端的文件夾存取權

## 調閱所有使用者的OneDrive URL

※若已有明確需要關閉的使用者清單或單一使用者，請跳過這個步驟，並繼續往下閱讀。 <br>

Step 1. 請以全域管理者或SharePoint 管理員身分登入 [https://admin.microsoft.com](https://admin.microsoft.com)。 <br>

Step 2. 在左方導覽列中選擇「報告 > 使用情況」。<br>

![GITHUB](image/image1.jpg) <br>

Step 3. 進入使用情況後，請往下捲動至 OneDrive 檔案的位置，並點選「檢視更多」。<br>

![GITHUB](image/image2.jpg) <br>

Step 3. 確認清單後，請點選上方的「匯出」連結，以將所有的OneDrive URL匯出 (你可能需要往下捲動至最底端選擇「檢視更多」)。 <br>

![GITHUB](image/image3-1.jpg) <br>

## 透過 PowerShell 關閉Client端文件夾存取權

### 關閉單一使用者

Step 1. 透過系統管理員身分開啟PowerShell ISE

![GITHUB](image/image4.jpg) <br>

Step 2. 安裝 SharePoint Module，請輸入以下指令 (執行過程需要一段時間安裝)，並在過程中點選 **全部皆是(A)** <br>

若執行完成跳出橘色文字之警示訊息，可忽略。

```Install-Module -Name Microsoft.Online.SharePoint.PowerShell```

![GITHUB](image/image5.jpg) <br>

Step 3. 連結 SharePoint Admin Center 請輸入以下指令 <br>

```Connect-SPOService -Url https://xxx-admin.sharepoint.com``` <br>

其中 xxx 位置為您的 SharePoint Admin Center 網址，此網址可於 Microsoft 365 Admin Center中查看，<br>

查看位置為：**Microsoft 365 Admin Center > 系統管理中心 > SharePoint** <br>

進入後之URL即為 SharePoint Admin Center <br>

輸入指令後，請於彈跳出之登入視窗中，登入您的全域管理員或SharePoint管理員帳號<br>

![GITHUB](image/image6.jpg) <br>

Step 4. 最後請輸入以下指令以關閉使用者OneDrive在Client端的文件夾存取權

```$OneDriveSiteURL = "https://xxxxxx-my.sharepoint.com/personal/xxxx_nrosni_onmicrosoft_com"```

```Get-SPOSite -Identity $OneDriveSiteURL | Set-SPOSite -LockState NoAccess```

其中 xxxxxxx 為欲關閉之使用者 OneDrive URL，若不清楚此資訊，可於Microsoft 365 Admin Center中查看，

查看位置為：**Microsoft 365 Admin Center > 使用者 > 作用中的使用者 > 選擇使用者 > OneDrive > 產生連結***

![GITHUB](image/image7.jpg) <br>

### 關閉多位使用者
