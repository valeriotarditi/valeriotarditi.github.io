---
title: "Heart Rate Recovery Analysis via Smartphone PPG Signal"
excerpt: "Smartphone-based photoplethysmography (PPG) pipeline to assess cardiac recovery differences between trained and untrained subjects after anaerobic exercise."
collection: portfolio
---

## Overview

This project was developed as part of the **Smart Measurements in Sports and Physical Activity** exam at Politecnico di Torino. The study investigated whether Heart Rate Recovery (HRR) measured via smartphone PPG could detect meaningful differences in cardiac autonomic response between trained and untrained subjects following a standardised anaerobic exercise protocol.

## Research Question

*Are there differences in cardiac recovery between trained and untrained subjects after anaerobic exercise at standardised intensity and recovery times?*

## Experimental Protocol

- **Exercise:** horizontal leg press (Matrix G3) at 65% of 1RM (73 kg standardised load), 15 repetitions
- **Subjects:** 4 healthy males (2 trained weightlifters, 2 occasional aerobic exercisers), age 23–25
- **PPG acquisition:** iPhone 13 Pro rear camera with flash (30 fps), fingertip contact, 2-minute recording immediately post-exercise
- **Perceived exertion:** monitored via Borg CR10 RPE scale

## Signal Processing Pipeline

- **Raw PPG extraction:** red channel selected based on RGB luminosity histogram analysis (Siddiqui method)
- **Pre-processing:** min-max normalisation, mean removal, bandpass filter (0.67–3.33 Hz / 40–200 bpm)
- **HR estimation:** frequency-domain approach via `fromPPgToHr` function
- **Artefact removal:** linear interpolation around outliers caused by motion artefacts
- **Smoothing:** Savitzky-Golay filter to isolate recovery trend
- **HRRPT detection:** fitting of a line between HR peak and last sample; point of maximum Euclidean distance identifies the fast-to-slow phase transition (Heart Rate Recovery Point of Transition)

## Extracted Parameters

- **HR Range [bpm]:** difference between peak HR and final HR
- **T_HR90 [s]:** time to reach and sustain HR below 90 bpm
- **HRRFP_norm:** normalised fast-phase recovery amplitude
- **HRRSP_norm:** normalised slow-phase recovery amplitude

## Key Results

| Subject | Group | T_HR90 (s) | HRRFP_norm | HRRSP_norm |
|---|---|---|---|---|
| 1 | Trained | 59 | 0.83 | 0.17 |
| 2 | Trained | 28 | 0.85 | 0.15 |
| 3 | Untrained | 107 | 0.66 | 0.34 |
| 4 | Untrained | 116.5 | 0.52 | 0.48 |

Trained subjects reached 90 bpm significantly faster (28–59 s vs 107–116 s), with over 80% of recovery occurring in the fast phase — consistent with faster parasympathetic reactivation. Untrained subjects showed a more gradual recovery distributed across both phases.

## Tools

MATLAB · PPG signal processing · Frequency-domain HR estimation · Savitzky-Golay filtering · Sports physiology

## Team

L. Infantino, S. Maffei, F. Ricciardelli, R.M. Signer, V. Tarditi, M.G. Traverso

## Download

[📄 Download full report](/files/heart-rate-recovery-ppg.pdf)
