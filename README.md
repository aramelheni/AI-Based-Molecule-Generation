# AI-Powered Drug Discovery Pipeline

A production-ready transformer-based molecular generation and property prediction system for drug discovery, featuring reward-guided sampling, scaffold conditioning, and multi-task learning.

[![Kaggle](https://img.shields.io/badge/Kaggle-View%20Notebook-blue)](your-kaggle-link)
[![Python](https://img.shields.io/badge/Python-3.12-blue)](https://www.python.org/)
[![RDKit](https://img.shields.io/badge/RDKit-2025.9.3-green)](https://www.rdkit.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.8.0-red)](https://pytorch.org/)

## 🚀 Overview

This project implements a complete AI-driven drug discovery pipeline that generates novel, drug-like molecules using transformer-based language models and multi-task property prediction. The system combines:

- Generative Models: GRU and Transformer language models trained on SMILES strings
- Property Predictors: Multi-task transformer for pIC50, logP, and QED prediction
- Reward-Guided Search: Active filtering mechanism for quality-focused generation
- Scaffold Conditioning: Targeted exploration of chemical space around seed structures

### Key Statistics

- Dataset: 15,037 validated drug-like molecules
- Vocabulary Size: 36 chemical tokens
- Model Parameters: ~4.3M (language model), ~3.2M (predictors)
- Generation Quality: 70-85% valid SMILES, 80%+ drug-likeness (QED ≥ 0.5)
- Novelty: 60-70% of generated molecules not in training set

## ✨ Features

- Multiple Sampling Strategies (temperature, beam, top-k, nucleus)
- Conditioning modes (scaffold, property-guided, unconditioned)
- RDKit validation, synthesizability scoring, diversity metrics

## 🏗️ Pipeline Architecture

```text
INPUT → GENERATION MODELS (GRU / Transformer) → REWARD-GUIDED SEARCH → PROPERTY PREDICTION → RANKING & FILTERING → OUTPUT
```

## 📦 Installation

This notebook is hosted on Kaggle where required packages are available in the environment. To run on Kaggle, open the notebook and "Run" — no `requirements.txt` is necessary.

If you need to run locally, create a virtual environment and install the minimal packages used in the notebook (example):

```bash
python -m venv venv
source venv/bin/activate
pip install torch gradio rdkit pandas numpy scikit-learn matplotlib tqdm
```

## 🎬 Quick Start

```python
from model import sample_smiles
smiles = sample_smiles(lm_model, max_len=150, temperature=0.8)
```

## 🔧 Core Components

- Tokenization, encoding/decoding utilities
- Transformer-based language model and multi-task predictors
- Reward and filtering utilities using RDKit

## ⚙️ Generation Modes

- Mode 1: Generate & Filter (fast)
- Mode 2: Reward-Guided Search (quality-focused)
- Mode 3: Scaffold-Conditioned (targeted)

## 🏛️ Model Architecture

Transformer LM (causal) and shared encoder multi-task predictor.

## 🏋️ Training

Hyperparameters and training loop examples are provided in the notebook.

## 📊 Evaluation Metrics

- SMILES validity, QED, novelty, diversity, prediction MAE/RMSE

## 📈 Results

Top generated molecules, diversity analysis, and temperature sweep summaries are in the notebook.

## ⚙️ Configuration

Pipeline configuration dataclass and examples are available in the code.

## 🏭 Production Features

- Logging, checkpointing, memory management, and export utilities.

## License

[MIT](LICENSE)

---

Made with ❤️ for drug discovery
