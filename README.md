# Enhancing Indian Sign Language Translation via Motion-Aware Modeling

### Curated iSign-10k Subset • SpaMo-OF (Code Coming Soon)

This repository provides the **curated iSign-10k subset** used in our paper:

**Enhancing Indian Sign Language Translation via Motion-Aware Modeling**
*Workshop on Sign Language Processing (WSLP), IJCNLP–AACL 2025*
*IIT Bombay, Mumbai, India — December 20, 2025*

The **SpaMo-OF code** (our extension of SpaMo with optical-flow-based motion features) will be released soon.

---

## 📘 Overview

Indian Sign Language (ISL) remains underexplored compared to German, American, or British SLT.
Our work benchmarks multiple SLT models on ISL and proposes **SpaMo-OF**, which enhances SpaMo by incorporating:

* **GMA-based optical flow maps** for robust motion cues

This repository releases the dataset used in achieving these results.

---

## 📂 Dataset Release: iSign-10k Subset

We release a **clean, balanced, noise-filtered 10k sample subset** of the iSign dataset.

### 🔧 How this subset was curated

* Kept sentence lengths between **5–15 words**
* Removed overly short, overly long, or noisy samples
* Applied vocabulary frequency grouping (rare / mid-frequency / common)
* Ensured strong coverage of diverse linguistic structures
* Maintained ~200 frames per sample on average

### 📄 Dataset Stats

* **10,000 ISL videos** with English translations
* Average length: **~200 frames**
* More stable and reproducible for SLT modeling

Here is the updated **Download section in clean Markdown**, ready to paste into your GitHub README.
It reflects:
✅ your **uploaded train/val/test CSVs in the `Data/` folder**
✅ the **source iSign dataset link**
✅ a clear explanation of how to use the curated subset.

---

## 📥 Download

This repository includes the curated **iSign-10k subset** used in our experiments.
You can directly access the train, validation, and test splits from the following files:

```
Data/train.csv  
Data/val.csv  
Data/test.csv
```

Each CSV file contains:

* video file names
* corresponding English translations
* cleaned and balanced samples (5–15 words)
* metadata used during our experiments

### 🔗 Source Dataset (iSign)

The curated subset is extracted from the original **iSign** dataset:

👉 **iSign on HuggingFace:**
[https://huggingface.co/datasets/Exploration-Lab/iSign](https://huggingface.co/datasets/Exploration-Lab/iSign)

To fully reproduce the dataset, download the videos from the source iSign repository and map them using our CSV splits.


---

## 🧠 Code Release (Coming Soon)

The complete **SpaMo-OF** pipeline will be released soon, including:

* Multi-scale spatial feature extraction
* GMA-based optical flow computation
* VideoMAE motion feature extraction
* Cross-modal alignment
* LoRA-based multilingual LLM fine-tuning
* Evaluation scripts and utilities

Please ⭐ star the repository to get updates.

---

## 🔗 Upstream Projects Used

Our implementation builds on the following excellent open-source projects:

### SpaMo

Spatial + motion features with LLM alignment
[https://github.com/eddie-euijun-hwang/SpaMo.git](https://github.com/eddie-euijun-hwang/SpaMo.git)

### MMFlow

Optical flow library that includes GMA
[https://github.com/open-mmlab/mmflow](https://github.com/open-mmlab/mmflow)

### GMA (Global Motion Aggregation)

is a transformer-based optical flow model that robustly handles occlusions by modeling long-range pixel dependencies and aggregating global motion cues, producing state-of-the-art flow estimates even in heavily occluded regions.
[https://github.com/zacjiang/GMA](https://github.com/zacjiang/GMA)

Please cite and credit the original authors when using their work.

---

## 📊 Summary of Results

We evaluate SLT models on the curated iSign-10k subset:

* **SLT (GF)** – Transformer-based SLT
* **GFSLT-VLP** – Vision–language contrastive pretraining
* **SpaMo** – Multi-scale visual + motion features
* **SpaMo-OF (ours)** – SpaMo augmented with GMA optical flow

### Key Result

**SpaMo-OF BLEU-4:** **8.58**
This establishes a **strong baseline** for Indian Sign Language translation.

---

## 📜 Citation

If you use the dataset or build upon SpaMo-OF, please cite:

```bibtex
@inproceedings{
anonymous2025enhancing,
title={Enhancing Indian Sign Language Translation via Motion-Aware Modeling},
author={Anonymous},
booktitle={Workshop on Sign Language Processing},
year={2025},
url={https://openreview.net/forum?id=Q4n72lsMLe}
}
```

---

## 📌 License

The curated dataset is released **for research purposes only**.
Users must comply with the original iSign license and usage terms.

---

## 🙏 Acknowledgements

We thank the creators of **iSign**, **SpaMo**, **GMA**, **MMFlow**, and all upstream libraries and datasets that supported this research.
