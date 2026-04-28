# EEG Sleep Spindle Detection using Hilbert Transform & YASA Benchmark

![Python](https://img.shields.io/badge/Python-3.10-blue)
![MNE](https://img.shields.io/badge/MNE-EEG-orange)
![YASA](https://img.shields.io/badge/YASA-Sleep%20Analysis-green)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-red)
![Signal Processing](https://img.shields.io/badge/Domain-Signal%20Processing-purple)

---

## Project Overview

This project implements a **custom sleep spindle detection pipeline** using EEG recordings from the ANPHY-Sleep dataset and compares results against the automated **YASA spindle detection framework**.

Sleep spindles are short bursts of oscillatory activity occurring during NREM sleep and are associated with memory consolidation, learning, and neurological health.

---

## Objective

* Detect sleep spindles (11–16 Hz oscillations lasting 0.5–2 sec)
* Build a manual signal-processing pipeline
* Compare results with YASA automated detection
* Analyze spindle variability across subjects

---

## Dataset

Dataset: ANPHY Sleep Dataset
https://osf.io/r26fh/overview

Participants Used:

* P11
* P12
* P13
* P14
* P15

---

## Methodology

### 1. EEG Preprocessing

* Bandpass Filter: 0.5–30 Hz
* Noise removal
* Channel selection: Cz

### 2. Spindle Band Isolation

* Bandpass Filter: 11–16 Hz

### 3. Envelope Extraction

* Hilbert Transform
* Moving average smoothing

### 4. Spindle Detection

Threshold:

```python
threshold = mean + k * std
```

Duration constraints:

* Minimum: 0.5 sec
* Maximum: 2 sec

### 5. Benchmark Comparison

Compared against:

* YASA spindle detection framework

---

## Results Summary

| Participant | Manual Count | YASA Count |
| ----------- | ------------ | ---------- |
| P11         | 576          | 561        |
| P12         | 314          | 246        |
| P13         | 559          | 1090       |
| P14         | 579          | 826        |
| P15         | 390          | 176        |

---

# Visual Results

## Sleep Spindle Detection Overlay

This visualization compares manual detections vs YASA detections.

![Sleep Spindle Overlay](images/spindle_overlay.png)

---

## Power Spectral Density Plot

Shows frequency concentration within spindle frequency band.

![PSD Plot](images/psd_plot.png)

---

## Performance Comparison Table

Comparison of spindle counts, density, and duration.

![Performance Table](images/performance_table.png)

---

## Tech Stack

* Python
* MNE
* YASA
* NumPy
* SciPy
* Matplotlib
* Jupyter Notebook

---

## Project Structure

```bash
EEG_Sleep_Spindle_Detection/
│
├── EEG_Spindle_Detection.ipynb
├── README.md
├── .gitignore
└── images/
    ├── spindle_overlay.png
    ├── psd_plot.png
    └── performance_table.png
```

---

## Future Improvements

* Deep learning spindle detection
* Multi-channel EEG analysis
* Real-time deployment for sleep monitoring systems

---

## Author

**NagaPavan Musunuri**
AI/ML | Signal Processing | Brain Computer Interfaces
