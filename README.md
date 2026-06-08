# dogri-english-lora-translation
# OVERVIEW

**This project explores low-resource machine translation for Dogri → English using LoRA (Low-Rank Adaptation) fine-tuning on the NLLB-200 Distilled 600M model.**
The objective was to investigate whether a pre-trained multilingual translation model can improve translation quality when fine-tuned on a small custom Dogri-English dataset.

# DATASET

477 Dogri-English sentence pairs
Dogri written in Devanagari script
Custom curated and cleaned dataset
Train-Test Split: 80:20 (seed=42)

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
| NLLB-200 + LoRA |	0.59 |

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
│   ├── baseline_scores.json
│   ├── lora_scores.json
│   └── predictions.csv
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
