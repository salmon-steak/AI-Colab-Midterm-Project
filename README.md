# 115 人工智慧 期中報告：Google Colab 實作專案

## 專案簡介
本專案為人工智慧課程期中報告，主要實作並記錄如何在 Google Colaboratory 雲端環境中配置 GPU 資源、掛載 Google Drive 雲端硬碟、載入 CIFAR-10 資料集，並透過 PyTorch 官方預訓練模型 ResNet-18 於 GPU 上完成前向推論（Inference）之完整 AI 流程。

## 個人資訊
- **姓名**：劉彥甫
- **學號**：11225034

## 實作環境與規格
- **雲端運算平台**：Google Colaboratory
- **運算核心**：NVIDIA Tesla T4 GPU
- **開發語言**：Python 3.10+
- **核心套件**：PyTorch / Torchvision / NumPy

---

## 實作流程與核心步驟說明

### 1. 檢查 GPU 硬體資源
於 Google Colab 選單列點選「執行階段」->「變更執行階段類型」，選取 T4 GPU，並透過 nvidia-smi 指令確認系統成功分配到顯示卡資源。

### 2. 掛載雲端硬碟與設定工作目錄
為確保執行過程中的資料持久化儲存，授權掛載個人 Google Drive，並建立與切換至專屬的專案資料夾作為工作目錄。

### 3. 驗證開發環境與運算裝置
載入 PyTorch 相關套件，檢查版本資訊與 CUDA 加速是否可用，並將運算裝置明確指定為 GPU（cuda），以確保後續運算能享有硬體加速。

### 4. 下載與預處理示範資料集
利用 torchvision 內建功能下載 CIFAR-10 小型影像分類資料集，進行影像縮放、張量轉換與標準化前處理，並設定資料批次載入器（DataLoader）。

### 5. 載入預訓練模型並執行 GPU 推論
匯入官方預訓練的 ResNet-18 模型權重並切換至評估模式（eval），將影像張量移至 GPU 記憶體中進行前向傳播（Forward Pass）運算，最終成功輸出預測結果的維度資訊。

---

## 專案檔案清單
- `AI_Colab_Workflow.ipynb`：包含 5 個執行步驟輸出與 GPU 日誌的 Colab 筆記本程式檔。
- `README.md`：專案報告說明文件。
