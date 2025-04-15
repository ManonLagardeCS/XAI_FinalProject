# XAI_FinalProject : Interpretable Deep Learning for Cancer Detection

## 🧠 Project Overview

This project investigates **explainability techniques** applied to deep learning models trained on the **PatchCamelyon (PCam)** dataset, a benchmark for histopathological image classification. We focus on understanding the internal decision logic of two types of architectures:  
- **U-Net (CNN)**  
- **ViT (Vision Transformer)**  

We explore and evaluate various **XAI (Explainable AI)** methods including:
- Gradient-based (e.g., Saliency Maps, GradCAM, Integrated Gradients)
- Perturbation-based (e.g., Occlusion)
- Model-agnostic (e.g., LIME, SHAP)
- Concept-based (e.g., CRAFT)

## 🎯 Objectives

- Provide visual and quantitative insight into how models detect cancerous tissue
- Compare the faithfulness and interpretability of different explanation methods
- Understand how model architecture impacts explainability
- Evaluate explanations using Deletion, Insertion, and Fidelity metrics

---

## 🗂️ Repository Structure

```
📁 notebooks/
 ├── XAI_CRAFT_Patchcam.ipynb       # CRAFT concept extraction and visualization
 └── XAI_Evaluation_Patchcam.ipynb  # Evaluation of various XAI methods

📄 Interpretable Deep Learning for Cancer.pdf  # Full project report
📄 XAI.pdf                                     # Project presentation slides
📄 README.md                                   # Project description (this file)
```

---

## 🧬 Dataset

**PatchCamelyon (PCam)**:
- 327,680 RGB histopathological image patches (96x96)
- Binary classification: metastatic (1) or benign (0)
- Derived from Camelyon16 challenge
- Preprocessed (resized to 224x224, normalized, split into train/val/test)

---

## 🏗️ Models Used

| Model          | Description |
|----------------|-------------|
| **MobileNetV2** | Lightweight CNN, used for benchmarking XAI techniques |
| **U-Net**       | Encoder-decoder CNN, adapted for classification |
| **ViT-S/16**    | Vision Transformer pretrained with DINO self-supervision |

---

## 🧪 Explainability Methods

| Category            | Methods                                    |
|---------------------|---------------------------------------------|
| **Gradient-Based**  | Saliency Maps, GradCAM, Integrated Gradients |
| **Perturbation-Based** | Occlusion, RISE                          |
| **Model-Agnostic**  | LIME, SHAP                                  |
| **Concept-Based**   | CRAFT (Concept Recursive Activation Factorization) |

---

## 📊 Evaluation Metrics

We use the following **quantitative metrics** to assess explanation quality:

- **Deletion**: Measures drop in prediction when important pixels are removed  
- **Insertion**: Measures confidence recovery when important pixels are added  
- **Fidelity**: Correlation between explanations and model sensitivity  

CRAFT uses **Sobol indices** to measure the importance of discovered visual concepts.

---

## 🧠 Key Findings

- **Integrated Gradients** showed consistently high fidelity and balanced performance
- **LIME** achieved the highest insertion score, effective for black-box interpretation
- **Occlusion** excelled at deletion, highlighting critical regions
- **CRAFT** revealed clinically-relevant visual concepts like hyperchromasia and tissue disorganization, especially in **U-Net** and **ViT**

---

## 🏥 Clinical Impact

Concept-based methods such as **CRAFT** offer reusable, semantically meaningful insights aligned with **pathological reasoning**, making them suitable for future integration into clinical decision-support systems.

---

## 👩‍🔬 Authors

- **Chaimae Sadoune** – chaimae.sadoune@student-cs.fr  
- **Manon Lagarde** – manon.lagarde@student-cs.fr  
Supervised by: **Céline Hudelot** (CentraleSupélec)

---
