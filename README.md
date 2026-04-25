# EEG Sleep Spindle Detection

## Overview

This project implements a custom sleep spindle detection algorithm using EEG data and compares it with an automated benchmark (YASA).

## Objective

To detect sleep spindles (11–16 Hz oscillations lasting 0.5–2 seconds) and evaluate the performance of a manual detection method against an automated algorithm.

## Methodology

* Bandpass filtering (0.5–30 Hz) to remove noise
* Spindle band filtering (11–16 Hz)
* Hilbert transform to extract amplitude envelope
* Thresholding using mean + k × std
* Duration filtering (0.5–2 seconds)
* Comparison with YASA automated detection

## Results

* Performance evaluated using spindle count, density, and average duration
* Observed variability across participants
* YASA tends to detect slightly longer spindle durations

## Dataset

ANPHY-Sleep Dataset:
https://osf.io/r26fh/overview

## How to Run

1. Install dependencies:
   pip install mne yasa numpy scipy matplotlib

2. Open the notebook:
   EEG_Spindle_Detection.ipynb

## Note

Dataset is not included due to size and licensing constraints.

## Author

NagaPavan Musunuri
