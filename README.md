# ESL Face_Recognition

連向伺服器

```
ssh <User_Name>@<Server_Ip>
```

### 連進伺服器後

為了方便demo，使用tmux來同時開啟多個bash，這樣一來就不用一直ssh進伺服器來操作

首先確保自己在tmux在第一個頁面，請輸入以下指令。

```
tmux attach-session -t server_demo
```

```
<C-o> + 1     (按下Ctr+o+1)
```

### 將資料庫檔案更新

```
rm table.db
```

完成後，創建資料庫

```
python Create_Table.py
```

### 開啟分流器

```
<C-o> + 1
```

```
sudo python Balance.py
```

之後輸入使用者密碼（因為憑證放在網站根目錄底下，必須要root權限才能進入存取）

### 開啟後端辨識伺服器

輸入以下指令來切換視窗，或者使用滑鼠點擊視窗來執行程式

```
<C-o> + j
```

這時視窗會切到下方，便可開啟第一隻伺服器

```
sudo python server8800.py
```
若需開啟多個伺服器，就將視窗切到第二個頁面和第三個頁面，分別重複上面步驟來開啟伺服器。

### 開啟Chrome並輸入以下URL

連向分流器(開在port 9000)

```
https://esldlep.cs.ccu.edu.tw:9000/
```

按下Enter之後，即可開始進行辨識。
