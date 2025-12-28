---
layout: page
title: 建立gitHub page步驟
---

# 使用Gemini建立gitHub page步驟
建立新的網站並建立產生步驟，包含matlab、AI兩個課程

Q1.
1.使用GitHub Pages建立步驟

2.說明必須建立的.md檔步驟

3.建立matlab、AI兩個課程的前兩章內容步驟

4.使用HTML語法 加入matlab、AI兩個課程「浮動側邊欄」步驟

A1.

針對 GitHub Pages + Jekyll 完整架構的產生手冊。我們將利用「自動化模板」技術，讓 MATLAB 和 AI 課程擁有各自獨立且專業的側邊欄位。
## 第一階段：GitHub Pages 建立步驟
1.建立儲存庫：在 GitHub 建立名為 fileName 的 Repository。

2.建立設定檔：在根目錄建立 _config.yml，貼入以下代碼以開啟課程集合功能：
### YAML
```
title: 我的課程平台
theme: jekyll-theme-architect

collections:
  matlab:
    output: true
    permalink: /matlab/:name
  ai:
    output: true
    permalink: /ai/:name
```

3.啟用頁面：進入 Settings > Pages，確認 Branch 為 main 並點擊 Save。

## 第二階段：建立側邊欄模板 (HTML/CSS)
建立資料夾 _layouts 並在其中建立 course_layout.html。

這個檔案會根據你所在的資料夾自動切換側邊欄選單。

_layouts/course_layout.html 內容：
### HTML
```
---
layout: page
---
<style>
    .course-container { display: flex; align-items: flex-start; }
    .sidebar { width: 200px; background: #f4f4f4; padding: 15px; border-radius: 8px; position: sticky; top: 10px; height: fit-content; border: 1px solid #ddd; }
    .main-content { flex: 1; padding-left: 30px; }
    .sidebar ul { list-style: none; padding: 0; }
    .sidebar li { margin-bottom: 10px; border-bottom: 1px solid #ccc; }
    .sidebar a { text-decoration: none; color: #007bff; font-weight: bold; }
</style>

<div class="course-container">
    <div class="sidebar">
        {% if page.collection == 'matlab' %}
            <h4>📊 MATLAB 目錄</h4>
            <ul>
                <li><a href="../matlab/ch01">CH01 矩陣運算</a></li>
                <li><a href="../matlab/ch02">CH02 數據繪圖</a></li>
            </ul>
        {% elsif page.collection == 'ai' %}
            <h4>🤖 AI 目錄</h4>
            <ul>
                <li><a href="../ai/ch01">CH01 AI 簡介</a></li>
                <li><a href="../ai/ch02">CH02 神經網路</a></li>
            </ul>
        {% endif %}
    </div>
    <div class="main-content" markdown="1">
        {{ content }}
    </div>
</div>
```
## 第三階段：建立課程內容 (.md 檔) 步驟
請依序建立資料夾與對應的章節檔案。注意：標頭 (Front Matter) 必須設定 layout: course_layout。
1. MATLAB 課程 (建立 _matlab 資料夾)
   - _matlab/ch01.md:
       ```
       ---
       layout: course_layout
       title: "MATLAB CH01"
       ---
       # CH01 矩陣運算
       這是 MATLAB 的第一章。
       ``` 
   - _matlab/ch02.md:
       ```
       ---
       layout: course_layout
       title: "MATLAB CH01"
       ---
       # CH02 數據繪圖
       這是 MATLAB 的第二章。
       ``` 
2. AI 課程 (建立 _ai 資料夾)
   - _ai/ch01.md:
       ```
       ---
       layout: course_layout
       title: "AI CH01"
       ---
       # CH01 AI 簡介
       這是 AI 的第一章。
       ``` 
   - _ai/ch02.md:
       ```
       ---
       layout: course_layout
       title: "AI CH02"
       ---
       # CH02 神經網路
       這是 AI 的第二章。
       ```
## 第四階段：建立 README.md 目錄說明
在根目錄建立或更新 README.md，方便未來管理：
```
# 📚 課程教學網站專案架構

## 📂 目錄結構說明
```text
.
├── _config.yml              # 宣告課程集合 (matlab, ai)
├── index.md                 # 網站總首頁
├── _layouts/
│   └── course_layout.html   # 自動判定側邊欄的 HTML 模板
├── _matlab/                 # MATLAB 講義區
│   ├── ch01.md
│   └── ch02.md
└── _ai/                     # AI 講義區
    ├── ch01.md
    └── ch02.md
```

## 第五階段：建立網頁首頁 (index.md) 建立導向這兩個課程章節的連結
為了讓你的網站擁有一個專業且美觀的門面，我們將在 index.md 使用 「卡片式佈局」。

這樣使用者進入首頁後，可以直觀地選擇進入「MATLAB」或「AI」課程
建立 index.md 內容為以下代碼：
```
---
layout: page
title: 📚 程式課程學習中心
---

# 歡迎來到我的線上講義

這是一個專為 **MATLAB** 與 **AI** 學習者設計的免費資源平台。請點選下方區塊開始學習。

<style>
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
```

