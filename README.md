# dogri-english-lora-translation
# OVERVIEW

**This project explores low-resource machine translation for Dogri → English using LoRA (Low-Rank Adaptation) fine-tuning on the NLLB-200 Distilled 600M model.**
The objective was to examine whether a pre-trained multilingual translation model can improve translation quality when fine-tuned on a small custom Dogri-English dataset.

# DATASET

1) 477 Dogri-English sentence pairs, and from this two smaller subsets were created for incremental evaluation: Dataset 1 (v1) contains 51 pairs, Dataset 2 (v2) contains 151 pairs, and the final dataset with all 477 pairs
2) Dogri written in Devanagari script
3) Custom curated and cleaned dataset
4) Train-Test Split: 80:20 (seed=42)

### ADDITIONAL EVALUATION SET

67 Dogri idioms

# MODEL

Base Model- NLLB-200 Distilled 600M
Fine-Tuning Method- LoRA (Low-Rank Adaptation)

# EVALUATION METRICS

The model was evaluated using: METEOR

# RESULTS

| Model	| METEOR Score |
|:--- | :---: |
| Baseline NLLB-200 |	0.32 |
| NLLB-200 + LoRA (with 477 sentence pairs) |	0.59 |
| NLLB-200 + LoRA (with 151 sentence pairs) | 0.46 |
| NLLB-200 + LoRA (with 51 sentence pairs) | 0.22 |
| Idiom METEOR | 0.0052 |
| Normal METEOR | 0.019 |

# KEY OBSERVATIONS
1) Fine-tuning significantly improved translation quality.
2) The model learned common sentence patterns from a relatively small dataset.
3) Translation quality improved as dataset size increased.
4) The model struggled with idiomatic expressions.
5) Most Dogri idioms were translated literally rather than semantically because of low idiom dataset.

# PROJECT STRUCTURE
```
├── data/
│   ├── train.csv
│   └── idioms.csv
│
├── notebooks/
│   ├── lora_training.ipynb
│   └── baseline_evaluation.ipynb
│
├── results/
│   ├── baseline results.json
│   ├── final-dataset results.json
|   ├── v1 results.json
│   └── v2 results.json
│
└── README.md
```
# TECHNOLOGIES USED

Python
Hugging Face Transformers
PEFT (LoRA)
PyTorch
Datasets
Evaluate
Google Colab

# FUTURE WORK
1) Increase training data size
2) Include more idiomatic expressions
3) Experiment with larger multilingual models
4) Improve semantic understanding for low-resource languages
