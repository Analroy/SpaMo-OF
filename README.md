# Enhancing Indian Sign Language Translation via Motion-Aware Modeling

### Curated iSign-10k Subset • SpaMo-OF (Dataset Release)

This repository provides the **curated iSign-10k subset** used in our paper:

**Enhancing Indian Sign Language Translation via Motion-Aware Modeling**
*Workshop on Sign Language Processing (WSLP), IJCNLP–AACL 2025*
*IIT Bombay, Mumbai, India — December 20, 2025*

This repository contains only the **curated dataset splits**.
SpaMo-OF can be easily reproduced using existing implementations of SpaMo, GMA, and MMFlow.

---

## 📘 Overview

Indian Sign Language (ISL) remains underexplored compared to German, American, or British SLT.
Our work benchmarks multiple SLT models on ISL and introduces **SpaMo-OF**, which augments SpaMo using:

* **GMA-based optical flow maps** for robust and occlusion-resilient motion cues

This repository releases the curated dataset used in our experiments.

---

## 📂 Dataset Release: iSign-10k Subset

We release a **clean, balanced, noise-filtered 10k sample subset** derived from the original iSign dataset.

### 🔧 How This Subset Was Curated

* Kept sentence lengths between **5–15 words**
* Removed extremely short, long, or noisy samples
* Used vocabulary frequency grouping (rare / mid / common)
* Ensured wide linguistic diversity
* Maintained ~200 frames per sample (average)

### 📄 Dataset Stats

* **10,000 ISL signing videos**
* English textual translations
* Balanced linguistic coverage
* More stable and reproducible for SLT modeling

---

## 📥 Download

This repository includes the curated **iSign-10k** splits used in our experiments.
You can access them directly:

```
Data/train.csv  
Data/val.csv  
Data/test.csv
```

Each CSV includes:

* video file names
* English translations
* curated and cleaned samples
* metadata used during training

### 🔗 Source Dataset (iSign)

The curated subset originates from the full **iSign** dataset:

👉 **iSign HuggingFace Dataset:**
[https://huggingface.co/datasets/Exploration-LLab/iSign](https://huggingface.co/datasets/Exploration-LLab/iSign)

To fully reconstruct the dataset, download video files from iSign and align them using our CSV splits.

---

## 🧠 Code Availability

SpaMo-OF can be easily implemented using existing open-source projects:

* SpaMo (multi-scale spatial + motion features + LLM alignment)
* MMFlow (for optical flow pipelines)
* GMA (occlusion-robust optical flow)
* VideoMAE (motion encoding)
* Flan-T5 / LLaMA / T5 models with LoRA tuning

These components allow straightforward replication of our pipeline.

---

## 🔗 Upstream Projects Used

Below are the primary open-source resources used in our work:

### SpaMo

Spatial + motion features with LLM alignment
[https://github.com/eddie-euijun-hwang/SpaMo.git](https://github.com/eddie-euijun-hwang/SpaMo.git)

### MMFlow

Optical flow library that provides GMA
[https://github.com/open-mmlab/mmflow](https://github.com/open-mmlab/mmflow)

### GMA (Global Motion Aggregation)

Transformer-based optical flow model that handles occlusions by capturing long-range pixel dependencies and aggregating global motion cues—highly effective for hand/arm occlusions in sign language videos.
[https://github.com/zacjiang/GMA](https://github.com/zacjiang/GMA)

Please cite and acknowledge the original authors when using their work.

---

## 📊 Summary of Results

We evaluated several SLT models on the curated iSign-10k subset:

* **SLT (GF)** – Transformer-based SLT
* **GFSLT-VLP** – Vision–language contrastive pretraining
* **SpaMo** – Multi-scale spatial + motion features
* **SpaMo-OF (ours)** – SpaMo enhanced with GMA-based optical flow

### Key Result (iSign-10k)

**SpaMo-OF BLEU-4:** **8.58**
A strong baseline for future Indian Sign Language translation research.

---

## 📜 Citation

If you use the curated dataset or related resources, please cite:

```bibtex
@inproceedings{chowdhury-sanyal-2025-enhancing,
    title = "Enhancing {I}ndian {S}ign {L}anguage Translation via Motion-Aware Modeling",
    author = "Chowdhury, Anal Roy  and
      Sanyal, Debarshi Kumar",
    editor = "Hasanuzzaman, Mohammed  and
      Quiroga, Facundo Manuel  and
      Modi, Ashutosh  and
      Kamila, Sabyasachi  and
      Artiaga, Keren  and
      Joshi, Abhinav  and
      Singh, Sanjeet",
    booktitle = "Proceedings of the Workshop on Sign Language Processing (WSLP)",
    month = dec,
    year = "2025",
    address = "IIT Bombay, Mumbai, India (Co-located with IJCNLP{--}AACL 2025)",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.wslp-main.7/",
    pages = "39--46",
    ISBN = "979-8-89176-304-3",
    abstract = "Sign language translation (SLT) has witnessed rapid progress in the deep learning community across several sign languages, including German, American, British, and Italian. However, Indian Sign Language (ISL) remains relatively underexplored. Motivated by recent efforts to develop large-scale ISL resources, we investigate how existing SLT models perform on ISL data. Specifically, we evaluate three approaches: (i) training a transformer-based model, (ii) leveraging visual-language pretraining, and (iii) tuning a language model with pre-trained visual and motion representations. Unlike existing methods that primarily use raw video frames, we augment the model with optical flow maps to explicitly capture motion primitives, combined with a multi-scale feature extraction method for encoding spatial features (SpaMo-OF). Our approach achieves promising results, obtaining a BLEU-4 score of 8.58 on the iSign test set, establishing a strong baseline for future ISL translation research."
}
```

---

## 📌 License

The curated dataset is released **for research purposes only**.
Please follow the licensing terms of the original iSign dataset when using the videos.

---

## 🙏 Acknowledgements

We thank the creators of:

* **iSign**
* **SpaMo**
* **GMA**
* **MMFlow**
* and other supporting frameworks

for enabling this research.
