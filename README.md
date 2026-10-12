# GW-Scaled-Subtraction-Analysis

An advanced extension of gravitational-wave (GW) signal processing, focusing on proper **amplitude scaling** and **phase alignment** to isolate overlapping binary black hole mergers.

## Objective
When multiple gravitational-wave signals overlap in a detector stream (e.g., a heavy $35 M_\odot + 30 M_\odot$ merger coinciding with a lighter $15 M_\odot + 12 M_\odot$ merger), direct subtraction fails due to amplitude disparities and epoch mismatches. 

This repository implements **least-squares amplitude scaling ($\alpha$)** and waveform alignment to successfully subtract Template A and reveal the underlying faint waveform of **Signal B** in the residual stream.

---

## Methodology & Code
1. **Waveform Generation:** Simulates two distinct binary black hole mergers using PyCBC (`IMRPhenomD` approximant).
2. **Shared Grid Alignment:** Places both signals on a synchronized time-series grid with a controlled $0.02\text{s}$ time shift.
3. **Least-Squares Scaling:** Computes the optimal amplitude scaling factor ($\alpha$) via inner products:
   $$\alpha = \frac{\sum(s(t) \cdot h_1(t))}{\sum(h_1(t) \cdot h_1(t))}$$
4. **Residual Extraction:** Subtracts the scaled template from the composite stream to expose the hidden secondary signal.

---

## How to Run
You can open and execute the analysis directly in Google Colab using the badge below:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/hafiashafqat/GW-Scaled-Subtraction-Analysis/blob/main/Scaled_Subtraction_Analysis.ipynb)

---
## Next Steps
Transitioning towards **Joint Bayesian Parameter Estimation** for full multi-source probabilistic parameter recovery.
