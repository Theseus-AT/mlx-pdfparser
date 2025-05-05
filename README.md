# 🔗 Theseus MLX RAG Ecosystem

**Datenschutzfreundliches RAG-System für Apple Silicon und MLX-kompatible Umgebungen.**
Dieses Projekt vereint lokal laufende Vektordatenbanken, ein leichtgewichtiges RAG-Framework und eine vollständige PDF-Verarbeitung – ohne Abhängigkeit von LangChain oder Cloud-Diensten.

---

## 🧩 Komponentenübersicht

| Modul                      | Beschreibung |
|---------------------------|--------------|
| [`mlx-rag-advanced`](https://github.com/Theseus-AT/mlx-rag-advanced) | Zentrale RAG-Logik (PDF, Embeddings, Retrieval, LLM) |
| [`mlx-vector-db`](https://github.com/Theseus-AT/mlx-vector-db.git) | Eigene Vektordatenbank für lokale Similarity-Suche |
| [`mlx-langchain-lite`](https://github.com/Theseus-AT/mlx-langchain-lite) | Mini-Framework zur Modell-, Prompt- und Retrieval-Verknüpfung (ohne LangChain) |

---

## 🚫 Warum **nicht LangChain**?

> Wir setzen bewusst auf ein **leichtgewichtiges, lokales Framework**, das:
>
> - keine Telemetrie oder Cloud-Verbindungen aufbaut
> - keine tief verschachtelten Abstraktionen verwendet
> - auf MLX (Apple Silicon), NumPy und PyTorch reduziert bleibt
> - schneller und transparenter erweiterbar ist

Unsere `mlx-langchain-lite`-Komponente nutzt nur die Konzepte von LangChain (Tools, Chains, Retriever), aber nicht dessen Codebasis oder Architektur.

---

## ⚙️ Systemübersicht

```text
[PDF] → [Chunker] → [Embeddings (MLX)] → [mlx-vector-db]
                                          ↓
                                      [Retriever]
                                          ↓
                          [PromptBuilder (mlx-langchain-lite)]
                                          ↓
                            [LLM (Gemma, Mistral, etc.)]
