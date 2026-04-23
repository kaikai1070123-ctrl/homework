# IM-Scholar: 資管學術論文 RAG 系統專案

這是一個針對資管領域學術論文設計的檢索增強生成 (RAG) 系統，旨在提升專業知識檢索的可解釋性與準確度。

## 1. 架構圖解 (Architecture)

```mermaid
graph LR
    subgraph "數據處理 (ETL)"
        PDF[學術論文 PDF] -->|PyMuPDF| MD[Markdown]
        MD -->|Semantic Chunking| CH[Chunks]
    end

    subgraph "檢索層 (Retrieval)"
        CH -->|BGE-M3 Embedding| VDB[(Vector DB: ChromaDB)]
        Query[使用者提問] -->|Hybrid Search| VDB
        VDB -->|Top-10| RR[Reranker: FlashRank]
    end

    subgraph "生成層 (Generation)"
        RR -->|Top-3 Context| LLM[GPT-4o]
        LLM --> Output[可解釋性回答]
    end
