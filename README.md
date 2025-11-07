# 人工智慧期中作業：Google Colab 影片目標追蹤

## 組員
- 11125013 郭慧庭
- 11125032 林欣儀
- 11125036 夏振凱

---

## 一、程式目的
程式的執行目標是在 Google Colab 上執行影片目標追蹤。  
我們先依照題目提供的示範流程操作，但因環境差異導致無法正常執行，  
因此整理可在 Colab 中正常運作的替代追蹤方法，並比較其差異。

題目教學來源：  
https://blog.csdn.net/qq_30347421/article/details/104534297

測試影片來源：  
https://pixabay.com/videos/search/people%20walking/?utm_source=chatgpt.com

---

## 二、題目原始方法（無法於 Colab 完整執行）

Notebook：  
https://colab.research.google.com/drive/1W4ejb55Ll4tb3B0jU2w1ABNdjUYuo6yi

主要執行流程：


## 三、可在 Colab 成功執行的方法

### 方法 1：自動找人 + CSRT 追蹤
Notebook：  
https://colab.research.google.com/drive/1myJMZpZqiKZTzWcI_MTvekDEtF_hy_na

**概念說明：**  
1. 使用 HOG 偵測第一幀中的人物  
2. 擷取偵測到的初始框  
3. 使用 CSRT 持續追蹤該人物

**本組執行成果影片：**  
`videos/auto_csrt_tracked.mp4`  
(已成功輸出，可直接播放)

**成果截圖：**  
![assets/step5_result.jpg](assets/step5_result.jpg)

---

### 方法 2：骨架偵測追蹤（MediaPipe Pose）
Notebook：  
https://colab.research.google.com/drive/1H91ZppZwKA_QGpaH-PmXRAr2GZKtwkSJ

**概念說明：**  
使用 MediaPipe Pose 偵測人體 33 個關鍵點，並繪製骨架來呈現動作軌跡。

**本組執行情況：**  
程式可成功執行並逐幀繪製骨架。  
影片已成功產生，檔名為 `pose_tracked.mp4`。

（本組影片檔案較大，將於口頭報告時展示。）

---

### 方法 3：YOLO 偵測 + 多人 CSRT 追蹤
Notebook：  
https://colab.research.google.com/drive/1Q5uEcF9hB27QALWkMBR2JAYDF9GiEdd3

**概念說明：**  
1. YOLO 用於偵測畫面中的所有人物  
2. 為每位人物建立一個 CSRT 追蹤器  
3. 可同時追蹤多人，適用於群體場景

**本組執行情況：**  
程式成功運作並可輸出多人追蹤影片 `test-2_tracked.mp4`。  
（同樣於報告中展示成果。）

---

## 四、三種方法比較

| 方法 | 偵測方式 | 優點 | 缺點 | 適合情況 |
|---|---|---|---|---|
| 方法 1 | HOG + CSRT | 單人追蹤穩定、設定簡單 | 僅適用單人 | 單人影片追蹤 |
| 方法 2 | MediaPipe Pose | 可觀察動作與姿勢 | 骨架線條可能抖動 | 運動 / 舞蹈分析 |
| 方法 3 | YOLO + 多 CSRT | 可同時追蹤多人 | 計算量較大、較慢 | 多人行為追蹤 |

---

## 五、執行截圖（本組紀錄）

| 描述 | 檔案 |
|---|---|
| Drive 掛載成功 | `step2_mount.jpg` |
| 影像追蹤結果截圖 | `step5_result.jpg` |

---

## 六、結論
本次實作比較三種追蹤方式：  
- **方法 1** 在本次環境下最簡單且穩定  
- **方法 2** 適用於需要觀察人體動作的場景  
- **方法 3** 可多人追蹤，但計算量較高  

可依實際應用情境選擇合適的模型與追蹤策略。
