---
title: "Fluorescence Microscopy Challenge – Cell Nucleus Segmentation"
excerpt: "Deep learning pipeline for automatic segmentation of cell nuclei in fluorescence microscopy images, using FCN and PSPNet architectures."
collection: portfolio
---

## Overview

This project was developed as part of the **Elaborazione di Immagini Mediche** exam at Politecnico di Torino. The goal was to design and evaluate a deep learning pipeline for automatic segmentation of cell nuclei in fluorescence microscopy images of cardiospheres — 3D aggregates of cardiac progenitor cells relevant to regenerative medicine.

## Objectives

- Develop an automated segmentation method to replace manual expert annotation
- Compare two CNN architectures (FCN and PSPNet) for nucleus segmentation
- Optimise pre- and post-processing pipelines to maximise segmentation accuracy

## Methods

- **Dataset:** 90 grayscale fluorescence images (1024×1024 px) with expert manual segmentation masks, split 80/10/10 for training, validation and test
- **Pre-processing:** median filter, CLAHE, Gaussian filter, min-max scaling
- **Architectures:** Fully Convolutional Network (FCN) and Pyramid Scene Parsing Network (PSPNet), implemented via MMSegmentation; patch-based inference (128×128 px)
- **Training:** multiple loss functions (CrossEntropy, Dice, Sigmoidal Focal), data augmentation, batch size tuning
- **Post-processing:** small object removal, hole filling, dilation, marker-controlled watershed transform, morphological opening, contour overlay

## Results

The FCN with CrossEntropy loss and data augmentation achieved the best performance:

- **Dice Similarity Coefficient (DSC):** 0.810 ± 0.035 on test set
- **Recall:** 0.833 ± 0.067
- **Nucleus count error:** 7 ± 6

## Tools

Python · MMSegmentation · OpenCV · Deep Learning (FCN, PSPNet) · Image processing

## Team

S. Maffei, F. Piccatti, V. Tarditi, M.G. Traverso

## Download

[📄 Download full report](/files/fluorescence-microscopy-challenge.pdf)
