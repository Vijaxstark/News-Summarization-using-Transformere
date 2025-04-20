# 📰 News Summarization using Transformers

This project fine-tunes a pre-trained transformer model (BART) for summarizing English-language news articles from the ILSUM dataset.

## 📌 Objective

- Explore transformer-based models for text summarization.
- Fine-tune a suitable BART variant (`facebook/bart-base`) on a filtered English subset of the ILSUM-1.0 dataset.
- Evaluate using standard summarization metrics like ROUGE.

## 📚 Dataset

**Indian Language Summarization Dataset (ILSUM-1.0)**  
- Subset: English  
- Source: https://huggingface.co/datasets/ILSUM/ILSUM-1.0  
- Filtering:
  - Input tokens limited to 512
  - Target summary tokens limited to 128
  - Kept samples with sufficient length and quality
  - Training samples > 1000

## 🔧 Model Details

| Model Variant         | Max Input Tokens | Parameters |
|-----------------------|------------------|------------|
| facebook/bart-base    | 1024             | 139M       |
| facebook/bart-large   | 1024             | 406M       |
| t5-small              | 512              | 60M        |
| t5-base               | 512              | 220M       |

Chosen model: ✅ `facebook/bart-base` — well-balanced for fine-tuning on Colab/Kaggle.

## 🏗️ Preprocessing & Fine-tuning

- Tokenization using HuggingFace's `AutoTokenizer`
- Truncation and padding to fixed length
- Dataset split into training, validation, and test sets
- Model fine-tuned using `Seq2SeqTrainer`

## 📈 Evaluation Metrics

Used **ROUGE** metrics via the `evaluate` library:
- ROUGE-1
- ROUGE-2
- ROUGE-L

These metrics compare overlap between predicted summaries and reference texts.

## 🚀 How to Run

```bash
pip install -r requirements.txt
# Then run the notebook: ME21B1039_Assignment_10.ipynb
```

## 🧠 Tools & Libraries

- Transformers (`facebook/bart-base`)
- HuggingFace Datasets
- Evaluate (ROUGE)
- Accelerate, PEFT
- PyTorch

---

**Author**: Vijay Krishna RV  
**ID**: ME21B1039  
**Date**: 07-04-2025
