# 🌕 **LunaXplore** 🌑

<div align='center'>
  <img src="https://img.shields.io/badge/Project%20Status-Active-brightgreen" alt="Project Status">
  <img src="https://img.shields.io/badge/License-All%20Rights%20Reserved-red" alt="License">
  <img src="https://img.shields.io/badge/Python-3.11%2B-yellow" alt="Python Version">
  <img src="https://img.shields.io/badge/Contributions-Welcome-orange" alt="Contributions Welcome">
</div>

<div align='center'>
  <img src="https://img.shields.io/github/contributors/TechieSamosa/LunaXplore?style=for-the-badge&color=blue" alt="GitHub contributors">
  <img src="https://img.shields.io/github/issues-closed-raw/TechieSamosa/LunaXplore?style=for-the-badge&color=brightgreen" alt="GitHub Closed issues">
  <img src="https://img.shields.io/github/issues-pr/TechieSamosa/LunaXplore?style=for-the-badge&color=aqua" alt="GitHub PR Open">
  <img src="https://img.shields.io/github/issues-pr-closed-raw/TechieSamosa/LunaXplore?style=for-the-badge&color=blue" alt="GitHub PR closed">
  <img src="https://img.shields.io/github/languages/count/TechieSamosa/LunaXplore?style=for-the-badge&color=brightgreen" alt="GitHub language count">
  <img src="https://img.shields.io/github/last-commit/TechieSamosa/LunaXplore?style=for-the-badge&color=blue" alt="GitHub last commit">
  <img src="https://img.shields.io/badge/Maintained%3F-yes-brightgreen.svg?style=for-the-badge" alt="Maintained">
  <img src="https://img.shields.io/github/repo-size/TechieSamosa/LunaXplore?style=for-the-badge&color=aqua" alt="Repo Size">
</div>

---

## 🚀 **Project Overview**

**LunaXplore** is an innovative project aimed at enhancing low-light images from the **Permanently Shadowed Regions (PSR)** of lunar craters, captured by the **Orbiter High-Resolution Camera (OHRC)** onboard Chandrayaan-2. The PSR areas, located near the lunar poles, are perpetually shadowed, making it challenging to obtain high Signal-to-Noise Ratio (SNR) images suitable for exploration and scientific analysis.

## 🌟 **Proposed Solution**

**LunaXplore** combines advanced **Deep Learning** and **Image Processing** techniques to enhance PSR images. Using a custom workflow that includes **Contrast Enhancement**, **Denoising Algorithms**, and **Low-Light Generative Adversarial Networks (GANs)**, this project produces high-resolution PSR image maps of the lunar poles, crucial for:
- 🛬 **Landing Site Selection**: Identifying scientifically valuable and safe sites for future lunar missions.
- 🏞 **Geomorphological Studies**: Enabling detailed analysis of lunar surface features to support geological research.

## 🛠️ **Technical Approach**

### **Technologies Used**
- **Programming Languages**: Python (for deep learning and image processing), MATLAB (optional, for certain image processing tasks)
- **Frameworks/Libraries**: TensorFlow and Keras for GANs, OpenCV for image preprocessing, Retinex Theory-based custom algorithms for color balancing
- **Hardware Requirements**: High-performance computing (HPC) resources with GPU support are recommended for efficient model training and processing of large datasets

### **Methodology**

1. **Data Acquisition and Preprocessing**:
   - **Data Sources**: Primary data from OHRC images, with auxiliary data from DFSAR (terrain), IIRS (infrared spectra), CLASS (elemental abundances), and SPICE (geometric and timing data) to add spatial, spectral, and contextual information.
   - **Preprocessing**: Normalize, reduce noise, and align coordinates using SPICE data for accurate mapping of PSR regions. 

2. **Image Enhancement Pipeline**:
   - **Low-Light Image Denoising**: Use Non-Local Means and deep-learning-based DnCNN models to reduce noise while retaining essential features.
   - **Contrast Enhancement**: Apply Contrast Limited Adaptive Histogram Equalization (CLAHE) to enhance visibility in shadowed areas.
   - **Low-Light GAN Model**: A custom GAN is developed to enhance image quality by generating high-resolution, detail-enhanced images from low-light inputs.

3. **Retinex Theory Application**:
   - **Theory Integration**: Utilize Retinex-based processing to simulate human vision by balancing light and color, enhancing details in low-light regions.

4. **Auxiliary Data Integration**:
   - **DFSAR Overlay**: Integrate radar-based terrain details to enhance structural feature visibility within PSR regions.
   - **IIRS and CLASS Overlays**: Use spectral and elemental data overlays to highlight geological compositions for comprehensive analysis.

5. **Spherical Visualization of the Lunar Surface**:
   - **Map Creation**: Organize enhanced PSR images into a polar map format, providing a comprehensive lunar visualization with PSR areas highlighted.

6. **Output**: The final product is a detailed, high-resolution PSR image map, accessible via a user-friendly interface for mission planning, scientific research, and exploration.

## 💡 **Unique Features**

- **High-Resolution Lunar PSR Mapping**: Provides detailed, high-quality visualizations of PSR regions for scientific and mission-planning use.
- **Multi-Spectral and SAR Data Fusion**: Allows optional integration with Synthetic Aperture Radar (SAR) and infrared data for enhanced analysis of structural and compositional details.

## 🧠 **Feasibility and Viability**

### **Challenges**
- **Complexity of Low-Light Data**: Processing low-light lunar images with limited PSR data samples requires specialized training and enhancement techniques.
- **High Computational Requirements**: Large datasets and GAN model processing require significant computational resources.

### **Strategies**
- **Model Optimization and Regularization**: Use GAN regularization techniques to prevent overfitting and optimize training.
- **High-Performance Computing**: Leverage GPU support and HPC resources to streamline data processing and model training.

## 🌍 **Impact and Benefits**

**LunaXplore** aims to:
- **Advance Lunar Science**: Contribute valuable high-resolution data for lunar geological studies.
- **Support Future Missions**: Aid in the identification of optimal landing sites by producing clear images of previously obscured PSR regions.
- **Promote Technological Innovation in Space Imaging**: Pioneer advancements in AI and image processing tailored to space exploration.

## 📁 **Repository Structure**

- `/data`: Contains example datasets (low-light OHRC images) and auxiliary data from DFSAR, IIRS, and CLASS for demonstration purposes.
- `/models`: Stores pre-trained GAN models and configuration files for model inference.
- `/src`: Source code for preprocessing, enhancement algorithms, GAN training, and integration with auxiliary data.
- `/docs`: Documentation files, including setup instructions and references.
- `/examples`: Sample outputs and visualization files for demonstration.

*Note*: Certain datasets may require separate access permissions (e.g., DFSAR or IIRS data), available via ISSDC or relevant databases.

## 🔍 **Sample Results**

To provide users with a reference, sample PSR enhancement outputs are included in the `/examples` folder. These examples demonstrate the expected quality of the enhanced images after processing with the LunaXplore pipeline.

## 🎯 **Contribution Guidelines**

We welcome contributions from the community! To contribute:

1. **Fork the Repository**: Fork this repository to your GitHub account.
2. **Open an Issue**: Before starting any work, open an issue describing your proposed changes.
3. **Create a Pull Request**: Once ready, create a pull request (PR) from your forked repository to the main repository. Reference the related issue in your PR description.
4. **Follow Coding Standards**: Maintain consistent code styling and include comments for clarity.

Upon approval, contributions will be merged, and your name will be added to the list of contributors.

## 🏅 **Contributors**

<a href="https://github.com/TechieSamosa/LunaXplore/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=TechieSamosa/LunaXplore" />
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

All rights reserved. Redistribution, modification, or use of this code for any commercial, competitive, hackathon, personal, or academic project purposes

 is strictly prohibited without the express written permission of the authors. Unauthorized use, reproduction, or distribution of this code or any project components is forbidden to protect the project’s integrity and intended purpose.

---

Together, let’s unlock the mysteries of the Moon’s hidden regions! 🌙✨
