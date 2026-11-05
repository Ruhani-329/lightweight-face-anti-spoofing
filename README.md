# Lightweight Face Anti-Spoofing Using Frequency-Domain Analysis

**Research prototype | Computer Vision · Image Processing · Machine Learning**

## Overview
Face authentication systems can be vulnerable to presentation attacks such as printed photographs and screen replays. This project explores a lightweight face anti-spoofing pipeline using frequency-domain features and conventional machine-learning models.

The repository documents image preprocessing, Fast Fourier Transform (FFT) and Discrete Cosine Transform (DCT) feature extraction, and pilot model evaluation on two public benchmark datasets.

> **Research status:** Pilot experiments completed. The reported runs are exploratory, not final or independently validated benchmark results.

## Datasets
- **LCC-FASD:** Training, development, and evaluation splits. A face detector is used for cropping before resizing and normalization.
- **CASIA-FASD:** Provided train/test splits of pre-extracted, face-focused frames; preprocessing uses grayscale conversion and normalization.

Datasets are **not included** in this repository. Obtain them from their respective authorized sources and respect licensing and usage terms.

## Methodology
1. Inspect dataset structure and label distributions.
2. Validate image readability and preprocessing results.
3. Detect and crop faces where appropriate (LCC-FASD).
4. Convert images to standardized grayscale, normalized arrays.
5. Extract interpretable FFT features using windowed spectra and radial power bands.
6. Extract DCT-based frequency features.
7. Compare selected conventional classifiers, including SVM, Random Forest, and MLP.
8. Evaluate within-dataset and cross-dataset pilot runs using classification and anti-spoofing metrics.

## Tools
Python, NumPy, Pandas, OpenCV, Matplotlib, scikit-learn, and Jupyter/Kaggle Notebooks.

## Pilot experiment details
- Reproducible random seed: `42`.
- Includes preprocessing integrity checks, failure tracking, experiment exports, and a protocol audit.
- The shared research run reports **12 within-dataset** and **12 cross-dataset** experiment configurations.
- The final export explicitly labels the results **PILOT**, so no final accuracy or generalization claim is made here.

## How to run
1. Install the dependencies in `requirements.txt`.
2. Obtain LCC-FASD and CASIA-FASD and update the dataset paths in the notebook for your environment.
3. Open `notebooks/face_anti_spoofing.ipynb` in Kaggle or Jupyter.
4. Run the cells in order. Some stages download an OpenCV face-detector model and require network access.
5. Review the exported experiment outputs and failure/protocol logs.

**Note:** The notebook currently uses Kaggle-specific paths and is not a turnkey local CLI application.

## Limitations and next steps
- Verify CASIA subject/video grouping against original protocol metadata.
- Complete a subject-level leakage audit for LCC-FASD.
- Validate full-dataset performance before making benchmark claims.
- Review frame-level versus video-level APCER/BPCER calculations.
- Assess preprocessing-inclusive latency and statistical variability.

## Repository contents
- `notebooks/face_anti_spoofing.ipynb` — source notebook with methodology and experiments.
- `results/` — selected generated charts and non-sensitive pilot summaries, if included.
- `requirements.txt` — dependencies.

## Project scope
This is a research-oriented student project. It does **not** represent a production-ready face authentication or security system.
