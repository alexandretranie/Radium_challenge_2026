# Radium Challenge 2026

Classification d'images — challenge Radium 2026.

## Installation

Le projet utilise [uv](https://docs.astral.sh/uv/) pour la gestion des dépendances.

```bash
git clone <url-du-depot>
cd Radium_challenge_2026
uv sync
```

`uv sync` recrée l'environnement à l'identique depuis `uv.lock` (Python 3.12, PyTorch 2.13).
Aucune activation manuelle n'est nécessaire : préfixer les commandes par `uv run`.

```bash
uv run python train.py
uv run jupyter lab
```

## Données

**Les données ne sont pas versionnées** (255 Mo de labels + 2500 images, au-delà des
limites GitHub). Elles sont à récupérer depuis la plateforme du challenge et à placer
à la racine du projet :

```
Radium_challenge_2026/
├── label_Hnl61pT.csv       # labels (255 Mo)
├── annotated_labels.json   # annotations, 2000 entrées
├── train-images/           # 2000 images
└── test-images/            # 500 images
```

## Environnement

| | |
|---|---|
| Python | 3.12.12 |
| PyTorch | 2.13.0 (accélération MPS sur Apple Silicon) |
| torchvision | 0.28.0 |
| pandas | 3.0.5 |
| scikit-learn | 1.9.0 |

Vérifier que le GPU est disponible :

```bash
uv run python -c "import torch; print(torch.backends.mps.is_available())"
```

## Dépendances

```bash
uv add <paquet>      # ajouter
uv remove <paquet>   # retirer
uv tree              # arbre des dépendances
```
