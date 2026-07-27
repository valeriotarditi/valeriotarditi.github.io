---
title: "Photodiode-Based Luxmeter with Arduino and AVR Assembly"
excerpt: "Hardware design and low-level firmware development of a light intensity meter using a photodiode, transresistance amplifier, and three 7-segment displays, programmed in AVR Assembly."
collection: portfolio
---

## Overview

This project was developed as part of the **Progettazione di Dispositivi Biomedici Programmabili (PDBP)** lab course at Politecnico di Torino. The goal was to design and implement a complete luxmeter system — from analog signal conditioning to embedded firmware — capable of measuring light intensity in klux and displaying it on three 7-segment displays, with battery voltage monitoring.

## System Specifications

- **Measurement range:** 0 – 6.55 klux (design target: 9.99 klux; limited by op-amp offset)
- **Sampling period:** ~1000 ms for both light intensity and battery voltage
- **Display:** 3-digit 7-segment display (hundreds, tens, units in klux)
- **Battery alert:** LED indicator triggered when voltage drops below 4.2 V threshold

## Hardware Design

- **Light sensor:** SFH203 photodiode in transresistance (I-V converter) configuration
- **Amplifier:** TL081 op-amp (chosen due to availability; high offset ~1.52 V compensated via look-up table)
- **Feedback resistor:** 4084 Ω (3820 Ω + 264 Ω in series, measured)
- **ADC reference:** external 3.3 V (Vref) via stabilised power supply
- **Microcontroller:** Arduino UNO (ATmega328P), powered at 7 V via Vin
- **Clock:** internal 16 MHz divided by 16 → 1 MHz operating frequency

## Firmware (AVR Assembly)

- **Timer Counter 0:** interrupt-driven timing (overflow every ~20 ms, prescaler 1024)
- **ADC:** 8-bit conversions with left-justified result; dual-channel (battery on ADC0, photodiode on ADC1)
- **Look-up table:** 256-entry flash table mapping ADC values to klux digits (hundreds, tens, units); first 116 entries zeroed to compensate op-amp offset
- **Display driver:** multiplexed 7-segment control via BCD decoder (PD0–PD6), with latch enable (LE) strobing
- **Battery subroutine:** ADC threshold comparison (TSH_BAT = 217 → 4.2 V), flag-based LED control

## Calibration

End-point calibration performed using a portable reference luxmeter:
- Full-scale condition: ~9.8–9.99 klux (torch illumination)
- Measured output voltage: 2.80 V
- Real sensitivity: **S = 68 μA/klux**
- Maximum achievable range: **6.55 klux** (limited by TL081 offset consuming ~1.49 V of dynamic range)

## Tools & Technologies

AVR Assembly · Arduino UNO (ATmega328P) · Analog circuit design · EasyEDA (schematic) · Breadboard prototyping · Multimeter calibration

## Team

M.G. Traverso, S. Maffei, V. Tarditi

## Download

[📄 Download full report](/files/luxmeter-arduino-avr.pdf)
