# 📘 Emittr NLP Pipeline – Setup

This repository contains the setup and training pipeline for the Emittr NLP system, handling tasks such as Named Entity Recognition (NER), Summarization, Question Answering (QA), Sentiment Analysis, Intent Classification, and SOAP Note Generation.

---

## 🔧 Environment Requirements

- **Python**: 3.8+
- **Hardware**: Google Colab or a GPU-enabled machine is highly recommended for training efficiency.

---

## 📦 Installation

Install the required Python dependencies and spaCy language models:

```bash
pip install transformers torch datasets accelerate spacy scispacy keybert scikit-learn pandas
python -m spacy download en_core_web_sm
```

---

## 📂 Required Files

Ensure the following datasets are uploaded to your root directory before running the training cells:

| File Name | Usage |
|-----------|-------|
| `Combined_Data_with_Intents_5k.csv` | Required for training Sentiment Analysis and Intent Classification models |
| `soap_final_filled_roberta.json` | Required for training the SOAP note generation model |

---

## 🚀 How to Run

Execute the cells in the provided notebook from top to bottom. The recommended workflow is:

1. **Inference Pipeline**: Start with the NER, Summarization, and QA pipeline (Sections 1 & 2)
2. **Classification Training**: Train the combined Sentiment + Intent model (Section 3)
3. **Generation Training**: Train the SOAP note generation model (Section 4)

---

## 💾 Model Outputs

After training is complete, the fine-tuned models will be saved and zipped automatically. The downloadable artifacts include:

- **Model Weights**: The fine-tuned state dictionaries
- **Tokenizer**: The associated tokenizer files for the models
- **label_map.json**: Critical mapping file required for inference
