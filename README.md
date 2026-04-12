# Indian Cuisine Classification Framework — A Culturally Contextualized Image Dataset for Statistical Learning Education

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Dataset](https://img.shields.io/badge/Dataset-Google%20Drive-green.svg)](https://drive.google.com/file/d/1aEPoatOrExLkaM6NuZG0QOFyilLbUcR9/view?usp=sharing)
[![Notebook](https://img.shields.io/badge/Code-Jupyter%20Notebook-orange.svg)](foodclassification.ipynb)

---

## Authors

| Name | Role |
|---|---|
| **Dr. Swati Shinde** | Mentor / Supervisor |
| **Sneha Attarde** | Lead Researcher |
| **Khushi Dudhalkar** | Researcher |
| **Ritul Aloorkar** | Researcher |

---

## Abstract

This study presents a deep learning-based framework for the classification of Indian food images, addressing the challenges posed by high intra-class variability and inter-class similarity in food recognition tasks. The proposed system leverages Convolutional Neural Networks (CNNs) and data-driven learning techniques to accurately identify diverse categories of Indian cuisine. The dataset is designed to serve as a pedagogically valuable resource for instructors and students in statistical learning and data science education courses. The model is evaluated using standard performance metrics, demonstrating its effectiveness in real-world applications such as dietary monitoring, automated food recognition, and intelligent recommendation systems.

---

## Introduction

Food image classification has emerged as a significant area of research within computer vision due to its applications in health informatics, smart dining systems, and cultural data analysis. Indian cuisine, characterized by its remarkable diversity and visual similarity across dishes, presents unique and non-trivial challenges for classification models. This project develops a robust and scalable classification framework capable of handling such complexities, while simultaneously serving as an instructional case study for statistical learning concepts including feature extraction, model selection, and classification evaluation.

---

## Dataset Description

The dataset consists of labeled images representing various Indian food categories. It captures variations in presentation, lighting conditions, and background settings to enhance model generalization.

**Due to GitHub file size limitations, the dataset is hosted externally.**

### Dataset Access

> [Download Dataset (Google Drive)](https://drive.google.com/file/d/1aEPoatOrExLkaM6NuZG0QOFyilLbUcR9/view?usp=sharing)

> ⚠️ **Note for Reviewers:** A permanent DOI via Zenodo or OSF will be provided upon acceptance to comply with JSDSE reproducibility requirements.

### Dataset Characteristics

| Property | Details |
|---|---|
| Domain | Indian Cuisine |
| Format | Labeled image files |
| Variability | Lighting, background, presentation style |
| Intended Use | Statistical learning education, image classification research |

---

## Methodology

The proposed approach follows a structured pipeline:

1. **Data Preprocessing** — Image resizing, normalization, and augmentation techniques are applied to improve model robustness.
2. **Feature Extraction** — Deep convolutional layers automatically learn hierarchical features from input images.
3. **Model Training** — Supervised learning with labeled data using CNN-based architectures.
4. **Optimization** — Hyperparameter tuning and regularization techniques are applied to improve performance and prevent overfitting.

---

## Model Architecture

The system is based on Convolutional Neural Networks (CNNs), with integration of transfer learning models (e.g., ResNet) to enhance accuracy and efficiency. The architecture is designed to balance computational efficiency with classification performance across diverse food categories.

---

## Evaluation Metrics

The performance of the model is evaluated using the following standard metrics:

- **Accuracy** — Overall proportion of correctly classified images
- **Precision** — Proportion of true positives among predicted positives per class
- **Recall** — Proportion of true positives among actual positives per class
- **F1-Score** — Harmonic mean of Precision and Recall
- **Confusion Matrix Analysis** — Per-class performance visualization

---

## Experimental Results

The model demonstrates reliable classification performance across multiple food categories. Results indicate that deep learning approaches are effective in capturing complex visual patterns inherent in Indian cuisine. Further improvements can be achieved through larger datasets and more advanced architectures such as Vision Transformers.

---

## Reproducibility Instructions

To reproduce the results:

**1. Clone the repository:**
```bash
git clone https://github.com/Sneha-1608/FoodDataset.git
cd FoodDataset
```

**2. Install dependencies:**
```bash
pip install tensorflow numpy matplotlib scikit-learn opencv-python
```

**3. Download the dataset** from the link above and place it in:
```
/data
```

**4. Run the notebook:**
```bash
jupyter notebook foodclassification.ipynb
```

---

## Project Structure

```
├── foodclassification.ipynb   # Main classification notebook
├── data/                      # Dataset directory (external download required)
├── models/                    # Trained model weights (if applicable)
├── README.md                  # Project documentation
```

---

## Limitations

- Limited dataset size may affect generalization to unseen food items
- High visual similarity between certain food categories poses classification challenges
- Model performance may vary under different real-world lighting and presentation conditions

---

## Future Work

- Integration of larger and more diverse annotated datasets
- Implementation of advanced architectures such as Vision Transformers (ViT)
- Deployment as a scalable web or mobile application
- Real-time food recognition using embedded systems

---

## How to Cite

If you use this dataset or codebase in your research, please cite:

> Shinde, Swati, Attarde, Sneha, Dudhalkar, Khushi, and Aloorkar, Ritul (2026), "Indian Cuisine Classification Framework — A Culturally Contextualized Image Dataset for Statistical Learning Education," *Journal of Statistics and Data Science Education*. [Under Review]

**BibTeX:**
```bibtex
@article{shinde2026indianfood,
  author  = {Shinde, Swati and Attarde, Sneha and Dudhalkar, Khushi and Aloorkar, Ritul},
  title   = {Indian Cuisine Classification Framework --- A Culturally Contextualized Image Dataset for Statistical Learning Education},
  journal = {Journal of Statistics and Data Science Education},
  year    = {2026},
  note    = {Under Review}
}
```

---

## License

This work is licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to share and adapt this material for any purpose, including commercial use, provided appropriate credit is given to the original authors, a link to the license is provided, and any changes made are indicated.

**Suggested citation for reuse:** Shinde, Swati, Attarde, Sneha, Dudhalkar, Khushi, and Aloorkar, Ritul (2026), "Indian Cuisine Classification Framework — A Culturally Contextualized Image Dataset for Statistical Learning Education," *Journal of Statistics and Data Science Education*. [Under Review]

---

*Submitted to the Journal of Statistics and Data Science Education (JSDSE) — American Statistical Association / Taylor & Francis*
