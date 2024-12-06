# **Plan for Lunar PSR Image Enhancement and Interactive Deployment**

## **Project Overview**

### **Objective**
- Develop a robust software system to enhance low-light images from Permanently Shadowed Regions (PSRs) of lunar craters using Chandrayaan-2 datasets.
- Improve Signal-to-Noise Ratio (SNR) and resolution to create high-quality, annotated maps for:
  - Lunar landing site selection.
  - Geomorphological studies.
- Deploy an interactive platform that integrates a scrollable, spherical Moon visualization (like Google Earth) with layered overlays for enhanced usability.

---

## **Phase 1: Data Acquisition and Preprocessing**

### **1.1 Datasets**
This project leverages the following Chandrayaan-2 datasets:

1. **OHRC (Orbiter High-Resolution Camera)**:
   - **Purpose**: Primary dataset for lunar surface imagery.
   - **Data**: Calibrated and derived images in GeoTIFF format (L1 and L2).
   - **Key Use**: Source for low-light enhancement and resolution improvement.

2. **TMC2 (Terrain Mapping Camera-2)**:
   - **Purpose**: Provides Digital Elevation Models (DEM) and ortho-images.
   - **Data**: Calibrated (L1) and derived (L2) DEMs in GeoTIFF.
   - **Key Use**: Geometric corrections, terrain context, and validation.

3. **DFSAR (Dual-Frequency Synthetic Aperture Radar)**:
   - **Purpose**: Offers subsurface insights and water ice detection.
   - **Data**: Calibrated and derived radar data in GeoTIFF format.
   - **Key Use**: Validate surface features and subsurface anomalies.

4. **IIRS (Imaging Infrared Spectrometer)**:
   - **Purpose**: Provides hyperspectral data for surface composition analysis.
   - **Data**: Spectral cubes in binary format with XML metadata.
   - **Key Use**: Validate material composition and refine surface detection.

---

### **1.2 Workflow for Data Acquisition**

#### **1.2.1 Data Access**
1. **Download Data**:
   - Retrieve datasets from [ISRO’s ISSDC PRADAN portal](https://pradan.issdc.gov.in/).
   - Prioritize data specific to PSR regions.
2. **Data Format**:
   - OHRC, TMC2, DFSAR: GeoTIFF (calibrated and derived levels).
   - IIRS: Binary spectral cubes with accompanying metadata.

#### **1.2.2 Organization**
Standardize the directory structure:
```
/LunarEnhancement
├── raw_data
│   ├── ohrc
│   ├── tmc2
│   ├── dfsar
│   ├── iirs
├── preprocessed_data
├── models
├── outputs
├── overlays
└── documentation
```

---

### **1.3 Preprocessing Steps**

#### **1.3.1 OHRC (High-Resolution Images)**
- **Normalization**:
  - Scale pixel values between 0–1 for uniformity in model training.
- **Geometric Alignment**:
  - Use `gdalwarp` to align OHRC images with TMC2 DEM.
- **Noise Reduction**:
  - Apply median filtering or wavelet-based denoising to remove speckle noise.

#### **1.3.2 TMC2 (DEM and Ortho-images)**
- Extract and preprocess DEM using GDAL.
- Align ortho-images to OHRC data using mutual metadata.

#### **1.3.3 DFSAR (Radar Data)**
- Denoise subsurface radar data.
- Isolate radar signatures relevant to PSR regions.

#### **1.3.4 IIRS (Spectral Data)**
- Apply spectral filtering to remove low-confidence bands.
- Normalize spectral bands for material classification.

---

### **1.4 Integration of Preprocessed Data**
1. Align all datasets to a consistent CRS (e.g., Moon 2000/IAU CRS).
2. Resample to a uniform spatial resolution (e.g., 10m/pixel).
3. Merge datasets for analysis and visualization.

---

## **Phase 2: Model Development**

### **2.1 Goals**
- Enhance OHRC imagery with deep learning.
- Generate high-resolution outputs validated by auxiliary datasets.

---

### **2.2 Deep Learning Framework**

#### **2.2.1 DCGAN (Deep Convolutional GAN)**
- **Purpose**: Enhance low-light images by improving SNR.
- **Implementation**:
  - **Generator**: Uses convolutional layers to brighten low-light regions.
  - **Discriminator**: Validates the naturalness of generated enhancements.
  - **Training Data**: Illuminated OHRC images as ground truth.

#### **2.2.2 ESRGAN (Enhanced Super-Resolution GAN)**
- **Purpose**: Upscale enhanced images while retaining texture and edge details.
- **Enhancements**:
  - Incorporate TMC2 DEM to constrain elevation-induced distortions.

---

### **2.3 Training Details**
1. Use NVIDIA GPUs for training.
2. Augment training data with rotation, cropping, and simulated noise.
3. Implement perceptual loss for visual quality and pixel-based loss for fidelity.

---

## **Phase 3: Integration, Deployment, and Visualization**

### **3.1 Data Integration**
- Overlay DFSAR data on enhanced OHRC images to highlight subsurface structures.
- Use IIRS data for material validation by mapping spectral composition over enhanced regions.

---

### **3.2 Google Earth-Type Deployment**

#### **3.2.1 Features**
1. **Spherical Moon Interface**:
   - Scrollable, zoomable 3D model of the Moon.
   - Overlays stitched OHRC images for a complete lunar surface map.
2. **Layer Options**:
   - **Base Layer**: OHRC images (raw and enhanced).
   - **Altitude**: TMC2 DEM for elevation data.
   - **PSR Filter**: Highlight PSRs for easy identification.
   - **Enhanced Images**: Overlay enhanced OHRC images for detailed inspection.

#### **3.2.2 Implementation**
1. **Frameworks**:
   - CesiumJS for 3D visualization.
   - Three.js for custom enhancements.
2. **Backend**:
   - Flask/FastAPI to serve datasets dynamically.
3. **Data Storage**:
   - Use AWS S3 for hosting large GeoTIFFs.
4. **Frontend Deployment**:
   - Integrate CesiumJS with a React or plain HTML/CSS interface.

---

### **3.3 Workflow Automation**
- Use Airflow or Prefect to automate preprocessing, enhancement, and visualization pipelines.
- Enable real-time updates as new datasets become available.

---

### **3.4 Validation**
1. **Quantitative**:
   - Evaluate SNR improvement (>30%) and resolution enhancement (>25%).
2. **Qualitative**:
   - Compare results with known lunar features for accuracy.

---

## **Phase 4: Documentation and User Support**

### **4.1 Documentation**
1. **Technical Guide**:
   - Details preprocessing, model architectures, and deployment pipelines.
2. **User Guide**:
   - Instructions for navigating the Moon visualization interface.

### **4.2 Training and Outreach**
- Provide video tutorials for researchers.
- Conduct workshops for lunar mission planners.

---

## **Conclusion**
This refined plan integrates advanced image processing with a state-of-the-art visualization platform. The final deliverable not only enhances scientific understanding of lunar PSRs but also provides a practical tool for exploration planning. This scalable, interactive system lays the foundation for future lunar data analysis and dissemination.
