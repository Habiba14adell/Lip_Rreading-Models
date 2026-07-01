# Lip Reading Models

Graduation project - June 2023

This repository contains lip-reading experiments for classifying spoken words or phrases from mouth-region image sequences. The project includes the preprocessing notebook, model-training notebooks, and the image dataset used in the experiments.

## Project Overview

Lip reading is the task of recognizing speech from visual mouth movement. This project explores deep learning and machine learning approaches using RGB and depth frames extracted from speakers saying predefined words and phrases.

The repository includes:

- Data preprocessing and mouth-region extraction with OpenCV and dlib.
- A CNN + LSTM model for sequence-based visual speech recognition.
- A CNN feature extraction + XGBoost classification workflow.
- A local dataset containing original, cropped, resized, and final train/validation image folders.

## Repository Structure

```text
.
├── CNNplusLSTM.ipynb
├── CNN_plus_XGBOOST.ipynb
├── Data Pre-Processing.ipynb
├── DATASET/
│   ├── F01, F02, ...
│   ├── M01, M02, ...
│   ├── colored cropped/
│   ├── Resized/
│   └── Final/
└── README.md
```

## Notebooks

| Notebook | Description |
| --- | --- |
| `Data Pre-Processing.ipynb` | Detects faces and facial landmarks, crops the mouth region, prepares/resizes image data, and organizes the dataset. |
| `CNNplusLSTM.ipynb` | Builds and trains a CNN + LSTM model to learn spatial and temporal features from lip movement frames. |
| `CNN_plus_XGBOOST.ipynb` | Uses CNN-based feature extraction with an XGBoost classifier for lip-reading classification. |

## Dataset

The dataset is stored in `DATASET/` and contains speaker folders, word/phrase folders, RGB images, depth images, cropped images, resized images, and final train/validation splits.

Local dataset summary:

- Files: about 103,610
- Size: about 7.23 GB
- Image formats: `.jpg` and `.png`

## Requirements

The notebooks use Python with the following main libraries:

- TensorFlow / Keras
- OpenCV
- dlib
- imutils
- NumPy
- pandas
- matplotlib
- scikit-learn
- XGBoost

Install the dependencies with:

```bash
pip install tensorflow keras opencv-python dlib imutils numpy pandas matplotlib scikit-learn xgboost
```

The preprocessing notebook expects the dlib landmark model file:

```text
shape_predictor_68_face_landmarks.dat
```

Download it from the official dlib model source if it is not already available locally, then place it in the project directory or update the path inside the notebook.

## How to Run

1. Open the project in Jupyter Notebook or JupyterLab.
2. Run `Data Pre-Processing.ipynb` to prepare cropped/resized mouth images.
3. Run `CNNplusLSTM.ipynb` to train the CNN + LSTM model.
4. Run `CNN_plus_XGBOOST.ipynb` to train and evaluate the CNN + XGBoost approach.

## Notes

- The dataset is large, so cloning and pushing may take time.
- If GitHub rejects the dataset because of repository size limits, move the dataset to Git LFS, Google Drive, Kaggle, or another dataset host and keep only the download link in this repository.
- Notebook outputs are included as part of the original project history.

## Author

Habiba Adel
