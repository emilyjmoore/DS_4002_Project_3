# Breast Ultrasound Lesion Classification

This project builds a deep learning pipeline to segment and classify breast ultrasound images as benign, malignant, or normal. Using the Breast-Lesions-USG dataset, we evaluate whether combining **image features with clinical metadata** (e.g., age and BIRADS score) improves classification performance compared to image-only models.

## Repository Contents

This repository contains all code, data processing scripts, and documentation needed to reproduce the analysis and results. It includes:

- Data cleaning and preprocessing scripts  
- Deep learning model implementations (CNN + multimodal models)  
- Training and evaluation pipelines  
- Final results and supporting documentation  

## Section 1: Software and Platform

### Software Used
- Python 3.x  
- Jupyter Notebook / Python scripts  

### Required Packages
Install the following Python libraries before running the project:

```bash
pip install pandas numpy scikit-learn torch torchvision pillow matplotlib
```
### Platform Used
This project was developed and tested on:
- macOS

It should also run on:
- Windows
- Linux

## Section 2: Map of Documentation

```
DS_4002_Project_3/
│
├── README.md
├── LICENSE
├── DATA/
│   ├── cleaned_breast_lesions.csv
│   ├── Breast Lesions USG Images
│   └── Breast Lesions USG Masks
│
├── SCRIPTS/
│   ├── clean_csv_file.ipynb
│   ├── eda_figures_code.ipynb
│   ├── full_Unet_model.ipynb
│
└── OUTPUT/
    ├── q1_class_distribution.png
    ├── q2_image_mask_pairs.png
    ├── q3_lesion_area.png
    ├── q4_pixel_intensity.png
    ├── cleaned_breast_lesions.csv
```

## Section 3: Instructions to Reproduce Results

### Step 1: Clone the Repository

```bash
git clone https://github.com/emilyjmoore/DS_4002_Project_3.git
cd DS_4002_Project_3
```
### Step 2: Install Dependencies

```bash
pip install pandas numpy scikit-learn torch torchvision pillow matplotlib
```
### Step 3: Download and Prepare Data

1. Download the Breast-Lesions-USG dataset and Breast Lesions USG Images and Masks from the DATA folder
2. Place the files into the following structure:
```
data/
├── cleaned_breast_lesions.csv
├── images/
│   ├── case001.png
│   ├── case002.png
│   └── ...
├── masks/
│   ├── case001_tumor.png
│   ├── case002_tumor.png
│   └── ...
```
3. Ensure filenames in the CSV match the image and mask filenames exactly

### Step 4: Clean the Dataset

Run:
```bash
python scripts/clean_csv_file.ipynb
```
This will:
- Filter relevant columns
- Handle missing values
- Output: cleaned_breast_lesions.csv

### Step 5: Configure File Paths

Open the model script and update:
```python
CSV_PATH = "data/cleaned_breast_lesions.csv"
IMAGE_DIR = "data/images/"
MASK_DIR = "data/masks/"
```
### Step 6: Train and Evaluate Models

Run the model script:
```bash
python SCRIPTS/full_UNet_code.py
```
This will:
- Train the image-only model
- Train the image + metadata model
- Print training loss per epoch
- Output: Accuracy, Precision, and F1-score

### Step 7: Compare Results

You should observe:
- Image-only model performs moderately
- Image + metadata model improves performance

Example expected trend:
- Accuracy improves when metadata is included

## Summary

This project demonstrates that:
- Deep learning models can classify breast ultrasound images
- Adding clinical metadata improves predictive performance
- Multimodal approaches are more effective than image-only models

## Future Work

- Incorporate U-Net segmentation into classification
- Use advanced architectures (e.g., EfficientNet)
- Optimize hyperparameters to reach ≥88% accuracy
