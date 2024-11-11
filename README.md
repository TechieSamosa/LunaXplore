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

**LunaVision-PSR-ImageLab** is a pioneering project developed to enhance low-light images captured from the **Permanently Shadowed Regions (PSR)** of lunar craters by the **Orbiter High-Resolution Camera (OHRC)** onboard Chandrayaan-2. These lunar poles' regions are in constant shadow, receiving only minimal reflected light, making it challenging to obtain high Signal-to-Noise Ratio (SNR) images suitable for scientific analysis and exploration.

## 🌟 **Proposed Solution**

Our solution employs state-of-the-art **Generative Adversarial Networks (GANs)** in combination with **Retinex Theory** to significantly improve the visibility and clarity of PSR images under extreme low-light conditions. By harnessing the generative capabilities of GANs and Retinex Theory’s approach to simulate human vision through light and color balance, **LunaVision-PSR-ImageLab** strives to produce a high-resolution PSR image map of the lunar poles, which is crucial for:
- 🛬 **Landing Site Selection:** Identifying scientifically valuable and safe sites for future lunar missions.
- 🏞 **Geomorphological Studies:** Supporting lunar surface feature analysis to enhance understanding of lunar geology.

## 🛠️ **Technical Approach**

### **Technologies Used**
- **Programming Languages:** Python (for GAN and image processing), MATLAB
- **Frameworks/Libraries:** TensorFlow for GANs, OpenCV for image preprocessing, Retinex Theory-based custom algorithms
- **Hardware Requirements:** High-performance computing resources for efficient model training and large dataset processing

### **Methodology**

1. **Image Acquisition:** Obtain raw images of PSR regions captured by Chandrayaan-2's OHRC.
  
2. **Data Preprocessing:** Normalize and reduce noise from images to prepare high-quality input for the model.

3. **Image Enhancement with GANs:**
   - **GAN Setup:** A Deep Convolutional GAN (DCGAN) structure is tailored for enhancing lunar PSR imagery.
   - **Training Process:** Train the GAN using a curated set of 208 low-light images, iteratively refining the network to generate high-resolution, detail-enhanced images from low-light data.

4. **Retinex Theory Application:** Integrate Retinex Theory to further enhance perceptual quality, optimizing the balance of light and color for clearer image output.

5. **Post-Processing:** Utilize contrast adjustment, edge sharpening, and additional noise reduction techniques to produce final high-resolution images.

6. **Spherical Visualization of the Lunar Surface:** Organize enhanced images in a spherical format for a comprehensive "moon-view" visualization, highlighting PSR areas on the lunar poles.

7. **Output:** The final output is a detailed, high-resolution PSR image map intended for advanced scientific analysis and exploration.

## 💡 **Unique Features**

- **High-Resolution Lunar PSR Mapping:** Generates a clear image map of PSR regions to facilitate mission planning, scientific analysis, and geological studies.
- **Fusion with SAR Data (Optional):** Enables integration of Synthetic Aperture Radar (SAR) data to amplify structural details in PSR regions.

## 🧠 **Feasibility and Viability**

### **Challenges**
- **Training GANs on Limited PSR Data:** The unique nature of lunar PSR images requires specialized training techniques.
- **Balancing Computational Load:** Processing large datasets and running complex GAN models demand significant computational resources.

### **Strategies**
- **GAN Regularization and Optimization:** Employ techniques like regularization to prevent overfitting, while optimizing GAN parameters for efficient training.
- **High-Performance Computing:** Leverage HPC resources to streamline data processing and model training.

## 🌍 **Impact and Benefits**

**LunaVision-PSR-ImageLab** aims to:
- **Advance Lunar Science:** Support lunar geological studies by providing high-quality data from PSR regions.
- **Assist Future Missions:** Help identify optimal landing sites for future lunar missions by delivering detailed imaging of previously obscured regions.
- **Promote Innovation in Space Imaging:** Encourage the development of advanced AI and image processing technologies tailored to space exploration.

## 🎯 **Contribution Guidelines**

We welcome contributions from the community! Please follow the steps below:

1. **Fork the Repository:** Start by forking this repository to your GitHub account.
2. **Open an Issue:** Before working on any changes, open an issue in the main repository to describe your proposed modifications.
3. **Create a Pull Request:** Once your changes are ready, create a pull request (PR) from your forked repository to the main repository. Reference the related issue in your PR description.
4. **Adhere to Coding Standards:** Follow consistent code styling and include comments where necessary for clarity.

Upon approval, your contributions will be merged, and your name will be added to the list of contributors automatically.

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
