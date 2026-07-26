---
title: "Gait Analysis in Post-Stroke Patients"
excerpt: "Kinematic and EMG analysis of gait cycle alterations in post-stroke patients, with automatic step segmentation algorithm."
collection: portfolio
---

## Overview

This project was developed as part of the **Bioingegneria della riabilitazione** exam. The study analysed the walking patterns of two post-stroke patients through kinematic and electromyographic data, identifying significant deviations from normative values.

## Objectives

- Quantify gait alterations in post-stroke patients using 3D marker data and EMG signals
- Develop an automatic gait segmentation algorithm (no force plates available)
- Identify pathological patterns such as drop-foot through combined kinematic and EMG analysis

## Methods

- **Motion capture:** 3D marker trajectories acquired via optoelectronic system following the PluginGait Vicon protocol (100 fps)
- **EMG:** bilateral acquisition of 6 lower limb muscles (RF, VL, ST, BF, TA, GAS) at 1000 Hz
- **Gait segmentation:** custom automatic algorithm based on heel and toe marker velocity profiles
- **Joint angles:** computed via Cardan ZYX rotation convention
- **EMG processing:** bandpass filtering (50–450 Hz), rectification, low-pass envelope extraction

## Key Findings

- Identified unilateral motor dysfunction in both patients
- Patient 1 showed clear drop-foot pattern: reduced ankle dorsiflexion, absent tibialis anterior activation during swing phase, shorter step length on the affected side
- Combined kinematic and EMG approach proved essential for reliable clinical interpretation

## Tools

MATLAB · Motion capture (Vicon) · EMG signal processing · Biomechanical modelling

## Team

S. Maffei, F. Piccatti, V. Tarditi, M.G. Traverso

## Download

[📄 Download full report](/files/Analisi-del-cammino-in-pazienti-post-ictus.pdf)
