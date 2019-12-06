# ESL Face_Recognition

連向伺服器

```
ssh <User_Name>@<Server_Ip>
```

### 連進伺服器後

為了方便demo，使用tmux來同時開啟多個bash，這樣一來就不用一直ssh進伺服器來操作

首先確保自己在tmux的第一個頁面，請輸入以下指令。

```
tmux attach-session -t server_demo
```

### 熟悉tmux指令

輸入以下指令來切換視窗，或者使用滑鼠點擊視窗來執行程式

```
<C-o> + j   （往下移動cursor)
```

```
<C-o> + k    (往上移動cursor)
```

```
<C-o> + h    (往左移動cursor)
```

```
<C-o> + l    (往右移動cursor)
```

### 開啟人臉辨識伺服器

視窗切到目標位置後，便可開啟伺服器

```
sudo python server8800.py
```

```
sudo python server8811.py
```

```
sudo python server8822.py
```

```
sudo python server8833.py
```

```
sudo python server8844.py
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
sudo python Balance.py
```

之後輸入使用者密碼（因為憑證放在網站根目錄底下，必須要root權限才能進入存取）

### 開啟Chrome並輸入以下URL

連向分流器(開在port 9000)

```
https://esldlep.cs.ccu.edu.tw:9000/
```

按下Enter之後，即可開始進行辨識。

### 離開tmux

```
<C-o> + d     (d是detach的意思）
```
