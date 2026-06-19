# EndoAI
Explainable deep learning framework for classifying Endometrioid Adenocarcinoma in H&amp;E histopathology images using DenseNet121, Grad-CAM, and handcrafted features. Validated on external local clinical data from PIMS, Islamabad.

## Overview

Endometrial cancer is one of the most prevalent gynecologic cancers in women worldwide, and its most common subtype — **Endometrioid Adenocarcinoma (EA)** — is traditionally diagnosed through manual examination of Hematoxylin & Eosin (H&E) stained histopathology slides. This process is time-consuming, subjective, and prone to inter-observer variability.

This project presents an **automated, explainable deep learning framework** that classifies H&E histopathology image patches as either:

- **EA** — Endometrioid Adenocarcinoma (cancerous)
- **NE** — Normal Endometrium (healthy)

The framework goes beyond classification accuracy by integrating **Grad-CAM explainability**, **handcrafted feature extraction**, and a **Random Forest validation layer** — making the system interpretable and clinically trustworthy. It was further validated on **external real-world data** from the Pathology Department of PIMS (Pakistan Institute of Medical Sciences), Islamabad.

## Key Features

- **DenseNet121** as the primary deep learning classifier (transfer learning, two-phase fine-tuning)
- **ResNet50** and **MobileNet** as comparative baseline models
- **Grad-CAM heatmaps** for visual explainability — highlights the tissue regions that drive each prediction
- **Handcrafted feature extraction** — color (RGB/HSV), texture (GLCM, LBP), morphological, and spatial distribution features
- **Random Forest classifier** trained on the full handcrafted feature matrix for feature validation and importance analysis (Gini/SHAP)
- **External validation** on annotated whole-slide images from PIMS, Islamabad — completely unseen by the model during training
- **Flask-based diagnostic web tool** with classification, Grad-CAM visualization, feature dashboard, and risk assessment modules

### Diagnostic Web Tool
A Flask-based tool was developed with the following modules:
- **Classification Module** — Upload image → DenseNet121 prediction + confidence score
- **Grad-CAM Module** — Heatmap overlay for visual explanation
- **Feature Dashboard** — Visual display of extracted handcrafted features (graphs, plots)
- **Risk Assessment Module** — Feature-based risk score and tissue characteristic summary

## Tech Stack

| Component | Technology |
|---|---|
| Deep Learning | Python, TensorFlow / Keras |
| Feature Extraction | OpenCV, scikit-image, NumPy |
| Machine Learning | scikit-learn (Random Forest) |
| Explainability | Grad-CAM (custom implementation) |
| Web Tool | Flask, HTML/CSS/JS |
| Data Handling | pandas, NumPy |
| Visualization | Matplotlib, Seaborn |

## External Validation

The model was validated on **real-world clinical data** from PIMS (Pakistan Institute of Medical Sciences), Islamabad. Pathologists manually annotated Regions of Interest (ROIs). ROI patches were extracted and used exclusively for external testing — the model had no prior exposure to this data during training or validation. This confirms the framework's generalizability to diverse, clinically sourced histopathological material.

## Significance

- Assists pathologists in faster, more consistent endometrial cancer diagnosis
- Addresses the black-box problem in clinical AI through Grad-CAM and feature-based explainability
- Validated on both public and real-world local clinical data
- Provides a complete end-to-end diagnostic pipeline — from raw image to interpretable prediction
- Contributes toward the adoption of trustworthy AI in digital pathology workflows

## Citation

If you use this work, please cite:

```
Mahnoor, E., & Aasim, Z. (2026). Explainable Deep Learning Framework for Classification 
of Endometrioid Adenocarcinoma in H&E Histopathology Images. 
BS Thesis, Department of Biosciences, COMSATS University Islamabad.
Supervisor: Dr. Zoya Khalid.
```

## Acknowledgements

We extend our sincere gratitude to our supervisor **Dr. Zoya Khalid** for her continuous guidance and support throughout this project. We also thank the **Pathology Department of PIMS, Islamabad** for providing annotated clinical data for external validation.
