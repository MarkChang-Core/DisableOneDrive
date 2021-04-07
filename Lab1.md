# 如何關閉OneDrive在Client端的文件夾存取權

## 調閱所有使用者的OneDrive URL

※若已有明確需要關閉的使用者清單或單一使用者，請跳過這個步驟，並繼續往下閱讀。 <br>

Step 1. 請以全域管理者或SharePoint 管理員身分登入 [https://admin.microsoft.com](https://admin.microsoft.com)。 <br>

Step 2. 在左方導覽列中選擇「報告 > 使用情況」。<br>

![GITHUB](image/image1.jpg) <br>

Step 3. 進入使用情況後，請往下捲動至 OneDrive 檔案的位置，並點選「檢視更多」。<br>

![GITHUB](image/image2.jpg) <br>

Step 3. 確認清單後，請點選上方的「匯出」連結，以將所有的OneDrive URL匯出 (你可能需要往下捲動至最底端選擇「檢視更多」)。 <br>

![GITHUB](image/image3.jpg) <br>

## 透過SPO PowerShell 關閉Client端文件夾存取權

### 關閉單一使用者



### 關閉多位使用者
