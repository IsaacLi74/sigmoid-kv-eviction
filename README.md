# Sigmoid KV Eviction

Code for **Sigmoid Attention as a Better Substrate for Learned KV Cache Eviction**  
ICML 2026 AdaptFM Workshop

This repository contains the notebooks and artifacts for a controlled GPT-2-scale experiment on learned KV-cache eviction. Because the models are GPT-2 scale, the experiments are designed to be simple to inspect and reproducible in Google Colab.

## Overview

The experiments compare:

- Softmax vs. sigmoid attention
- Dense vs. learned-gate models
- RoPE vs. NoRoPE settings

The main question is whether sigmoid attention provides a better substrate for transferring a soft training-time KV-retention gate into hard physical KV-cache deletion at inference time.

## Files

```text
.
├── paper/        # camera-ready paper files
├── notebooks/   # Colab notebooks for training and evaluation
├── figures/     # paper figures
├── results/     # exported result tables
├── requirements.txt
├── LICENSE
└── README.md
```

## Reproduction

Open the notebooks in `notebooks/` with Google Colab and run them in numerical order.

```text
01_Data_Preparation.ipynb
02/03/04/05_*_Train_*.ipynb
06_Tau_Selection.ipynb
07_Headline_Results.ipynb
08_Mechanism_Evidence.ipynb
09_Token_Interpretability.ipynb
```

The main evaluation uses sequence length 512, with 384 tokens for prefill and 128 tokens for decode.

## Note

Large training artifacts such as datasets and checkpoints are not included. The notebooks are provided for reproducibility and inspection.

## Citation

```bibtex
@inproceedings{li2026sigmoidkv,
  title     = {Sigmoid Attention as a Better Substrate for Learned KV Cache Eviction},
  author    = {Li, Isaac},
  booktitle = {ICML 2026 Workshop on Resource-Adaptive Foundation Model Inference},
  year      = {2026}
}
```

## License

MIT License.
