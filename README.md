# Trustworthy_multimodal_AI_for_skin_cancer_detection
A multimodal deep‐learning framework that combines skin lesion images with patient metadata (e.g., Fitzpatrick type) to build a fair, explainable, and robust skin cancer diagnostic model across diverse skin tones.



````markdown
# Trustworthy Multimodal AI for Skin Cancer Detection

Group 1, 2025 CEAMLS Summer AI Research Institute  
Faculty: Dr. Saroj Pramanik

---

##  Overview

Early detection of skin cancer is critical—but most AI tools rely solely on images and often underperform on darker skin tones. Our project addresses this bias by combining lesion images with patient metadata (e.g., Fitzpatrick skin type) to build a fair, explainable, and robust deep-learning model for skin cancer diagnosis.

---

##  Team

- Mentor: Blessing Isoyiza Adeika  
- Students:
  - Cara Hicks  
  - Crystal Onyeama  
  - Kenidee Blakey  
  - Omotolani Bello  

---

##  Repository Structure


├── data/  
│   ├── raw/                    # Original datasets (download before preprocessing)  
│   └── processed/              # Cleaned, merged, balanced CSVs & images  
├── notebooks/                  # Exploratory analysis & model prototyping  
├── src/                        
│   ├── data_cleaning.py        # Scripts to normalize & merge datasets  
│   ├── dataset_builder.py      # Code to balance & split images/metadata  
│   ├── train_cnn.py            # CNN training pipeline  
│   └── utils.py                # Helper functions (e.g., loaders, metrics)  
├── models/                     # Saved model weights & artifacts  
├── README.md                   
└── requirements.txt            # `pip install -r requirements.txt`
````

---

# Datasets

We sourced three public skin-lesion datasets to ensure diverse Fitzpatrick representation:

1. [Mendeley Data: ISIC Skin Lesion Dataset](https://data.mendeley.com/datasets/zr7vgbcyr2/1)
2. [Hospital Italiano de Buenos Aires ISIC Archive](https://api.isic-archive.com/doi/hospital-italiano-de-buenos-aires-skin-lesions/)
3. [Stanford AIMI Training Datasets](https://stanfordaimi.azurewebsites.net/datasets/35866158-8196-48d8-87bf-50dca81df965)

> Note: Download each into `data/raw/` before running preprocessing scripts.

---

# Installation

1. Clone the repo

   ```bash
   git clone https://github.com/blessadeik/Trustworthy_multimodal_AI_for_skin_cancer_detection.git
   cd Trustworthy_multimodal_AI_for_skin_cancer_detection
   ```

2. Create a virtual environment

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```

---

# Usage

1. Preprocess & merge datasets

   ```bash
   python src/data_cleaning.py \
     --input-dir data/raw/ \
     --output-dir data/processed/
   ```

2. Balance & split data

   ```bash
   python src/dataset_builder.py \
     --input-csv data/processed/merged.csv \
     --output-dir data/processed/
   ```

3. Train the CNN model

   ```bash
   python src/train_cnn.py \
     --train-dir data/processed/train/ \
     --test-dir  data/processed/test/ \
     --output-dir models/
   ```

4. Evaluate & visualize

   * Check `models/` for saved weights and training logs.
   * Open notebooks in `notebooks/` to explore metrics, plots, and explainability analyses.

---

# Results & Next Steps

* Fairness Evaluation: We integrate an adversarial branch to de-bias representations by Fitzpatrick type.
* Explainability: Grad-CAM visualizations and SHAP analysis live in `notebooks/`.
* Future Work: Extend to multi-label classification, deploy via a web app, and audit on external clinical sets.

---

# Contact

For questions or collaboration, please reach out to **Blessing Adeika** at *[blessadeik@gmail.com](mailto:blessadeik@gmail.com)*.

---

> *“Equitable AI saves lives—one pixel at a time.”*
> — Group 1, 2025 CEAMLS Summer AI Research Institute

```
```
