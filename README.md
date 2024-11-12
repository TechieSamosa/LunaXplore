# 🌕 **LunaVision-PSR-ImageLab** 🌑

<div align='center'>
  <img src="https://img.shields.io/badge/Project%20Status-Active-brightgreen" alt="Project Status">
  <img src="https://img.shields.io/badge/License-All%20Rights%20Reserved-red" alt="License">
  <img src="https://img.shields.io/badge/Python-3.11%2B-yellow" alt="Python Version">
  <img src="https://img.shields.io/badge/Contributions-Welcome-orange" alt="Contributions Welcome">
</div>

<div align='center'>
  <img src="https://img.shields.io/github/contributors/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=blue" alt="GitHub contributors">
  <img src="https://img.shields.io/github/issues-closed-raw/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=brightgreen" alt="GitHub Closed issues">
  <img src="https://img.shields.io/github/issues-pr/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=aqua" alt="GitHub PR Open">
  <img src="https://img.shields.io/github/issues-pr-closed-raw/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=blue" alt="GitHub PR closed">
  <img src="https://img.shields.io/github/languages/count/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=brightgreen" alt="GitHub language count">
  <img src="https://img.shields.io/github/last-commit/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=blue" alt="GitHub last commit">
  <img src="https://img.shields.io/badge/Maintained%3F-yes-brightgreen.svg?style=for-the-badge" alt="Maintained">
  <img src="https://img.shields.io/github/repo-size/TechieSamosa/LunaVision-PSR-ImageLab?style=for-the-badge&color=aqua" alt="Repo Size">
</div>


---

## 🚀 **Project Overview**

**LunaVision-PSR-ImageLab** is an innovative project designed to enhance low-light images captured in the **Permanently Shadowed Regions (PSR)** of lunar craters by the **Orbiter High-Resolution Camera (OHRC)** onboard Chandrayaan-2. These regions, located near the lunar poles, remain in perpetual darkness, posing challenges for obtaining high Signal-to-Noise Ratio (SNR) images for exploration and scientific analysis.

## 🌟 **Proposed Solution**

Our solution combines advanced **Deep Learning** and **Image Processing** techniques to enhance PSR images. Using a custom workflow of **Contrast Enhancement**, **Denoising Algorithms**, and **Low-Light Generative Adversarial Networks (GANs)**, **LunaVision-PSR-ImageLab** produces a high-resolution PSR image map of the lunar poles, crucial for:
- 🛬 **Landing Site Selection:** Identifying suitable sites for future lunar missions.
- 🏞 **Geomorphological Studies:** Supporting lunar surface feature analysis to understand the geological history.

## 🛠️ **Technical Approach**

### **Technologies Used**
- **Programming Languages:** Python (for deep learning, image processing), MATLAB (for optional image processing tasks)
- **Frameworks/Libraries:** TensorFlow and Keras for GANs, OpenCV for image preprocessing, Retinex Theory-based custom algorithms for color balancing
- **Hardware Requirements:** High-performance computing (HPC) resources for efficient model training and data processing

### **Methodology**

1. **Data Acquisition and Preprocessing**:
   - **Data Sources**: Utilize OHRC images as the primary dataset and leverage supporting data from DFSAR (terrain data), IIRS (infrared spectra), CLASS (elemental abundances), and SPICE (geometric and timing data) to add spatial, spectral, and contextual information.
   - **Preprocessing**: Apply normalization, noise reduction, and coordinate alignment using SPICE data for accurate mapping of PSR regions.

2. **Image Enhancement Pipeline**:
   - **Low-Light Image Denoising**: Utilize Non-Local Means and deep-learning-based DnCNN models to reduce noise without obscuring essential features.
   - **Contrast Enhancement**: Apply Contrast Limited Adaptive Histogram Equalization (CLAHE) to improve visibility of shadowed regions.
   - **Low-Light GAN Model**: Develop a custom GAN to further enhance image quality by generating high-resolution, detail-enhanced images from the low-light input.

3. **Retinex Theory Application**:
   - **Theory Integration**: Apply Retinex-based processing to simulate human vision perception, balancing light and color to bring out details in low-light areas.

4. **Auxiliary Data Integration**:
   - **DFSAR Overlay**: Add radar-based terrain details to enhance structural features in PSR regions.
   - **IIRS and CLASS Overlays**: Integrate spectral and elemental data for a more comprehensive analysis, highlighting geological compositions.

5. **Spherical Visualization of the Lunar Surface**:
   - **Map Creation**: Organize enhanced PSR images into a lunar polar map, with PSR areas prominently visualized.

6. **Output**: The final product is a detailed, high-resolution PSR image map, accessible via a user-friendly interface for mission planning, scientific research, and exploration.

## 💡 **Unique Features**

- **High-Resolution Lunar PSR Mapping**: Provides detailed, clear visualizations of PSR regions for scientific and mission-planning use.
- **Multi-Spectral and SAR Data Fusion**: Optional integration with Synthetic Aperture Radar (SAR) and infrared data for enhanced analysis of structural and compositional details.

## 🧠 **Feasibility and Viability**

### **Challenges**
- **Low-Light Data Complexity**: Processing low-light lunar images with limited PSR data samples requires specialized training techniques.
- **Computational Requirements**: High computational load for processing large datasets and training GANs on low-light imagery.

### **Strategies**
- **Model Optimization and Regularization**: Use techniques like GAN regularization to prevent overfitting and maintain efficient model training.
- **High-Performance Computing**: Utilize HPC resources to expedite data processing and model training.

## 🌍 **Impact and Benefits**

**LunaVision-PSR-ImageLab** aims to:
- **Advance Lunar Science**: Contribute valuable, high-resolution data for lunar geological studies and research.
- **Support Future Missions**: Aid in the identification of optimal landing sites for lunar exploration by producing clear images of shadowed regions.
- **Promote Technological Innovation in Space Imaging**: Lead advancements in AI and image processing for space exploration applications.

## 🎯 **Contribution Guidelines**

We welcome contributions from the community! Please follow these steps:

1. **Fork the Repository**: Fork this repository to your GitHub account.
2. **Open an Issue**: Before starting any work, open an issue to describe your proposed changes.
3. **Create a Pull Request**: Once your changes are ready, create a pull request from your forked repository to the main repository. Reference the related issue in your PR description.
4. **Adhere to Coding Standards**: Ensure consistent code styling and include comments for clarity.

After approval, your contributions will be merged, and your name will be added to the list of contributors automatically.

## 🏅 **Contributors**

<a href="https://github.com/TechieSamosa/LunaVision-PSR-ImageLab/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=TechieSamosa/LunaVision-PSR-ImageLab" />
</a>

## 📚 **Research and References**

- **"LLNet: A Deep Autoencoder Approach to Natural Low-light Image Enhancement"**
- **"Automated Lunar Crater Identification with Chandrayaan-2 TMC-2 Images using Deep Convolutional Neural Networks"**
- **"A Low-light Image Enhancement Model Based on Anisotropic Weighted Exponential Local Derivatives"**
- **"A Physics-based GAN for Single Image Defogging"**
- **"Low-light Image Enhancement Algorithm Based on Retinex and GAN"**
- **"Imaging and Analysis of Lunar Polar Regions: Challenges and Techniques"**
- **"Enhancement of Low-Light Satellite Images using Deep Convolutional Neural Networks"**

## 🔒 **License**

All rights reserved. Redistribution, modification, or use of this code for any commercial, competitive, hackathon, personal, or academic project purposes is strictly prohibited without the express written permission of the authors. Unauthorized use, reproduction, or distribution of this code or any project components is forbidden to protect the project’s integrity and intended purpose.

---

Together, let’s unlock the mysteries of the Moon’s hidden regions! 🌙✨
