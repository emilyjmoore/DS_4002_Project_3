# Breast Ultrasound Lesion Classification (DS 4002 Project 3)

This project builds a deep learning pipeline to **segment and classify breast ultrasound images** as *benign, malignant, or normal*. Using the Breast-Lesions-USG dataset, we evaluate whether combining **image features with clinical metadata** (e.g., age and BIRADS score) improves classification performance compared to image-only models.

---

## Repository Contents

This repository contains all code, data processing scripts, and documentation needed to reproduce the analysis and results. It includes:

- Data cleaning and preprocessing scripts  
- Deep learning model implementations (CNN + multimodal models)  
- Training and evaluation pipelines  
- Final results and supporting documentation  

---

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
