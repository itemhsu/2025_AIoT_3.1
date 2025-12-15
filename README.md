# Hour 1：AIoT 是什麼？為什麼要用 ESP32-P4？
（課程時間：60 分鐘）

---

## 一、課程目標（Learning Objectives）

完成本小時課程後，學生應能：

- 理解 **AIoT（Artificial Intelligence of Things）** 的核心概念  
- 分辨 **Cloud AI** 與 **Edge AI** 的差異與取捨  
- 理解為什麼 **AI 必須往邊緣端（Edge）移動**  
- 認識 **ESP32-P4 在 AIoT 架構中的定位與價值**  
- 建立「**AI 只是系統中的一個模組，不是全部**」的正確觀念  

---

## 二、什麼是 AIoT？

### 2.1 IoT 的基本定義

**IoT（Internet of Things）** 的核心是三件事：

1. **感測（Sense）**  
   - 攝影機、IMU、溫度、聲音、電流、位置  
2. **連線（Connect）**  
   - Wi-Fi、Ethernet、BLE、LTE  
3. **控制（Act）**  
   - 顯示、警示、儲存、馬達、繼電器  

傳統 IoT 系統流程：

- 感測 → 上傳資料 → 雲端分析 → 回傳指令

---

### 2.2 為什麼要加上 AI？

加入 AI 之後，系統能力產生質變：

- 不只量測「數值」
- 開始理解「語意」

範例（影像）：
- 不是「畫面」，而是「畫面中有人」
- 不是「像素變化」，而是「行為或事件」

---

### 2.3 AIoT 的定義

**AIoT = IoT + AI（在系統中）**

重點說明：  
AIoT 不是把模型跑起來，而是把 AI 納入系統決策流程。

典型 AIoT 系統包含：

- 感測器（Camera / IMU / Mic）
- 邊緣 AI 推論
- 即時決策
- 人機互動（UI）
- 在地或雲端儲存

---

## 三、Cloud AI vs Edge AI

### 3.1 Cloud AI 架構

```
Sensor → Internet → Cloud AI → Internet → Device
```

**優點**
- 模型大、精度高
- 集中管理、更新方便

**缺點**
- 延遲高
- 必須依賴網路
- 隱私與頻寬成本問題

---

### 3.2 Edge AI 架構

```
Sensor → Edge Device（AI）→ Decision / Action
```

**優點**
- 即時反應（ms 級）
- 不依賴網路
- 隱私保護佳

**缺點**
- 硬體資源有限
- 模型需量化與優化
- 系統整合較複雜

---

### 3.3 AIoT 的選擇原則

| 情境 | 適合位置 |
|---|---|
| 即時反應 | Edge |
| 大量分析 | Cloud |
| 隱私敏感 | Edge |
| 長期趨勢 | Cloud |

結論：AIoT 的關鍵在於分工，而非二選一。

---

## 四、為什麼 MCU 也要跑 AI？

### 4.1 傳統迷思

- AI 只能跑在 GPU / Server
- MCU 只能做控制

這些觀念在 Edge AI 時代已不完全正確。

---

### 4.2 真實需求

- 攝影機與感測器遍佈各處
- 全部上雲成本過高
- 即時反應不能等待網路
- 隱私資料不能外流

因此，AI 必須下放到邊緣裝置。

---

### 4.3 MCU 跑 AI 的三個條件

1. 輕量化模型（Quantization）
2. 足夠的記憶體
3. 正確的系統架構

ESP32-P4 即是為此設計。

---

## 五、ESP32-P4 在 AIoT 中的定位

### 5.1 一句話定位

ESP32-P4 是一顆 **Vision-first Edge AI MCU**。

---

### 5.2 為什麼適合 AIoT

ESP32-P4 可以同時執行：

- Camera（影像感測）
- Edge AI（YOLO / COCO）
- UI（LVGL）
- Storage（SD / NVS）
- 其他感測（IMU）

這是完整 AIoT 系統，而非 Demo。

---

### 5.3 教學價值

學生可以實際看到：

- 資料如何進來
- AI 如何推論
- 結果如何影響系統行為

---

## 六、課程範例系統總覽

本課程將使用以下系統：

- ESP32-P4 + Camera
- COCO Object Detection
- UI 互動介面
- 本地儲存（SD / NVS）

資料流程：

```
Camera
  ↓
Frame
  ↓
Edge AI
  ↓
Detection Result
  ↓
UI / Decision / Storage
```

---

## 七、課堂討論

請學生思考：

1. 哪些功能一定要在 Edge？
2. 哪些資料適合送上 Cloud？
3. 沒有網路時系統是否仍有價值？

---

## 八、本小時重點整理

- AIoT 是系統工程
- Edge AI 解決延遲、隱私與成本
- ESP32-P4 讓 MCU Vision AI 成為可能

---

## 九、Next Hour 預告

**Hour 2：從 app_main() 開始拆解 AIoT 系統架構**
