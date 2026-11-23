# Music LLM Wiki — 全球主要音樂流派知識庫

歡迎查閱 **Music LLM Wiki**。本知識庫專為 LLM 檢索增強（RAG）與音樂科普設計，包含標準化的流派屬性定義、風格演變、標誌性樂器、代表音樂家與文化影響。

---

## 知識庫架構規範 (Ontology Schema)

每個音樂流派條目皆遵循以下 LLM 友善結構：
1. **元資料 (Frontmatter)**: ID、名稱、起源年代與發源地、關聯標籤 (LLM Tags)。
2. **核心概述 (Overview)**: 簡練定義與核心哲學。
3. **音樂特徵 (Musical Characteristics)**: 節奏 (Rhythm)、和聲 (Harmony)、常見編制樂器 (Instrumentation)、演唱特質 (Vocals)。
4. **代表性子流派 (Subgenres)**: 演化分支。
5. **標誌性音樂家與代表作 (Key Artists & Masterpieces)**: 必聽曲目與歷史巨擘。
6. **文化與跨界影響 (Cultural Impact)**: 對社會、時尚與現代音樂的影響。
7. **LLM 提示工程與檢索提示 (LLM Prompting & Retrieval Context)**: 用於 AI 角色扮演或音樂推薦的特徵向量提示。

---

## 收錄流派目錄

| 編號 | 流派名稱 (中文 / 英文) | 誕生年代與地區 | 核心音樂特色 | 代表藝術家 | 檔案連結 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **01** | [古典音樂 (Classical Music)](file:///C:/Users/Heng/.gemini/antigravity/scratch/music-llm-wiki/wiki/01_classical.md) | 16-19世紀 / 歐洲 | 嚴謹結構、管弦樂編制、複調與動態張力 | 巴哈、莫札特、貝多芬 | `01_classical.md` |
| **02** | [爵士樂 (Jazz)](file:///C:/Users/Heng/.gemini/antigravity/scratch/music-llm-wiki/wiki/02_jazz.md) | 20世紀初 / 美國紐奧良 | 即興演奏 (Improvisation)、切分節奏、藍調音階 | 路易斯·阿姆斯壯、邁爾士·戴維斯 | `02_jazz.md` |
| **03** | [搖滾樂 (Rock Music)](file:///C:/Users/Heng/.gemini/antigravity/scratch/music-llm-wiki/wiki/03_rock.md) | 1950年代 / 美國與英國 | 電吉他破音、強勁後拍、反叛與自由精神 | 披頭四、齊柏林飛船、皇后合唱團 | `03_rock.md` |
| **04** | [嘻哈音樂 (Hip-Hop)](file:///C:/Users/Heng/.gemini/antigravity/scratch/music-llm-wiki/wiki/04_hiphop.md) | 1970年代 / 美國紐約布朗克斯 | 韻律說唱、取樣 (Sampling)、重低音 808、街頭文化 | 吐派克 (2Pac)、阿姆 (Eminem)、肯德里克·拉馬爾 | `04_hiphop.md` |
| **05** | [電子音樂 (Electronic / EDM)](file:///C:/Users/Heng/.gemini/antigravity/scratch/music-llm-wiki/wiki/05_electronic.md) | 1970-80年代 / 歐美俱樂部文化 | 合成器音色、連續重拍 (4-on-the-floor)、Build-up & Drop | 傻瓜龐克 (Daft Punk)、艾維奇 (Avicii) | `05_electronic.md` |
| **06** | [節奏藍調與靈魂樂 (R&B & Soul)](file:///C:/Users/Heng/.gemini/antigravity/scratch/music-llm-wiki/wiki/06_rnb_soul.md) | 1940-60年代 / 美國非裔社群 | 濃厚情感轉音 (Melisma)、福音和聲、律動感 (Groove) | 雷·查爾斯、艾瑞莎·弗蘭克林、碧昂絲 | `06_rnb_soul.md` |

---

## 關聯知識圖譜 (Relation Graph)

- **古典音樂** $\rightarrow$ 奠定了和聲學、曲式結構，是所有現代西方流行樂的理論底層。
- **藍調 (Blues)** $\rightarrow$ 孕育了 **爵士樂**、**搖滾樂** 與 **節奏藍調 (R&B)**。
- **搖滾樂** 與 **靈魂樂** $\rightarrow$ 碰撞出放克 (Funk)，進一步成為 **嘻哈音樂** 最關鍵的採樣骨架。
- **合成器技術普及** $\rightarrow$ 催生了現代 **電子音樂 (EDM)**，並與嘻哈、當代流行音樂高度融合。
