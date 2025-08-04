# Leukemia


This repository contains training pipelines and experiments for **leukemia cell detection** 

- **ViT-MAE**: Masked Autoencoders trained from scratch or initialized from ImageNet-1K.
- **DINO**: Self-supervised learning using Facebook AI’s DINO method.

> Built upon official repositories via Git submodules and customized for leukemia-specific datasets.

---

## Project Structure
---
 
leukemia/
│
├── datasets/ image dataset
│
├── external_module/
│ ├── transformers/ # Forked from HuggingFace Transformers (ViT-MAE)
│ └── dino/ # Forked from Facebook DINO repo
│
├── results/ # Outputs saved under respective image folder names
│
├── scripts/ # Helper scripts (to be added later)
│
└── README.md 



---

## Setup Instructions

### 1. Clone the repository with submodules

```bash
git clone --recurse-submodules https://github.com/YourUsername/leukemia.git
```

If you already cloned it without submodules:

```bash
git submodule update --init --recursive
```

### 2. Setup Python Environments  

- **uv** 
Each submodule has its own environment and requirements.txt.

Install uv (if not already)
```bash
pip install uv
```


- Setup environment for transformers (ViT-MAE)
```bash 
cd external_module/transformers
uv venv --python=3.10
uv pip install -r requirements.txt
```

- Setup environment for dino
```bash
cd external_module/dino
uv venv --python=3.10
uv pip install -r requirements.txt
```

### 3. Training

Once environments are set up:

Activate the environment  ``source .venv/bin/activate``

Run training commands depending on whether you're using ViT-MAE or DINO.

### 4. Results

Training scripts will save results under the results/ directory, named by image folder.

Example usage or training command docs will be added later in scripts/.

---


***Notes on Submodules***
1. external_module/transformers: Forked from HuggingFace, using leukemia-train branch.
2. external_module/dino: Forked from Facebook Research, using dino-train branch.

Each submodule has its own pinned dependencies for reproducibility.

To update submodules:

```bash
cd external_module/<module>
git checkout leukemia-train # or dino-train
git pull origin leukemia-train
``` 