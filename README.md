# roberta-spam-classifer
roBERTa based model for spam classification for [this](https://www.kaggle.com/datasets/mariumfaheem666/spam-sms-classification-using-nlp) kaggle challenge.

The `main.ipynb` is where everything is housed. I used the following models:
- KNN
- Multinominal Naive Bayes
- XGBoost
- LightGBM
- A fine-tuned a roBERTa model (found in the other ipynb, run through google collab).

The huggingFace for it is here: [https://huggingface.co/ggrizzly/roBERTa-spam-detection](https://huggingface.co/ggrizzly/roBERTa-spam-detection)

I used 3 datasets (outlined in the hf page):
- Original SMS data with a 80/20 train test split
- Disjoint Enron+Telegram test data with SMS as test
- 80/20 uniform distribution of all 3

The results are 92% - 98% accuracy depending on model use and dataset used
| | SMS only accuracy | Disjoint 3 accuracy | Combo'd 3 accuracy |
|:------:|:------:|:------:|:------:|
| Multinominal Naive Bayes | 97.13% | 80.1% | 92.43% |
| -> **KNN** | 96.23% | ***((97.45%))*** | 92.33% |
| XGBoost | 97.49% | 94.42% | 93.99% |
| -> **LightGBM** | ***((97.93%))*** | 92.82% | **93.98%** |
| roBERTa | - | 95.03% | - |
