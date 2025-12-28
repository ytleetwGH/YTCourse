---
layout: default
title: YTLee課程講義 - 首頁
---

# 歡迎來到 YTLee 課程講義平台

<style>
    .card-container {
        display: flex;
        gap: 20px;
        margin-top: 30px;
    }
    .card {
        flex: 1;
        padding: 20px;
        /* 將背景改為透明或深灰色，邊框改為綠色 */
        border: 2px solid #2ecc71; 
        border-radius: 12px;
        background-color: #1a1a1a; 
        text-align: center;
        transition: transform 0.2s, box-shadow 0.2s;
        text-decoration: none !important;
        /* 將文字顏色改為 Hacker 綠 */
        color: #2ecc71 !important; 
    }
    .card:hover {
        transform: translateY(-5px);
        box-shadow: 0 0 15px #2ecc71;
        background-color: #262626;
    }
    .card h2 {
        margin-top: 0;
        color: #2ecc71;
    }
    .btn-start {
        display: inline-block;
        margin-top: 15px;
        padding: 8px 20px;
        background-color: #2ecc71;
        color: #000 !important;
        border-radius: 5px;
        font-weight: bold;
    }
</style>

<div class="card-container">
    <a href="/YTCourse/matlab/ch01" class="card">
        <h2>📊 MATLAB</h2>
        <p>矩陣運算、數據繪圖與科學計算基礎。</p>
        <span class="btn-start">開始學習</span>
    </a>

    <a href="/YTCourse/ai/ch01" class="card">
        <h2>🤖 AI 課程</h2>
        <p>機器學習導論與神經網路實作教學。</p>
        <span class="btn-start">開始學習</span>
    </a>
</div>

---
### 📢 最新更新
- **2025-12-28**: 成功切換為 Hacker 主題風格。
