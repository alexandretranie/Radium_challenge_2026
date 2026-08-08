# Radium Challenge 2026

Image classification — Radium 2026 challenge.

## Setup

This project uses [uv](https://docs.astral.sh/uv/) for dependency management.

```bash
git clone <repo-url>
cd Radium_challenge_2026
uv sync
```

`uv sync` recreates the environment exactly from `uv.lock` (Python 3.12, PyTorch 2.13).
No manual activation needed — just prefix commands with `uv run`.

```bash
uv run python train.py
uv run jupyter lab
```

## Data

**The data is not versioned** (255 MB of labels plus 2500 images, beyond GitHub's limits).
Download it from the challenge platform and place it at the project root:

```
Radium_challenge_2026/
├── label_Hnl61pT.csv       # labels (255 MB)
├── annotated_labels.json   # annotations, 2000 entries
├── train-images/           # 2000 images
└── test-images/            # 500 images
```

## Environment

| | |
|---|---|
| Python | 3.12.12 |
| PyTorch | 2.13.0 (MPS acceleration on Apple Silicon) |
| torchvision | 0.28.0 |
| pandas | 3.0.5 |
| scikit-learn | 1.9.0 |

Check that the GPU is available:

```bash
uv run python -c "import torch; print(torch.backends.mps.is_available())"
```

## Dependencies

```bash
uv add <package>      # add
uv remove <package>   # remove
uv tree               # dependency tree
```
