# 人工智慧期中作業：Google Colab 執行影片目標追蹤

## 組員
- 11125013 郭慧庭
- 11125032 林欣儀
- 11125036 夏振凱

---

## 一、執行目的
本次作業目標為：在 Google Colab 上執行影片目標追蹤程式，使電腦能在影片中辨識並持續追蹤同一物體。  
我們依照老師提供教學網站的流程進行嘗試，並整理出可重複執行的操作步驟。

教學來源：  
https://blog.csdn.net/qq_30347421/article/details/104534297

---

## 二、實際操作流程（依老師教學整理）

> 教學來源：  
> https://blog.csdn.net/qq_30347421/article/details/104534297

### Step 1. 開啟 Colab
https://colab.research.google.com/

### Step 2. 掛載 Google Drive
左側 **Files** → **Mount Drive**，或執行：
```python
from google.colab import drive
drive.mount('/content/drive')
```

### Step 3. 切換到程式所在資料夾
```bash
%cd /content/drive/MyDrive/video_analyst/
```

### Step 4. 安裝必要套件
```bash
pip install -r requirements.txt
```

### Step 5. 執行測試程式
```bash
python tools/test.py
```
執行後會讀取模型與影片並嘗試進行追蹤。

---

## 三、執行畫面（截圖）

| 步驟 | 截圖檔名 | 說明 |
|---|---|---|
| 掛載 Drive 成功 | assets/step2_mount.png | 看到「Mounted at /content/drive」字樣 |
| 切換資料夾 | assets/step3_cd.png | `pwd` 或 `cd` 後出現正確路徑 |
| 安裝套件 | assets/step4_pip.png | `pip install -r requirements.txt` 的安裝畫面 |
| 執行 test.py | assets/step5_test.png | 執行中的畫面或訊息（正常或中斷皆可） |

---

## 附件
小組成員的步驟紀錄（供參考）：  
https://drive.google.com/file/d/1W4ejb55Ll4tb3B0jU2w1ABNdjUYuo6yi/view?usp=sharing
