# Agent Guide & Project Specification: Music LLM Wiki & Presentation System

這份文件是本專案的最高規範與指南。無論是人類開發者或是協作的 AI Agent，在維護、擴充功能、新增音樂流派或編寫條目時，都必須嚴格遵循本文件的定義與原則。

---

## 1. 專案目的 (Project Purpose)

- **核心定位**：專門為大型語言模型（LLM）檢索增強（RAG）、提示工程（Prompt Engineering）與音樂科普教學設計的結構化音樂知識庫與互動簡報系統。
- **核心目標**：
  1. **本體論結構化管理**：依據流派歷史、樂理特徵、器樂編制、大師名盤與文化脈絡，提供標準化且可機器解析的六維知識條目。
  2. **輕量極速與零外部依賴**：知識庫基於純 Markdown 與 JSON 雙軌維護；互動簡報基於純原生 HTML5/CSS3/Vanilla JS，無後端或重型框架負擔。
  3. **自動化發布與純淨網址**：託管於 GitHub Pages 根目錄，存取完全無額外子路徑（`https://411335070.github.io/music-llm-wiki/`）。
  4. **原生 Web Audio 即時音效**：內建基於瀏覽器震盪器（Oscillator）之演算法合成音效，免下載額外 MP3 檔案即可試聽各流派代表和弦與律動。
  5. **LLM 與 RAG 友善**：每篇條目皆具備 YAML Frontmatter、語意標籤與專屬「LLM 提示詞錨點 (Retrieval Anchor)」，支援多跳圖譜推理與智能體角色扮演。

---

## 2. 系統運作方式 (Operational Workflow)

- **基礎架構**：採用純前端靜態架構，由雙核心模組構成：
  - **Wiki 模組**：Markdown 檔案叢集 + `music_genres_data.json` 結構化資料集。
  - **Presentation 模組**：單頁式毛玻璃（Glassmorphism）動態光影簡報。
- **工作流程**：
  1. **本地編輯 (Local Authoring)**：在本地使用 Markdown 編輯器撰寫各流派 Wiki 條目。
  2. **本地預覽 (Local Preview)**：直接雙擊 `index.html` 即可以瀏覽器離線預覽全螢幕簡報與合成音效。
  3. **自動化部署 (CI/CD)**：
     - 開發者將變更推播至 GitHub 的 `main` 分支。
     - GitHub Pages 服務自動檢測根目錄 `index.html` 並在 1~2 分鐘內完成全域 CDN 派送。
  4. **RAG 向量檢索與 AI 應用 (LLM Integration)**：
     - 知識庫可直接切片（Chunking）匯入向量資料庫（Chroma/Pinecone）。
     - 透過 Frontmatter 中的元資料（BPM、和聲、樂器）實現精確的元數據過濾（Metadata Filtering）與跨流派演化圖譜推理。

---

## 3. 檔案架構與命名規範 (File Structure & Naming Conventions)

### 3.1 目錄結構總覽

```text
music-llm-wiki/
├── index.html                   # 根目錄首頁簡報 (直接存取無路徑：https://411335070.github.io/music-llm-wiki/)
├── presentation/
│   └── index.html               # 簡報備用路徑 (相容既有連結)
├── wiki/
│   ├── index.md                 # Wiki 總目錄、本體論規範與演化圖譜
│   ├── 01_classical.md          # 01 古典音樂 (Classical Music)
│   ├── 02_jazz.md               # 02 爵士樂 (Jazz)
│   ├── 03_rock.md               # 03 搖滾樂 (Rock Music)
│   ├── 04_hiphop.md             # 04 嘻哈音樂 (Hip-Hop)
│   ├── 05_electronic.md         # 05 電子音樂 (Electronic / EDM)
│   ├── 06_rnb_soul.md           # 06 節奏藍調與靈魂樂 (R&B & Soul)
│   └── music_genres_data.json   # 結構化 JSON 資料庫 (供向量檢索與前端呼叫)
├── agent.md                    # 本規範文件
├── .gitignore                  # Git 忽略檔案設定
└── README.md                   # 專案首頁說明與線上入口
```

### 3.2 命名規則

1. **條目檔案名稱**：一律放置於 `wiki/` 目錄，命名格式為 `兩位序號_流派英文代碼.md`（例如：`01_classical.md`、`07_heavy_metal.md`、`08_reggae.md`）。
2. **結構化資料庫**：統一名稱為 `wiki/music_genres_data.json`，所有新增的流派必須同步追加至此 JSON 陣列。
3. **圖片檔案名稱**（若有擴充）：放置於 `wiki/images/` 目錄中，命名格式為 `kebab-case.png`。

### 3.3 Frontmatter 規範

每篇流派條目頂部**必須**包含標準 YAML Frontmatter，以便 AI 檢索與程式提取：

```yaml
---
id: genre_classical
name_zh: 古典音樂
name_en: Classical Music
origin_era: 16世紀末 - 19世紀初 (涵蓋巴洛克、古典主義與浪漫主義)
origin_region: 歐洲 (以德奧、義大利、法國為核心)
bpm_range: 40 - 180 (多變動態 Tempo Rubato)
tags: [管弦樂, 和聲學, 交響樂, 奏鳴曲, 複調音樂, 大師經典]
---
```

---

## 4. 媒體、音訊與超連結規範 (Media, Audio & Links Guide)

### 4.1 視覺與介面風格
- 全站採用深色沉浸式夜間主題（Dark Mode）與毛玻璃效果（Glassmorphism，`backdrop-filter: blur(20px)`）。
- 每個流派需分配一個主題代表色與漸層背景（例如古典紫 `#8b5cf6`、爵士金 `#f59e0b`、搖滾紅 `#ef4444`、嘻哈綠 `#10b981`、電音青 `#06b6d4`、靈魂粉 `#ec4899`），切換投影片時背景環境光暈將平滑過渡。

### 4.2 Web Audio 合成音訊規範
- **零外部依賴原則**：不得連結外部 MP3/WAV 檔案（避免 404 或版權封鎖），一律使用瀏覽器原生 `AudioContext` 震盪器演算法合成。
- **音色模擬定義**：
  - 古典：三角波（Triangle Wave）大三和弦琶音。
  - 爵士：正弦波（Sine Wave）大七度／小九度和弦。
  - 搖滾：鋸齒波（Sawtooth Wave）失真破音（Distortion Power Chord）。
  - 嘻哈：808 次低音滑音（Pitch Drop）+ 快速 Hi-hat 連擊。
  - 電子：四拍正拍重擊（Four-on-the-Floor）+ 向上升調琶音。
  - 靈魂：溫暖正弦電鋼琴（Rhodes）九和弦進行。

### 4.3 網址與超連結加入方式
1. **GitHub Pages 根網址存取**：`https://411335070.github.io/music-llm-wiki/`。
2. **GitHub 原始碼檔案連結**：`https://github.com/411335070/music-llm-wiki/tree/main/wiki`。
3. **條目內部相互引用**：使用相對路徑，如 `[前往爵士樂條目](./02_jazz.md)`。

---

## 5. 新增與操作流程指南 (How-To Guide)

### 5.1 方式一：新增全新音樂流派條目（例如新增「重金屬」或「雷鬼」）
1. 在 `wiki/` 目錄下建立新檔案，例如 `wiki/07_heavy_metal.md`。
2. 按照統一範式填入六大結構區塊：
   - 1. 核心概述 (Overview)
   - 2. 音樂特徵 (Musical Characteristics：節奏、和聲、編制、唱腔)
   - 3. 代表性歷史分期與子流派 (Subgenres)
   - 4. 標誌性音樂家與代表作 (Key Artists & Masterpieces)
   - 5. 文化與跨界影響 (Cultural Impact)
   - 6. LLM 提示詞參照 (LLM Retrieval Anchor)
3. 同步在 `wiki/index.md` 的目錄表格與關聯圖譜中加入該流派。

### 5.2 方式二：同步更新結構化資料庫與簡報矩陣
1. 打開 `wiki/music_genres_data.json`，將新流派的 ID、名稱、時代、BPM、樂器與特徵追加至陣列。
2. 打開 `index.html`（與 `presentation/index.html`）：
   - 在幻燈片容器中加入對應的 `<section class="slide" data-genre="...">` 投影片。
   - 在比對矩陣表格中追加一行。
   - 在封面頁加入快速跳轉膠囊標籤。
   - 在 `playGenreVibe()` 函式中加入該風格專屬的合成音頻演算法。

### 5.3 方式三：線上直接編輯既有條目（免本機環境）
1. 前往 GitHub 倉庫：`https://github.com/411335070/music-llm-wiki/tree/main/wiki`。
2. 點擊欲修改的條目（如 `03_rock.md`），點選右上角鉛筆圖示進行編輯。
3. 編輯完成後，在下方填寫 Commit 說明並點擊 **「Commit changes」**。
4. GitHub Pages 將在 1~2 分鐘內自動重新構建上線。

### 5.4 方式四：線上直接上傳條目檔案（拖曳上傳）
1. 前往 GitHub 倉庫的 `wiki/` 目錄。
2. 點選右上角的 **「Add file」 $\rightarrow$ 「Upload files」**。
3. 將寫好的 `.md` 檔案拖曳至上傳區塊。
4. 點擊 **「Commit changes」** 完成上傳。

### 5.5 方式五：本地端維護與推送
在專案目錄下執行標準 Git 操作：
```bash
git add .
git commit -m "feat: add heavy metal genre entry and update slides"
git push origin main
```

---

## 6. GitHub 建立與部署指南 (GitHub Setup & Deployment)

### 6.1 GitHub 儲存庫初始化指令
```bash
cd C:\Users\Heng\.gemini\antigravity\scratch\music-llm-wiki
git init
git add .
git commit -m "feat: initial commit for Music LLM Wiki and interactive presentation"
git branch -M main
git remote add origin https://github.com/411335070/music-llm-wiki.git
git push -u origin main
```

### 6.2 GitHub Pages 根網址設定（關鍵步驟）
1. 進入 GitHub 儲存庫頁面，點選 **Settings** $\rightarrow$ **Pages**。
2. 在 **Build and deployment** $\rightarrow$ **Branch** 選擇 `main`，目錄選擇 `/ (root)`。
3. 點擊 **Save**。
4. 部署完成後，存取網址即為乾淨的根網址：`https://411335070.github.io/music-llm-wiki/`。

### 6.3 專案路徑配置注意事項（Base URL）
- 本專案採用根目錄 `index.html` 部署，靜態資源一律使用**相對路徑**（如 `./wiki/...`），嚴禁硬編碼本地端絕對路徑（如 `C:/Users/...`），確保在任何線上域名或自訂網域下均能無縫載入。

---

## 7. AI Agent 行為準則 (Rules for AI Agents)

1. **六維本體論結構維持**：新增或修改條目時，嚴格保留 YAML Frontmatter 與 6 大章節結構，不可隨意省略 BPM 範圍或 LLM 提示詞錨點。
2. **機器可讀性與 JSON 同步**：修改 Markdown 條目時，必須主動同步更新 `wiki/music_genres_data.json`，確保 RAG 向量切片與前端呼叫資料的一致性。
3. **音效純前端零依賴原則**：擴充簡報功能時，一律遵循 HTML5 Web Audio API 演算法合成規則，不得擅自引入需要網路連線的外部巨大音訊資源。
4. **樂理與歷史脈絡準確性**：嚴禁時代錯置（如將 808 次低音歸因於 1950 年代，或混淆大小調功能和聲與模態爵士的和弦體系）。
5. **Prompt 錨點標準化**：每篇條目的 LLM 提示詞必須具備 `Role/Context`、`Key Attributes` 與 `Recommended Prompting` 三元素，以便下遊 AI 智能體直接掛載為 System Prompt。
