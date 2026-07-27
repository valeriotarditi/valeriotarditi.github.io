---
title: "Muscle Synergies Analysis During Treadmill Walking and Running"
excerpt: "Extraction and statistical comparison of muscle synergies from surface EMG data during walking and running, using NNMF and Hungarian algorithm sorting across gender subgroups."
collection: portfolio
---

## Overview

This project was developed as part of the **Neuroengineering** exam at Politecnico di Torino. The study analysed muscle synergy patterns extracted from surface EMG recordings of 30 healthy adults during treadmill walking (1.4 m/s) and running (2.8 m/s), investigating differences related to locomotion type and sex.

## Objectives

- Extract muscle synergies from 13 ipsilateral lower limb muscles using Non-Negative Matrix Factorisation (NNMF)
- Determine the optimal number of synergies via Variance Accounted For (VAF ≥ 90%)
- Compare synergy patterns across locomotion types (walk vs. run) and sexes (male vs. female)
- Validate synergy sorting consistency using the Hungarian algorithm

## Methods

**Dataset:** 30 healthy adults (15 M / 15 F), sEMG from 13 muscles (ME, MA, FL, RF, VM, VL, ST, BF, TA, PL, GM, GL, SOL), 16-channel wireless system at 2 kHz

**Pre-processing pipeline:**
- BMI-based outlier detection and subject removal
- Gait cycle segmentation (central 30 cycles), resampled at 500 samples per cycle (stance + swing equally weighted)
- High-pass Butterworth filter (50 Hz) + low-pass filter (20 Hz) for envelope extraction
- Custom `emgpolish.m` function: threshold-based artefact detection and linear interpolation

**Synergy extraction:**
- NNMF applied per subject per subgroup (Men Walk, Men Run, Women Walk, Women Run)
- Optimal synergy count: mode of per-subject optimal values (VAF ≥ 90%, single-muscle VAF ≥ 75%)
- Synergy sorting: Hungarian algorithm (`munkres.m`) for optimal cross-subject matching

**Statistical analysis:** bilateral Student's t-test (α = 0.05) comparing synergy time profiles and muscle weights across subgroups

## Key Findings

- **4 synergies** identified as optimal across all subgroups, mapping to four biomechanical functions: weight acceptance (C1), propulsion (C2), early swing (C3), late swing (C4)
- **Locomotion type:** highly significant differences between walking and running across both sexes — especially in weight acceptance (C1), driven by increased impact absorption demands during running
- **Sex:** minimal statistically significant differences between male and female subgroups, suggesting universal neural synergy organisation independent of sex
- **Hungarian algorithm** outperformed cross-correlation sorting, particularly for running task synergy matching

## Tools

MATLAB · NNMF · Hungarian algorithm · EMG signal processing · Statistical analysis (t-test) · Biomechanics

## Team

M. Fioretti, S. Maffei, V. Tarditi, M.G. Traverso

## Download

[📄 Download full report](/files/muscle-synergies-locomotion.pdf)
