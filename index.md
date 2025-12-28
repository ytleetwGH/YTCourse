---
layout: default
title: HOME
---

# YTLee課程講義

請點選下方區塊開始學習。

<style>
    
/* 隱藏 Architect 主題的藍色頁首 */
header {
    display: none !important;
}    

/* 隱藏 Architect/Hacker 主題右側的按鈕與側邊資訊 */
aside#sidebar {
    display: none !important;
}

/* 針對某些版本的主題，按鈕可能在 header 或特定的 section 內 */
.button, .view {
    display: none !important;
}

/* 讓主內容區域自動填滿，不再留出右側空間 */
#main_content {
    width: 100% !important;
    max-width: 100% !important;
    margin-right: 0 !important;
}
/* 隱藏頁底維護者與 GitHub Pages 產生資訊 */
footer, .site-footer {
    display: none !important;
}

/* 調整主內容區域的上方間距，確保內容不會頂到最上方 */
.main-content {
    padding-top: 50px;
}
    
    .card-container {
        display: flex;
        gap: 20px;
        margin-top: 30px;
    }
    .card {
        flex: 1;
        padding: 20px;
        border: 1px solid #e0e0e0;
        border-radius: 12px;
        background-color: #ffffff;
        text-align: center;
        transition: transform 0.2s, box-shadow 0.2s;
        text-decoration: none !important;
        color: #333 !important;
    }
    .card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        background-color: #f8fbff;
    }
    .card h2 {
        margin-top: 0;
        color: #007bff;
    }
    .card p {
        font-size: 0.9em;
        color: #666;
    }
    .btn-start {
        display: inline-block;
        margin-top: 15px;
        padding: 8px 20px;
        background-color: #007bff;
        color: white !important;
        border-radius: 5px;
        font-weight: bold;
    }
</style>

<div class="card-container">
    <a href="./matlab/ch01" class="card">
        <h2>📊 MATLAB</h2>
        <p>矩陣運算、數據繪圖與科學計算基礎。</p>
        <span class="btn-start">開始學習</span>
    </a>

    <a href="./ai/ch01" class="card">
        <h2>🤖 AI 課程</h2>
        <p>機器學習導論與神經網路實作教學。</p>
        <span class="btn-start">開始學習</span>
    </a>
</div>

---

### 📢 最新更新
- **2025-12-28**: 新增 AI 課程第二章「神經網路」。
- **2025-12-28**: 修正 MATLAB 側邊欄導覽連結。
