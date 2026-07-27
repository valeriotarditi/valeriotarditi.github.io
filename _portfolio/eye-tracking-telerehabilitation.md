---
title: "Reyebilitation – Eye-Tracking Telerehabilitation Platform for Children"
excerpt: "Webcam-based eye-tracking system integrated with a Unity serious game for remote assessment and rehabilitation of oculomotor dysfunction in paediatric patients."
collection: portfolio
---

## Overview

This project was developed as part of the **Soluzioni di Grafica 3D in applicazioni biometriche** exam at Politecnico di Torino. The goal was to design an accessible, non-invasive telerehabilitation platform — **Reyebilitation** — combining a webcam-based eye-tracking algorithm with a Unity serious game to monitor and stimulate visual attention in children with oculomotor disorders.

The system targets conditions such as attention and oculomotor control disorders, providing an engaging alternative to costly clinical tools through a standard webcam and a local web server.

## Key Features

- **Serious game ("Eye Catch You!"):** developed in Unity 6 with three progressive difficulty levels, marine-themed environment, and dynamic scoring — designed to maximise child engagement and minimise drop-out
- **Eye-tracking algorithm:** real-time gaze estimation via Google MediaPipe Face Mesh, with two-phase calibration (neutral zero-point + 9-point screen calibration) and linear regression mapping
- **Web platform:** local Python HTTP server with dual interface — clinician dashboard (patient management, session data, error logs) and child-facing game portal
- **Clinical outputs:** heatmaps, scanpaths, fixation metrics (duration, stability, spatial distribution), quadrant analysis, and automated textual reports for clinicians

## Methods

- **Gaze estimation:** iris landmark detection (MediaPipe), corrected gaze vector computation, multiple linear regression for screen coordinate mapping
- **Fixation detection:** I-DT (Dispersion Threshold Identification) algorithm
- **Database:** SQL backend with initialised paediatric patient profiles
- **Validation:** static accuracy and precision tests across four user–screen distances (30, 45, 60, 75 cm) on two healthy subjects

## Results

- Optimal operating distance: **60 cm** — accuracy >95%, angular error 2° ± 1°
- Precision consistently above **97%** across all tested distances
- System robustness confirmed across two independent users with consistent metrics

## Tools

Python · Unity 6 · MediaPipe · OpenCV · NumPy · scikit-learn · SQL · Bootstrap · HTML/CSS

## Team

S. Maffei, G. Martucci, V. Tarditi, M.G. Traverso, A. Villani

## Demo

🎬 [Watch the demo video](https://youtu.be/oh5nl8qD6tI) 

## Download

[📄 Download full report](/files/eye-tracking-telerehabilitation.pdf)
