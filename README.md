# 16-QAM Transceiver in 4G LTE

**Course:** CIE 437: Digital and Wireless Communication  
**Institution:** University of Science and Technology, Zewail City  
**Semester:** Fall 2025  
**Date:** December 28, 2025

## 📌 Project Overview
[cite_start]This project implements a complete 16-Quadrature Amplitude Modulation (16-QAM) transceiver chain to simulate and analyze data transmission in a 4G LTE context[cite: 1, 3]. [cite_start]The system is designed to transmit image data and analyze performance under various channel conditions, including AWGN, Rician (Line-of-Sight), and Rayleigh (Non-Line-of-Sight) fading[cite: 7, 36].

[cite_start]The implementation includes a software simulation in **MATLAB** and **LabVIEW**, alongside a hardware validation attempt using **NI USRP** (Universal Software Radio Peripheral) devices[cite: 6].


## 👥 Team Members
* [cite_start]**Mohammed Ali Sadek** (202200594) [cite: 1]
* [cite_start]**Ahmed Abdullah** (202202017) [cite: 1]
* [cite_start]**Abdelhady Mohamed** (202201172) [cite: 1]

[cite_start]**Instructor:** Dr. Ahmed Eltarass [cite: 1]

## 🎯 Objectives
* [cite_start]**Analyze 16-QAM:** Study the impact of modulation on Bit Error Rate (BER) and signal integrity isolated from the full OFDM stack[cite: 7].
* **Channel Simulation:** Evaluate performance across different environments:
    * [cite_start]**AWGN:** Baseline ideal noise[cite: 25].
    * [cite_start]**Rician Fading ($K=8$):** Simulating direct line-of-sight paths[cite: 20].
    * [cite_start]**Rayleigh Fading:** Simulating urban non-line-of-sight multipath environments[cite: 26].
* [cite_start]**Hardware Implementation:** Interface with NI USRP hardware to transmit and receive real signals[cite: 6].

## ⚙️ System Architecture

### 1. MATLAB Implementation
[cite_start]The MATLAB script models the full transmission chain using a granular, script-based approach[cite: 18, 19]:
* [cite_start]**Source:** Image serialization and dynamic bit-padding to align with 4-bit symbols[cite: 23].
* [cite_start]**Transmitter:** Mapping binary streams to complex 16-QAM constellation points[cite: 24].
* [cite_start]**Channel Modeling:** Application of AWGN, Rician, and Rayleigh fading with adjustable SNR (0–30 dB)[cite: 20, 27].
* [cite_start]**Receiver:** Zero-Forcing Equalizer to reverse channel path gains, demodulation, and image reconstruction[cite: 35, 29].

### 2. LabVIEW & USRP Implementation
[cite_start]The LabVIEW VI serves as both a pure simulation and a hardware interface[cite: 6, 62]:
* [cite_start]**Tx/Rx Design:** Handles framing, QAM modulation/demodulation, and pulse shaping[cite: 64, 68].
* [cite_start]**Hardware Challenges:** The USRP implementation highlighted real-world challenges such as synchronization mismatches (carrier rotation) and electromagnetic interference, which were contrasted with ideal software simulations[cite: 69, 71].


## 📊 Key Results
* [cite_start]**BER Performance:** The system demonstrated that Rician fading tracks AWGN closely due to the LOS component, while Rayleigh fading exhibits a much flatter error curve, representing the worst-case scenario[cite: 39, 40, 41].
* **Image Reconstruction:**
    * **10 dB:** "Ghost" figures visible in AWGN/Rician; [cite_start]Rayleigh suffers heavy "salt and pepper" noise[cite: 47, 59].
    * [cite_start]**30 dB:** Pristine image recovery across all channels[cite: 52, 60].
* [cite_start]**Constellation Analysis:** LabVIEW simulations confirmed distinct clustering at SNRs > 18 dB, validating the logic despite hardware noise limitations[cite: 80, 81].

  
## 📚 References
* [cite_start]J. G. Proakis and M. Salehi, *Digital Communications*, 5th ed., McGraw-Hill, 2008[cite: 85].
* [cite_start]MathWorks, *Communications Toolbox Documentation*[cite: 85].
