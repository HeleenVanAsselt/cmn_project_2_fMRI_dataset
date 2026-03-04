# fMRI MVPA: VTC vs V1 Object Category Decoding

## Overview

This project investigates whether object category information is more strongly represented in ventral temporal cortex (VTC) than in early visual cortex (V1).

Using the Haxby fMRI dataset, we compare multi-class decoding accuracy between classifiers trained on:

- Ventral Temporal Cortex (VTC) voxels  
- Early Visual Cortex (V1) voxels  

---

## Research Question

Does a classifier trained on ventral temporal cortex voxels achieve higher object category decoding accuracy than a classifier trained on early visual cortex voxels?

---

## Hypothesis

A classifier trained on ventral temporal cortex voxels will achieve significantly higher multi-class object category decoding accuracy than a classifier trained on early visual cortex voxels.

---

## Methods

### Data
- Dataset: Haxby et al. (2001) fMRI dataset  
- 6 subjects  
- 8 object categories  
- Blocked experimental design  

### Regions of Interest
- **VTC mask** provided in the dataset  
- **V1 mask** approximated using the Harvard–Oxford cortical atlas (Occipital Pole region)

### Preprocessing
- Rest periods removed  
- Labels aligned with fMRI volumes  
- Region-specific masking applied  
- Standardization within classifier pipeline  

### Classification
- Linear Support Vector Machine (SVM)  
- 8-way multi-class classification  
- Leave-one-run-out cross-validation (within subject)  

### Evaluation
- Mean decoding accuracy computed per subject  
- Paired t-test comparing VTC vs V1 accuracy across subjects  

---

## Results

For each subject:
- Mean VTC decoding accuracy  
- Mean V1 decoding accuracy  

Group-level statistical comparison performed using a paired t-test.

---

## Reproducibility

The dataset is automatically downloaded via `nilearn` if not already present.

To reproduce results:

```bash
pip install -r requirements.txt