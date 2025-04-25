# 🩺 Instruction-Tuning LLMs for EHR Understanding

Implementation and enhancement of the Llemr framework for instruction-tuning large language models on Electronic Health Records (EHR) using the MIMIC-Instr dataset. Includes custom context-aware matching, semantic retrieval, and key term extraction for clinical query understanding.


This project is a replication and enhancement of the NeurIPS 2024 paper:

**Title**: *Instruction Tuning Large Language Models to Understand Electronic Health Records*  
**Authors**: Zhenbang Wu, Anant Dadu, Michael Nalls, Faraz Faghri, Jimeng Sun  
📄 [NeurIPS 2024 Paper](https://neurips.cc/virtual/2024/poster/97801)  
📚 Original Repository: [LLEMR GitHub](https://github.com/zzachw/llemr)

---

## 🧠 Project Summary

This repository presents a lightweight yet effective implementation of the **LLEMR framework** using the **TinyLlama-1.1B-Chat-v1.0** model.

### 🔍 Objective

To build a conversational AI assistant that:
- Interprets Electronic Health Records (EHRs)
- Responds to natural language clinical questions
- Understands context, timing, and medical semantics

We enhanced the original LLEMR architecture by introducing **context-aware semantic matching** to make a smaller LLM perform comparably to larger models.

---

## 🚀 Key Features

✅ Uses a **lightweight LLM** (TinyLlama)  
✅ Context-aware **prompt engineering**  
✅ Realistic **EHR query simulation**  
✅ **Time-based filtering** for lab/procedure events  
✅ **Semantic matching** for relevant historical Q&A  
✅ Clearly shows when the model has **insufficient information**

---

## 🗃️ Dataset

- Source: Simulated from the **MIMIC-IV** instruction dataset
- Format: JSONL (`qa_event_subset.jsonl`)
- Fields:
  - `hadm_id`: Hospital admission ID
  - `event_type`: Category of clinical event (e.g., `labevents`, `prescriptions`)
  - `q`: Medical question
  - `a`: Corresponding answer

---

## 🛠️ Setup & Installation

### 1. Clone the Repository

```bash
git clone https://github.com/minalnaranje/Instruction-Tuning-LLMs-EHR.git
cd Instruction-Tuning-LLMs-EHR

