---
title: "Neuromuscular System Engineering – EMG Signal Analysis & Hand Gesture Classification"
excerpt: "Surface EMG acquisition, muscle fatigue analysis, crosstalk separation via PCA, and machine learning classification of hand gestures from forearm EMG signals."
collection: portfolio
---

## Overview

This project was developed as part of the **Ingegneria del Sistema Neuromuscolare** exam at Politecnico di Torino. It consisted of two experimental protocols covering the full pipeline of surface EMG signal processing: from raw acquisition and fatigue analysis to crosstalk separation and gesture classification for prosthetics and rehabilitation applications.

## Protocol 1 – Muscle Fatigue & Crosstalk Analysis

### Experimental Setup
Surface EMG signals were acquired from the biceps and triceps brachii of a healthy subject during isometric contractions at increasing loads (2, 4, 6, 8 kg) using an EMG16 system (2048 Hz), with 8-electrode arrays and 5 mm inter-electrode distance (IED).

### Methods
- **Pre-processing:** adaptive notch filters (50, 150, 250, 350 Hz), Butterworth bandpass filter (10–350 Hz), zero-phase implementation
- **Signal configurations:** monopolar, single differential (SD), double differential (DD)
- **Conduction velocity (CV) estimation:** spectral matching (two-channel) and maximum likelihood estimation (MLE, multichannel)
- **Fatigue analysis:** RMS, ARV, MNF, MDF computed on 250 ms epochs; fatigue plots generated for each load condition
- **Crosstalk simulation & separation:** mixed antagonist EMG signals analysed with PCA; reconstruction quality evaluated via MSE and R²

### Key Findings
- Spatial differentiation progressively shifts PSD toward higher frequencies, consistent with high-pass filtering behaviour
- Multichannel MLE provided more physiologically consistent CV estimates (3.58–4.34 m/s) than two-channel spectral matching
- PCA achieved good source separation (R² = 0.97–0.99), with slight improvement over the raw mixture

## Protocol 2 – Hand Gesture Classification

### Experimental Setup
EMG signals acquired from the forearm of a healthy subject using a Cometa system (2 kHz) during 20 hand opens and 20 hand closes, with 5 channels selected for classification.

### Methods
- **Pre-processing:** Chebyshev high-pass filter, EMG envelope extraction (rectification + Butterworth low-pass)
- **Classifiers:** SVM (linear kernel), LDA, Cosine Similarity prototype matcher
- **Feature extraction (FE):** MAV, RMS, SSC, WL computed on 250 ms windows
- **Evaluation:** accuracy and precision from confusion matrix (70/30 train-test split)

### Key Results

| Classifier | Accuracy (no FE) | Accuracy (with FE) |
|---|---|---|
| SVM envelope | 65.09% | 97.79% |
| LDA envelope | 80.55% | 93.22% |
| Cosine Similarity | 78.15% | — |

Feature extraction on raw signals dramatically improved classification, with SVM reaching **97.79% accuracy** — relevant for real-time prosthetic control.

## Tools

MATLAB · EMG signal processing · PCA · SVM · LDA · Feature extraction · Spectral analysis

## Team

G. Ciribilli, A. Debellis, I. Lionetti, V. Tarditi, L. Turchiarulo, M. Vitulano

## Download

[📄 Download full report](/files/neuromuscular-system-engineering.pdf)
