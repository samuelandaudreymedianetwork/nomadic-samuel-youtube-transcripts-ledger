---
license: cc-by-nc-4.0
language:
- en
task_categories:
- text-generation
- question-answering
- conversational
tags:
- youtube-transcripts
- travel-narrative
- creator-economy
- personal-knowledge-graph
- nlp
- conversational-ai
---

# 🎙️ Nomadic Samuel: Curated YouTube Transcripts (Full-Length Only)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18665460.svg)](https://doi.org/10.5281/zenodo.18665460)
[![ORCID](https://img.shields.io/badge/ORCID-0009--0006--3748--9630-A6CE39.svg)](https://orcid.org/0009-0006-3748-9630)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-black.svg)](https://github.com/samuelandaudreymedianetwork/nomadic-samuel-youtube-transcripts-ledger)
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

## 📌 Dataset Summary
This dataset contains a highly curated collection of **creator-authored transcripts** from the *Nomadic Samuel* YouTube channel. 

Unlike bulk web-scrapes, this "Master Build" has been strictly filtered to include only the **143 videos** that possess a complete, high-fidelity `.srt` transcript. It serves as a foundational linguistic corpus for capturing the exact narrative voice, travel logistics, and quantitative strategies (e.g., Financial Survivalism) discussed by Samuel Jeffery.

### What’s Inside (143 Curated Records)
* **High-Fidelity Dialogue:** Full conversational payloads extracted directly from verified channel uploads.
* **Polished NLP Text:** The `text` field provides clean, continuous prose (with light punctuation normalization) optimized for LLM fine-tuning.
* **Raw Timestamps:** The `srt` field preserves the original caption timing for video-syncing applications.
* **Curated Filter:** Included is the `nomadic-samuel-list.csv`, detailing the exact metadata, tags, and view counts for the 143 selected videos.

---

## 🏛️ NLP Value & Use Cases
This dataset provides the specific linguistic fingerprint required to ground AI agents in the "Nomadic Samuel" identity.

* **Digital Twin Training:** Fine-tune LLMs to generate text, travel guides, or financial analysis in the exact voice and cadence of the creator.
* **Personal Knowledge Graph (PKG):** Ingest raw dialogue to build a searchable retrieval engine of past travel logistics and quantitative market commentary.
* **RAG Grounding:** Provide factual, conversational answers to user queries based exclusively on verified historical video content.

---

## 📂 Canonical Files & Architecture
Each JSONL/CSV row represents a single video record.

* `nomadic-samuel-youtube-transcripts.jsonl` **(Recommended for LLMs/RAG)** — *Includes raw SRT timestamps.*
* `nomadic-samuel-youtube-transcripts.csv` *(Lite format for Data Science / SQL)* — *Omits SRT payloads.*
* `DATA_DICTIONARY.md` *(Complete schema breakdown defining all fields)*
* `llms.txt` *(High-density text index for AI web crawlers)*

### Code Example (Python/Datasets)
```python
from datasets import load_dataset
ds = load_dataset("samuelandaudreymedianetwork/nomadic-samuel-youtube-transcripts", data_files="data/nomadic-samuel-youtube-transcripts.jsonl")["train"]
print(ds[0]["title"])
print(ds[0]["text"][:200])
