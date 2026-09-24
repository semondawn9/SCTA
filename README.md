<h1 align="center">
  Scene-Adaptive Continual Test-Time Adaptation for Open-Vocabulary Remote Sensing Segmentation
</h1>

<h2 align="center">
  🌟 ICASSP 2027 Submission 🌟
</h2>

<p align="center">
  <img src="assets/method_v13.png" width="80%" alt="Overview of the SCTA framework">
</p>

## Abstract

> Open-vocabulary remote sensing image semantic segmentation (OVRSIS) enables pixel-level recognition of text-defined categories with vision-language models, but existing methods are mostly evaluated under static test distributions or episodic adaptation protocols. In real deployments, sensor noise, imaging conditions, and environmental changes induce continual distribution shifts, where unsupervised online optimization can accumulate prediction drift and degrade performance. We propose **SCTA**, a Scene-Adaptive Continual Test-Time Adaptation framework for OVRSIS. It contains two complementary modules: **Scene-Adaptive Prompting (SAP)** builds category-level visual prototypes from frozen multi-description predictions and injects scene-relevant visual evidence into text representations, while **Semantic Drift Regulation (SDR)** constrains online predictions against a frozen reference model with symmetric KL divergence. The adaptation updates only text embedding offsets and fusion parameters, keeping the visual encoder frozen. On continual test streams constructed from seven remote sensing datasets, each with 15 corruption domains, **SCTA** achieves an average mIoU of **31.24%**, improving over the source model by **5.79 percentage points** and the strongest continual adaptation baseline, CoTTA, by **7.19 percentage points**. Ablation studies show that **SDR** stabilizes continual adaptation and **SAP** further improves segmentation quality. Code will be released at [https://github.com/semondawn9/SCTA](https://github.com/semondawn9/SCTA).

## Results

Continual test-time adaptation performance (mIoU, %). Best results are in **bold** and second-best results are <u>underlined</u>.

| Dataset | Source | SAR | TENT | CoTTA | MLMP | TMPA | DAF | SCTA |
|:---:|---:|---:|---:|---:|---:|---:|---:|---:|
| OpenEarthMap | <u>19.98</u> | 15.99 | 3.17 | 11.95 | 2.11 | 3.00 | 17.73 | **25.35** |
| DeepGlobe | 25.87 | 36.69 | 47.90 | <u>51.98</u> | 47.89 | 47.87 | 29.88 | **53.34** |
| LoveDA | 20.19 | 14.99 | 5.17 | 16.73 | 5.17 | 5.20 | **20.58** | <u>20.29</u> |
| UAVid | <u>27.55</u> | 22.00 | 4.76 | 21.26 | 3.61 | 3.31 | 22.04 | **29.58** |
| Vaihingen | <u>15.38</u> | 12.15 | 4.65 | 8.33 | 4.65 | 0.22 | 9.36 | **15.54** |
| UDD5 | <u>38.22</u> | 34.47 | 26.24 | 33.21 | 26.57 | 4.23 | 32.05 | **40.87** |
| VDD | <u>30.97</u> | 25.70 | 19.97 | 24.88 | 26.47 | 4.87 | 25.69 | **33.71** |
| **Average** | <u>25.45</u> | 23.14 | 15.98 | 24.05 | 16.64 | 9.81 | 22.48 | **31.24** |

## Qualitative Results

<p align="center">
  <img src="assets/qualitative_result_v3.png" width="80%" alt="Qualitative segmentation results of SCTA and comparison methods">
</p>
