# Evaluating the Grammatical Iraab Capabilities of Large Language Models in Arabic

[![IEEE ICMI 2026](https://www.icmiconf.com/assets/img/header.png)]([https://www.icmi.com](https://www.icmiconf.com/index.html))

> **Accepted at:** IEEE 5th International Conference on Computing and Machine Intelligence (ICMI 2026)  
> **Date:** April 08–10, 2026 | King Faisal University, Al-Ahsa, Saudi Arabia (Hybrid)

---

## 📖 Overview

This repository contains the benchmark dataset, evaluation framework, and results for our study on Arabic syntactic *Iraab* (grammatical case marking) analysis using six state-of-the-art large language models (LLMs).

Arabic *Iraab* (الإعراب) refers to the system of grammatical case markings where word endings change to indicate syntactic function within a sentence. It is a morphologically complex task that poses significant challenges even for advanced NLP systems.

We designed **IraabMCQs**, a Multiple-Choice Question (MCQ) framework to systematically evaluate LLM performance across key grammatical dimensions and diverse Arabic text types.

---

## 🧪 Models Evaluated

| Model | Version |
|-------|---------|
| **ChatGPT** | gpt-4o |
| **DeepSeek** | deepseek-chat |
| **Claude** | claude-3-opus-20240229 |
| **Gemini** | gemini-2.0-flash |
| **Grok** | grok-3-latest |
| **Cohere** | command-r |

---

## 📊 Dataset

The benchmark consists of **536 MCQs** derived from **15 manually annotated Arabic sentences** across four text categories:

| Category | Count |
|----------|-------|
| Quranic Verses | 3 |
| Prophetic Hadith | 3 |
| Poetic Lines | 3 |
| General Sentences | 6 |

Each word in every sentence was annotated with three grammatical attributes:

- **`word_type`** — e.g., noun, verb, particle
- **`iraab_case`** — e.g., subject, predicate, object
- **`iraab_sign`** — e.g., nominative (Damma), accusative (Fatha), genitive (Kasra)

Three MCQs with four answer options (A/B/C/D) were generated per word, yielding the full 536-question benchmark. Distractors were drawn from the annotation schema to represent plausible linguistic confusions.

---

## 📁 Repository Structure

```
├── data/
│   ├── sentences/          # 15 annotated Arabic sentences (JSON)
│   ├── mcqs/               # 536 MCQs with answer keys
│   └── annotations/        # Word-level Iraab annotation tables
├── evaluation/
│   ├── eval_framework.py   # Unified Python evaluation script (API-based)
│   └── prompts/            # Prompt templates used per model
├── results/
│   ├── raw/                # JSON files with raw model responses
│   ├── reports/            # Excel summaries by model, question type, sentence type
│   └── figures/            # Accuracy charts (Figures 1–3 from the paper)
├── paper/
│   └── ICMI2026_Iraab_LLM_Evaluation.pdf
└── README.md
```

---

## 📈 Key Results

### Overall Accuracy by Model

| Model | Overall Accuracy |
|-------|-----------------|
| 🥇 **Gemini** | **79.10%** |
| 🥈 **DeepSeek** | **75.75%** |
| 🥉 **GPT** | **73.88%** |
| Claude | 69.59% |
| Grok | 68.84% |
| Cohere | 41.39% |

### Accuracy by Grammatical Aspect

| Model | Word Type | Iraab Case | Iraab Sign |
|-------|-----------|------------|------------|
| GPT | 88.92% | 67.84% | 64.84% |
| DeepSeek | 89.07% | 74.27% | 63.74% |
| Claude | 84.70% | 68.04% | 56.04% |
| Gemini | 85.79% | 70.76% | 80.22% |
| Grok | 87.43% | 63.16% | 55.49% |
| Cohere | 56.28% | 40.35% | 26.92% |

### Key Findings

- **Word type classification** was the strongest area across all models, with DeepSeek (89.07%) and GPT (88.92%) leading.
- **Iraab sign detection** was the most challenging task for all models, particularly for Cohere (26.92%) and Grok (55.49%).
- **Gemini** showed uniquely balanced performance, excelling across both structured classical texts (Quranic, Hadith) and modern prose.
- **Claude** performed best on poetic and Quranic verses relative to its own scores, but lowest on general prose (65.56%).
- **Cohere** showed limited proficiency across all categories, indicating significant challenges in Arabic morphosyntactic processing.


## 📝 Citation

If you use this dataset or evaluation framework in your research, please cite:

```bibtex
@inproceedings{iraabMCQs,
  title     = {Evaluating the Grammatical Iraab Capabilities of Large Language Models in Arabic},
  author    = {AlKhaluqi, Razan and AlGhamdi, Sharefah},
  booktitle = {Proceedings of the IEEE 5th International Conference on Computing and Machine Intelligence (ICMI)},
  year      = {2026},
  address   = {Al-Ahsa, Saudi Arabia},
  publisher = {IEEE}
}
```

---

## 👩‍💻 Authors
- **Razan AlKhaluqi** — Department of Information Technology, King Saud University, Riyadh, Saudi Arabia  
  📧 443204373@student.ksu.edu.sa

- **Sharefah AlGhamdi** — Department of Information Technology, King Saud University, Riyadh, Saudi Arabia  
  📧 sharefah@ksu.edu.sa



