# 使用Gemini建立gitHub步驟
建立新的網站並建立產生步驟，包含matlab、AI兩個課程

Q

1.使用GitHub Pages建立步驟

2.說明必須建立的.md檔步驟

3.建立matlab、AI兩個課程的前兩章內容步驟

4.使用HTML語法 加入matlab、AI兩個課程「浮動側邊欄」步驟

A

針對 GitHub Pages + Jekyll 完整架構的產生手冊。我們將利用「自動化模板」技術，讓 MATLAB 和 AI 課程擁有各自獨立且專業的側邊欄位。
## 第一階段：GitHub Pages 建立步驟
1.建立儲存庫：在 GitHub 建立名為 ytlee.github.io 的 Repository。

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
建立資料夾 _layouts 並在其中建立 course_layout.html。這個檔案會根據你所在的資料夾自動切換側邊欄選單。
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
                <li><a href="../ch01">CH01 矩陣運算</a></li>
                <li><a href="../ch02">CH02 數據繪圖</a></li>
            </ul>
        {% elsif page.collection == 'ai' %}
            <h4>🤖 AI 目錄</h4>
            <ul>
                <li><a href="../ch01">CH01 AI 簡介</a></li>
                <li><a href="../ch02">CH02 神經網路</a></li>
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
