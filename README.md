# Indian Food Image Dataset — Data, Code, and Teaching Materials

Materials supporting the manuscript *Indian Cuisine Classification Framework — A
Culturally Contextualized Image Dataset for Statistical Learning Education*,
submitted to the **Journal of Statistics and Data Science Education**.

**Authors:** Swati Shinde, Sneha Attarde, Khushi Dudhalkar, and Ritul Aloorkar
Department of Computer Engineering, Pimpri Chinchwad College of Engineering, Pune, India

**Archived release:** https://doi.org/10.5281/zenodo.19543423

A 100-class dataset of Indian food photographs, built for teaching statistical
learning rather than for benchmarking, together with four classroom-ready lesson plans
covering stratified splitting, the bias–variance trade-off, multiclass evaluation, and
data augmentation as regularization.

---

## 1. What This Repository Contains

The repository holds everything needed to (a) obtain the dataset, (b) reproduce every
number, table, and figure in the article, and (c) run the four lesson plans in a
classroom without repeating any computation.

| File | What it is | Supports in the article |
|---|---|---|
| `Compressed_dataset.zip` | The full labeled dataset: 4,577 JPEG images in 100 folders, one folder per dish class. The folder name is the class label. | Section 2 (dataset), Table 1, Figure 1 |
| `class_metadata.csv` | One row per class: class name, culinary category, image count, and split allocation. | Section 2.3, Figure 1 |
| `S1_Full_Training_Pipeline.ipynb` | Preprocessing, stratified splitting, model definition, training, and evaluation. Writes the pre-computed outputs consumed by S2–S6. | Sections 3.2–3.4, Table 3, Figure 3 |
| `S2_Lesson1_Data_Splitting.ipynb` | Lesson Plan 1 — stratified train/validation/test splitting and class composition. | Section 4.3, Table 5, Figures 1 and 2 |
| `S3_Lesson2_Bias_Variance.ipynb` | Lesson Plan 2 — the bias–variance trade-off across three model capacities. Includes pre-computed training logs. | Section 4.4, Table 6, Table 3, Figure 3 |
| `S4_Lesson3_Confusion_Matrix.ipynb` | Lesson Plan 3 — confusion matrix and multiclass evaluation. Includes pre-computed test predictions for all 100 classes. | Section 4.5, Table 7, Figures 4 and 5 |
| `S5_Lesson4_Data_Augmentation.ipynb` | Lesson Plan 4 — data augmentation as regularization. | Section 4.6, Table 8, Figure 2 |
| `S6_Per_Class_Metrics.ipynb` | Per-class precision, recall, and F1-score for all 100 classes, plus the full confusion matrix in tabular form. | Section 3.5, Figure 6 |
| `S7_Assessment_Rubrics.pdf` | Assessment rubrics for all four lessons with worked examples at each score level, the complete student survey instrument, and item-level response distributions. | Section 4.7, Table 9, Section 5.5 |
| `training_log.csv` | Per-epoch training and validation loss and accuracy for the reference model. | Table 3, Figure 3 |
| `test_predictions.csv` | True label, predicted label, and confidence for every test image. | Figures 4, 5, 6 |

Every file named in the article appears here under exactly the name used in the
article. Lessons 1 and 3 need only `class_metadata.csv`, `test_predictions.csv`, and
the image archive — no GPU and no model training.

---

## 2. Quick Start (No GPU, About Ten Minutes)

Lessons 1 and 3 are fully self-contained and need no model training.

1. Download `Compressed_dataset.zip`, `class_metadata.csv`, and
   `test_predictions.csv`.
2. Extract `Compressed_dataset.zip`. You should get one folder per dish class.
3. Open `S2_Lesson1_Data_Splitting.ipynb` in Google Colab or Jupyter and run all cells.
4. Open `S4_Lesson3_Confusion_Matrix.ipynb` and run all cells.

Neither notebook trains anything; both read the deposited output files.

---

## 3. Full Reproduction, Step by Step

These steps reproduce every result in the article. They match Appendix A of the
manuscript.

**Step 1 — Get the files.** Download the repository contents. No account is required.

**Step 2 — Set up the environment.** Open the notebooks in a hosted service such as
Google Colab, or locally in Jupyter. Choose a GPU runtime for Lessons 2 and 4 and a
CPU runtime otherwise. The first cell of each notebook installs the required packages
and prints the version of each.

**Step 3 — Extract the data.** Unzip `Compressed_dataset.zip` so that it produces one
folder per dish class. The first cell of every notebook locates the directory
automatically and prints the resolved path and the number of images found.

> **This count must equal 4,577.** If it does not, stop and check the extraction —
> every later result will differ.

**Step 4 — (Optional) Retrain from scratch.** Run `S1_Full_Training_Pipeline.ipynb`
end to end. On a free Colab T4 this takes roughly 90 minutes and regenerates
`training_log.csv`, `test_predictions.csv`, and `class_metadata.csv`.

> Accuracies reproduce to within a few tenths of a percentage point rather than
> exactly, because GPU floating-point arithmetic is not bit-reproducible across
> devices. **This step can be skipped** — the outputs are already deposited here, and
> every lesson notebook reads them directly.

**Step 5 — Reproduce the tables and figures.**

| To reproduce | Run |
|---|---|
| Table 3, Figure 3 | `S3_Lesson2_Bias_Variance.ipynb` |
| Figures 4 and 5 | `S4_Lesson3_Confusion_Matrix.ipynb` |
| Figure 6 | `S6_Per_Class_Metrics.ipynb` |
| Figure 1 | `S2_Lesson1_Data_Splitting.ipynb` |
| Figure 2 | `S5_Lesson4_Data_Augmentation.ipynb` |

**Step 6 — Verify the split.** `S2_Lesson1_Data_Splitting.ipynb` prints the class
proportions of the three splits side by side, together with the chi-square statistic
comparing them. This is the check described in Section 2.3 of the article.

---

## 4. Requirements

No paid software is needed at any point.

- Python 3.10 or later
- `pandas`, `matplotlib`, `scikit-learn`, `torch`, `torchvision`, `numpy`

All are pre-installed in the free tier of Google Colab. For local use, the first cell
of each notebook installs anything missing.

**Hardware.** Lessons 1 and 3 run on CPU. Lessons 2 and 4 need a CUDA-capable GPU;
the free Colab tier is sufficient. Local execution needs roughly 3 GB of free disk
space.

---

## 5. About the Dataset

- **4,577 images** across **100 Indian dish classes**
- Mean class size approximately 45.8 images; the smallest class holds 7 images and the
  largest 83, a ratio of nearly 12:1
- Split 70/15/15 into training, validation, and test sets, stratified by class with a
  fixed random seed
- Images resized to 224 × 224 pixels
- Classes span six culinary categories: sweets and desserts (30), main courses (20),
  street food and snacks (20), rice dishes and biryanis (10), breakfast and South
  Indian items (10), and soups, drinks, and other items (10)

**A note on the smallest classes.** Because a 15% test allocation leaves the smallest
classes with only one or two test images, per-class recall for those classes can take
only a few distinct values and should not be read as a precise estimate. Lesson Plan 3
turns this into a teaching point by asking students to record the number of test images
behind every per-class figure they quote.

---

## 6. Troubleshooting

| Symptom | Cause and fix |
|---|---|
| Image count is not 4,577 | The archive extracted into a nested folder, or a partial download. Re-extract and confirm the notebook's printed path points at the directory containing the 100 class folders. |
| `FileNotFoundError` on a CSV | The notebook is looking in the wrong directory. Set the path variable in the first cell to wherever you extracted the files. |
| A cell fails with a CUDA error | The runtime has no GPU attached. Lessons 1 and 3 do not need one; for Lessons 2 and 4, switch the runtime type to GPU. |
| Colab disconnects during training | The free-tier GPU quota is exhausted. Skip Step 4 — `training_log.csv` and `test_predictions.csv` are already deposited, and every lesson runs from them. |
| Accuracy differs slightly from Table 3 | Expected. GPU arithmetic is not bit-reproducible; differences of a few tenths of a percentage point are normal. |
| A notebook will not open | Confirm the file downloaded with its `.ipynb` extension intact. |

---

## 7. License and Reuse

The dataset and all teaching materials are released for open educational and research
use. Instructors are welcome to adapt the lesson plans, extend the dataset with
additional dishes or additional cuisines, and translate the materials. The
one-directory-per-class layout is designed to make extension straightforward.

If you use these materials, please cite the archived release:

> Shinde, S., Attarde, S., Dudhalkar, K., and Aloorkar, R. (2026), *Indian Food Image
> Dataset: A Culturally Contextualized Image Dataset for Statistical Learning
> Education* [Data set], Zenodo. https://doi.org/10.5281/zenodo.19543423

## 8. Contact

Questions, corrections, and contributions are welcome. Please open an issue on this
repository, or contact the corresponding author.
