# 🎵 Music LLM Wiki 專案說明文件

本專案是一個專門為 **LLM 檢索增強（RAG）**、**提示工程（Prompt Engineering）** 與 **音樂科普教學** 設計的結構化音樂知識庫，並附帶一個現代化、互動式的 **HTML 簡報 (Slide Deck)**。

---

## 📁 專案目錄結構

```text
music-llm-wiki/
├── presentation/
│   └── index.html               # 現代化互動簡報 (支援鍵盤導航、全螢幕、Web Audio 試聽)
├── wiki/
│   ├── index.md                 # Wiki 總目錄、本體論規範與演化圖譜
│   ├── 01_classical.md          # 01 古典音樂 (Classical Music)
│   ├── 02_jazz.md               # 02 爵士樂 (Jazz)
│   ├── 03_rock.md               # 03 搖滾樂 (Rock Music)
│   ├── 04_hiphop.md             # 04 嘻哈音樂 (Hip-Hop)
│   ├── 05_electronic.md         # 05 電子音樂 (Electronic / EDM)
│   ├── 06_rnb_soul.md           # 06 節奏藍調與靈魂樂 (R&B & Soul)
│   └── music_genres_data.json   # 結構化 JSON 資料庫 (供向量檢索與前端呼叫)
└── README.md                    # 本專案說明
```

---

## 🌟 亮點特色

1. **結構化資料標準 (LLM-Ready Ontology)**：
   - 每個 Markdown 條目均具備統一的 YAML Frontmatter（包含 ID、中英文名稱、時期、地區、BPM 區間、檢索標籤）。
   - 包含「LLM 提示詞錨點 (LLM Retrieval Anchor)」，可直接作為 AI 角色扮演或推薦引擎的 System Prompt。
2. **超越要求的完整內容 (共 6 大核心流派)**：
   - 古典、爵士、搖滾、嘻哈、電子、節奏藍調與靈魂樂。
   - 涵蓋樂理特徵、和聲、樂器編制、歷史分支、代表音樂家與經典名盤、文化衝擊。
3. **無外部依賴的互動式 HTML 簡報**：
   - **鍵盤控制**：使用鍵盤 `←` / `→`、`Space`、`Home`、`End` 快速翻頁。
   - **Web Audio API 即時合成音效**：無需額外下載音檔，點擊「試聽風格音色」即可透過瀏覽器震盪器即時合成該風格的特色和弦或節奏（如古典弦樂和弦、爵士七和弦、搖滾破音、嘻哈 808 重低音、EDM 4拍重擊、R&B Rhodes 電鋼琴）。
   - **流派比對矩陣與 AI 架構展示**：包含完整的綜合對比表格與 RAG 落地說明。

---

## 🚀 如何開啟與使用

### 1. 開啟 HTML 簡報
在檔案總管中雙擊直接用 Chrome / Edge 等瀏覽器開啟：
👉 **檔案路徑**：`C:\Users\Heng\.gemini\antigravity\scratch\music-llm-wiki\presentation\index.html`

### 2. 查閱 Wiki 知識庫
所有條目皆為標準 Markdown 格式，可直接使用 VS Code、Obsidian 或任何文字編輯器瀏覽：
👉 **知識庫路徑**：`C:\Users\Heng\.gemini\antigravity\scratch\music-llm-wiki\wiki\`
