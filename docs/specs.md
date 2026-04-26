# IM-Scholar 系統規格說明書 (Specs)

### 1. 資料切分策略 (Chunking Strategy)
* **策略類型：** 語義切分 (Semantic Chunking) 輔以 Markdown 標記切分。
* **具體作法：** 考量學術論文具有嚴謹的章節（如 Abstract, Methodology, Conclusion），系統優先感應 Markdown 標題進行物理切分，再針對過長段落進行語義相似度滑動視窗處理，確保 context 不跨越主題。

### 2. 性能指標 (Performance Metrics)
* **檢索延遲 (Latency)：** Top-10 檢索與 Reranking 總耗時須低於 800ms。
* **Top-K 準確度：** 檢索前 5 名中必須包含能回答問題的關鍵段落 (Hit Rate > 85%)。

### 3. 評估機制 (Evaluation Framework)
本系統導入 **RAGAS** 評估框架，針對以下維度進行量化：
* **Faithfulness (忠實度)：** 確保答案完全源於檢索到的文獻，杜絕 AI 自行發揮。
* **Answer Relevance (答案相關性)：** 評估回答是否精確命中資管專業術語。
* **Context Precision (檢索精確度)：** 評估檢索出的論文片段是否真的具備參考價值。
