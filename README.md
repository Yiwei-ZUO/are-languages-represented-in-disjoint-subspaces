# Are Languages Represented in Disjoint Subspaces?

This repository contains the Jupyter notebook for Part 2 of the Multilingual NLP Lab 2. It investigates how multilingual BERT (mBERT) represents six languages across its embedding layer and twelve Transformer layers.

## Contents

- `m2_lab2_zuo_code.ipynb`: code, experiments, results, and answers for Part 2 (Questions 14–53) and the Synthesis (Questions 77–80)
- `representations/`: cached mBERT sentence representations for the six languages and two data splits

The experiments cover:

- sentence-representation geometry and anisotropy;
- rogue dimensions and standardisation;
- language identification before and after centring;
- cross-lingual sentence retrieval;
- principal-subspace overlap;
- cross-lingual domain classification.

## Data and model

- Model: [`google-bert/bert-base-multilingual-cased`](https://huggingface.co/google-bert/bert-base-multilingual-cased)
- Dataset: [`openlanguagedata/flores_plus`](https://huggingface.co/datasets/openlanguagedata/flores_plus)
- Languages: English, French, German, Russian, Chinese, and Yoruba

FLORES+ is a gated dataset. Request access on Hugging Face and authenticate before running the notebook. Do not commit your access token.

## Requirements

```bash
pip install jupyter numpy pandas matplotlib torch transformers datasets huggingface_hub scikit-learn
```

Open and run the notebook in order:

```bash
jupyter notebook m2_lab2_zuo_code.ipynb
```

The notebook loads the cached `.npy` files from `representations/`, so the experiments can be reproduced without extracting all mBERT representations again.

## Summary

The results show substantial shared geometry across languages, especially in the middle layers. Per-language centring removes most linearly decodable language identity and improves cross-lingual retrieval. Yoruba remains less strongly aligned with English than the other languages in the experiment.
