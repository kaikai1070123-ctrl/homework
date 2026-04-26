# 架構決策紀錄 (ADR)

### [ADR-001] 選擇 BGE-M3 作為 Embedding Model
* **Context:** 資管學術論文包含大量中英文術語對照。
* **Decision:** 捨棄純英文模型，選擇 BGE-M3。
* **Status:** Accepted.
* **Consequences:** 支援多語言且具備 Hybrid Search 能力，能同時處理關鍵字匹配與語義理解。

### [ADR-002] 引入 FlashRank 作為 Reranker
* **Context:** 向量資料庫檢索出的 Top-K 內容有時雜訊過多。
* **Decision:** 在檢索層與生成層之間加入 FlashRank 階段。
* **Status:** Accepted.
* **Consequences:** 雖然增加了約 200ms 延遲，但顯著提升了 LLM 輸入端的資訊純度，降低了生成錯誤率。

### [ADR-003] 使用 ChromaDB 作為 Vector Database
* **Context:** 需要支援本地化部署與快速原型的開發環境。
* **Decision:** 選擇開源的 ChromaDB。
* **Status:** Accepted.
* **Consequences:** 易於整合進 Python ETL 流水線，且足以支撐當前論文庫的檢索規模。
