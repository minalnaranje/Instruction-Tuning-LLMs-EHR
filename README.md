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

git clone https://github.com/minalnaranje/Instruction-Tuning-LLMs-EHR.git
cd Instruction-Tuning-LLMs-EHR

 ### 2. Install Dependencies
pip install -r requirements.txt
Alternatively, install individually:

pip install transformers torch accelerate

### 3. Prepare Sample Data
Ensure qa_event_subset.jsonl is located inside the sample_data/ directory or the root project folder.

--

## 🧪 Run the Application

Start the Assistant:
python ehr_assistant.py
Interactive CLI:
Type a patient ID (e.g., 110964)
Enter a natural language question like:
"What was the lab value at the 12-hour mark?"
"Was insulin prescribed during the stay?"
Or type list to see all known Q&A for the patient.

--

## 🧩 Improvements Over Original LLEMR

Component	Original LLEMR	Our Implementation
Base Model	Vicuna-7B (Med-tuned)	TinyLlama-1.1B (General-purpose)
Prompting Style	Basic instruction tuning	Context-aware, event-type-structured prompts
Matching Logic	Direct Q→A lookups	Semantic matching using key-term overlap
Time-sensitive Queries	Not handled	Supports filtering by timestamp within prompts
Deployment	Heavy compute required	Lightweight, laptop-compatible

--

## 📂 File Structure

├── Instruction_tuning_LLMs.py            # Main assistant script
├── sample_data/
│   └── qa_event_subset.jsonl   # EHR-based Q&A data
├── README.md                   # Project documentation
├── requirements.txt            # Python dependencies

--

## 📈 Results

TinyLlama successfully handled 80–90% of test queries with acceptable accuracy
Time-based and keyword-matched context improved relevance significantly
Clearly indicated when data was insufficient — aligned with human reasoning

--

## 🙏 Acknowledgements

The authors of the original LLEMR paper and MIMIC-IV dataset.
Hugging Face for TinyLlama and Transformers library.
MIT for maintaining the open-source MIMIC EHR datasets.

