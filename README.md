# Indian Cuisine Classification Framework — A Culturally Contextualized Image Dataset for Statistical Learning Education
## Abstract

This study presents a deep learning-based approach for the classification of Indian food images, addressing the challenges posed by high intra-class variability and inter-class similarity in food recognition tasks. The proposed system leverages convolutional neural networks and data-driven learning techniques to accurately identify diverse categories of Indian cuisine. The model is evaluated using standard performance metrics, demonstrating its effectiveness in real-world applications such as dietary monitoring, automated food recognition, and intelligent recommendation systems.

---

## Introduction

Food image classification has emerged as a significant area of research within computer vision due to its applications in health informatics, smart dining systems, and cultural data analysis. Indian cuisine, characterized by its diversity and visual similarity across dishes, presents unique challenges for classification models. This project aims to develop a robust and scalable classification framework capable of handling such complexities.

---

## Dataset Description

The dataset consists of labeled images representing various Indian food categories. It captures variations in presentation, lighting conditions, and background settings to enhance model generalization.

Due to GitHub file size limitations, the dataset is hosted externally.

Dataset Access:
https://drive.google.com/file/d/1aEPoatOrExLkaM6NuZG0QOFyilLbUcR9/view?usp=sharing

---

## Methodology

The proposed approach follows a structured pipeline:

1. Data Preprocessing: Image resizing, normalization, and augmentation techniques are applied to improve model robustness.
2. Feature Extraction: Deep convolutional layers are used to automatically learn hierarchical features from input images.
3. Model Training: The model is trained using supervised learning with labeled data.
4. Optimization: Hyperparameter tuning and regularization techniques are applied to improve performance and prevent overfitting.

---

## Model Architecture

The system is based on deep learning architectures such as Convolutional Neural Networks (CNNs), with potential integration of transfer learning models (e.g., ResNet or similar architectures) to enhance accuracy and efficiency.

---

## Evaluation Metrics

The performance of the model is evaluated using the following metrics:

* Accuracy
* Precision
* Recall
* F1-Score
* BLEU Score (if applicable for comparative evaluation)
* Confusion Matrix Analysis

---

## Experimental Results

The model demonstrates reliable classification performance across multiple food categories. The results indicate that deep learning approaches are effective in capturing complex visual patterns inherent in Indian cuisine. Further improvements can be achieved through larger datasets and advanced architectures.

---

## Reproducibility Instructions

To reproduce the results:

1. Clone the repository:

```id="v1k3xp"
git clone https://github.com/your-username/your-repo-name.git
```

2. Navigate to the project directory:

```id="z6o7qe"
cd your-repo-name
```

3. Download the dataset from the provided link.

4. Extract and place the dataset in:

```id="0k7dtn"
/data
```

5. Run the training and evaluation scripts as provided in the repository.

---

## Project Structure

```id="g9p2sd"
├── data/               # Dataset (external)
├── src/                # Source code
├── models/             # Trained models
├── notebooks/          # Experimental notebooks
├── README.md
```
## Limitations

* Limited dataset size may affect generalization
* High visual similarity between certain food categories
* Performance may vary under different real-world conditions

---

## Future Work

* Integration of larger and more diverse datasets
* Implementation of advanced architectures such as Vision Transformers
* Deployment as a scalable web or mobile application
* Real-time food recognition using embedded systems

---

## Contributors

Sneha Attarde

---

## License

This work is intended for academic and research purposes. Proper citation is recommended for reuse.
