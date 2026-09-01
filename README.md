# English–Hindi Neural Machine Translation: NLLB vs mBART vs MADLAD

Comparative evaluation of three state-of-the-art multilingual translation models — **NLLB-200**, **mBART-50**, and **MADLAD-400** — on English↔Hindi translation, fine-tuned and benchmarked on the IIT Bombay English-Hindi parallel corpus.

## Overview

This project explores how three different pretrained multilingual translation architectures perform on a low-resource-adjacent language pair (English–Hindi) after fine-tuning on the same dataset. Each notebook loads a pretrained model, fine-tunes it on parallel sentence pairs, and evaluates translation quality using BLEU scores.

| Notebook | Model | Base Checkpoint |
|---|---|---|
| `nllb_translation.ipynb` | NLLB-200 (distilled) | `facebook/nllb-200-distilled-600M` |
| `mbart_translation.ipynb` | mBART-50 | `facebook/mbart-large-50` |
| `madlad_translation.ipynb` | MADLAD-400 | `jbochi/madlad400-3b-mt` |

## Dataset

[IIT Bombay English-Hindi Parallel Corpus](https://www.cfilt.iitb.ac.in/iitb_parallel/) (`IITB.en-hi.en` / `IITB.en-hi.hi`) — sentence-aligned English-Hindi pairs.

> **Note:** The corpus files are not included in this repo due to size/licensing. Download them separately and place them in your Google Drive (the notebooks expect `/content/drive/MyDrive/IITB.en-hi.en` and `.hi` when run on Colab).

## Tech Stack

- Python, PyTorch
- 🤗 Hugging Face `transformers`, `datasets`, `accelerate`
- `sentencepiece` for tokenization
- `evaluate` + `sacrebleu` for BLEU scoring
- Google Colab (GPU runtime recommended)

## Setup

1. Open a notebook in [Google Colab](https://colab.research.google.com/).
2. Mount your Google Drive and ensure the IITB corpus files are placed as expected.
3. Run cells top to bottom — dependencies are installed via `pip` at the top of each notebook.
4. GPU runtime strongly recommended (`Runtime` → `Change runtime type` → `GPU`).

## Results

BLEU scores are computed via `sacrebleu` on a held-out test split. See each notebook's final cells for exact scores and sample translations.

## Repo Structure

```
.
├── nllb_translation.ipynb
├── mbart_translation.ipynb
├── madlad_translation.ipynb
├── README.md
└── .gitignore
```

## License

Specify a license here (e.g. MIT) if you intend to share this publicly.
