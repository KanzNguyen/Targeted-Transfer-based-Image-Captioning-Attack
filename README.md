# Targeted Adversarial Attack on Vision-Language Models

**Thesis project — VNU-HCM University of Information Technology.**

---

## Overview

This repository contains code for targeted adversarial attacks on vision-language models (VLMs) in image captioning tasks. This project extends the **Chain-of-Attack** framework by integrating:
* **GA-optimized surrogate ensembles**
* **Input diversity**
* **Deep CCA-based common space embedding**.

---

## Repository Structure

```text
BLIP2/
    blip2 ensemble.ipynb               # Simple surrogate ensemble
    blip2 DI.ipynb                     # Ensemble + input diversity (adv images)
    blip2 DI full.ipynb                # Ensemble + input diversity (ori, tgt, adv)
    blip2 DI feature alignment.ipynb   # Full pipeline: ensemble + DI + Deep CCA
Git-base/    # Same structure as BLIP2/
Img2Prompt/  # Same structure as BLIP2/
Kosmos2/     # Same structure as BLIP2/
OFA-base/    # Same structure as BLIP2/
Tag2Text/    # Same structure as BLIP2/
UniDiffuser/ # Same structure as BLIP2/
deepCCA/
    deepmcca_256_with_scalers_and_encoders.pkl  # Pretrained Deep CCA weights
image generation.ipynb  # Inference: generate target images
train MLP.ipynb         # Train MLP with Deep CCA
```

## Datasets

- **Test images (1k subset)**: [Kaggle Dataset](https://www.kaggle.com/datasets/sealeopard/1k-images)
- **MS-COCO**: [Kaggle Dataset](https://www.kaggle.com/datasets/nikhil7280/coco-image-caption)

---

## Pretrained Weights

Download the following weights and upload to Kaggle as a dataset before running notebooks.

- **ClipCap** (surrogate): [Google Drive](https://drive.google.com/file/d/1IdaBtMSvtyzF0ByVaBHtvM0JYSXRExRX)
- **BLIP base** (surrogate): [Salesforce](https://storage.googleapis.com/sfr-vision-language-research/BLIP/models/model_base.pth)
- **BLIP large** (surrogate): [Salesforce](https://storage.googleapis.com/sfr-vision-language-research/BLIP/models/model_base_capfilt_large.pth)
- **BEiT-3** (surrogate): [GitHub Release](https://github.com/addf400/files/releases/download/beit3/beit3_large_patch16_384_coco_retrieval.pth)
- **Tag2Text** (target): [Hugging Face](https://huggingface.co/spaces/xinyu1205/recognize-anything/blob/main/tag2text_swin_14m.pth)

---

## Running the Notebooks

All notebooks are designed to run on **Kaggle** (free GPU).

1. Upload datasets and pretrained weights to Kaggle as datasets.
2. Open the desired notebook on Kaggle.
3. Update dataset paths if necessary.
4. Run all cells.

---

## Acknowledgements

This project implements and extends the attack pipeline described in:
- [Chain-of-Attack (CVPR 2025)](https://openaccess.thecvf.com/content/CVPR2025/papers/Xie_Chain_of_Attack_On_the_Robustness_of_Vision-Language_Models_Against_CVPR_2025_paper.pdf) — original paper

**Code and weights used from:**
- [ClipCap](https://github.com/rmokady/CLIP_prefix_caption)
- [AICAttack](https://github.com/UTSJiyaoLi/AICAttack) — dataloader
- [Tag2Text](https://github.com/mattmazzola/Tag2Text)
- [BEiT-3](https://github.com/fonzi22/unilm)
- [OFA](https://github.com/OFA-Sys/OFA)
- [LAVIS](https://github.com/salesforce/LAVIS)

**Pretrained weights:**
- [BLIP](https://github.com/salesforce/BLIP)
- [BEiT-3 weights](https://github.com/addf400/files/releases)
