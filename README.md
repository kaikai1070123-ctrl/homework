## 2. 專案文件導覽 (Project Artifacts)

本專案嚴格遵循領域驅動 RAG 系統開發規範，各項核心交付文件如下：

* **[技術規格說明書 (Specs)](./docs/specs.md)**
    * 定義 Chunking Strategy（語義切分）、性能指標（Latency < 800ms）以及使用 RAGAS 框架的評估機制。
* **[架構決策紀錄 (ADR)](./docs/adr-records.md)**
    * 詳述為何選擇 BGE-M3 作為 Embedding 模型、引入 FlashRank 作為 Reranker 的邏輯，以及選擇 ChromaDB 的背景。
* **[學術論文 RAG 理論白皮書 (Whitepaper)](./docs/whitepaper.md)**
    * 探討資管文獻數位表徵的難點、系統如何透過引用來源對齊抑制「幻覺」問題，以及處理領域專有名詞的創新策略。

## 3. 開發環境與技術棧
* **Embedding:** BGE-M3 (Multi-lingual & Hybrid Search)
* **Vector DB:** ChromaDB
* **Reranker:** FlashRank
* **LLM:** OpenAI GPT-4o
* **Evaluation:** RAGAS Framework

## 4. 授權協議
本專案採用 [MIT License](./LICENSE) 授權。
