# NLP-SQL-Translator

## 📌 Overview
This project fine-tunes a quantized **Llama2-GPTQ 7B** model using **QLoRA** to generate SQL grounded in the correct schema context. The system shows major improvements over the baseline across ROUGE metrics and reliably handles complex SQL operations including joins, aggregations, grouping, and filtering.

---

## ✨ Key Features
- ⚡ Efficient QLoRA fine-tuning on 4-bit Llama2-GPTQ  
- 🧠 Schema-aware SQL generation using CREATE TABLE context  
- 🔧 Structured instruction prompts for improved accuracy  
- 🛠 Advanced preprocessing and noise reduction  
- 📊 Strong ROUGE performance gains  
- 🔗 Supports JOINs, GROUP BY, HAVING, ORDER BY, and multi-table reasoning  

---

## 📂 Dataset
- Source: **b-mc2/sql-create-context** (Hugging Face)  
- Includes natural language questions, reference SQL queries, and schema definitions  
- Grounded prompts reduce hallucinations of column/table names  
- Reformatted into structured instruction templates for consistency  

---

## 🧱 Model Architecture
- **Base model:** Llama2-GPTQ (4-bit quantized)  
- **Fine-tuning technique:** QLoRA  
  - Rank: 8  
  - LoRA dropout: 0.05  
  - Applied to key attention modules  
- **Tokenization:** Query + schema jointly encoded  
- **Environment:** Python, Hugging Face Transformers, A100 GPU  

---

## ⚙️ Training Configuration
Batch size: 16
Gradient accumulation: 4
Learning rate: 2e-4
Warmup steps: 2
Precision: fp16
Evaluation: per epoch
Checkpointing: per epoch

---

## 📈 Results

### ROUGE Improvements
- 🔹 **ROUGE-1 F1:** 0.37 → **0.79**  
- 🔹 **ROUGE-2 F1:** 0.17 → **0.59**  
- 🔹 **ROUGE-L F1:** 0.36 → **0.77**  

### Model Capabilities
- Generates schema-accurate SQL  
- Handles complex joins and aggregations  
- Reduces hallucinated column/table names  
- Strong structural alignment with SQL references  

---
