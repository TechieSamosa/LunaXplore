# **Comprehensive Plan for Lunar PSR Image Enhancement**

## **Project Overview**

### **Objective**
- Enhance low-light images from Permanently Shadowed Regions (PSRs) of lunar craters using Chandrayaan-2 datasets.
- Improve Signal-to-Noise Ratio (SNR) and generate high-resolution image maps for:
  - Lunar landing site selection.
  - Geomorphological studies.
- Integrate multi-instrument data into a validated and deployable system.

---

## **Phase 1: Data Acquisition and Preprocessing**

### **1.1 Datasets**
This project utilizes the following Chandrayaan-2 datasets:

1. **OHRC (Orbiter High-Resolution Camera)**:
   - **Purpose**: Primary source of high-resolution lunar imagery.
   - **Data**: Calibrated and derived images in GeoTIFF format (L1 and L2).
   - **Key Use**: Base imagery for low-light enhancement and resolution improvement.

2. **TMC2 (Terrain Mapping Camera-2)**:
   - **Purpose**: Provides DEM and ortho-images.
   - **Data**: Calibrated (L1) and derived (L2) DEMs in GeoTIFF.
   - **Key Use**: Geometric corrections, terrain context, and validation.

3. **DFSAR (Dual-Frequency Synthetic Aperture Radar)**:
   - **Purpose**: Maps subsurface features and detects potential water ice deposits.
   - **Data**: Calibrated and derived radar data in GeoTIFF.
   - **Key Use**: Validate enhanced surface features and provide subsurface insights.

4. **IIRS (Imaging Infrared Spectrometer)**:
   - **Purpose**: Offers spectral data for material composition analysis.
   - **Data**: Hyperspectral image cubes in binary format with XML metadata.
   - **Key Use**: Validate surface composition and refine feature detection.

---

### **1.2 Workflow for Data Acquisition**

#### **1.2.1 Data Access**
1. **Download Data**:
   - Access datasets from [ISRO’s ISSDC PRADAN portal](https://pradan.issdc.gov.in/).
   - Submit requests for PSR-specific data.
2. **Data Format**:
   - OHRC, TMC2, DFSAR: GeoTIFF (calibrated and derived levels).
   - IIRS: Binary spectral cubes with metadata.

#### **1.2.2 Organization**
Organize datasets systematically for preprocessing and analysis:
```
/LunaXplore
├── raw_data
│   ├── ohrc
│   ├── tmc2
│   ├── dfsar
│   ├── iirs
├── preprocessed_data
├── models
├── outputs
└── documentation
```

---

### **1.3 Preprocessing Steps**
#### **1.3.1 OHRC (High-Resolution Images)**
- **Normalization**:
  - Normalize pixel intensities to account for varying illumination levels.
  - Scale pixel values between 0–1 for deep learning models.
- **Geometric Alignment**:
  - Align OHRC images with TMC2 DEM using `gdalwarp`.
- **Noise Reduction**:
  - Apply median filtering to reduce background noise.

#### **1.3.2 TMC2 (DEM and Ortho-images)**
- **DEM Extraction**:
  - Extract DEM layers from TMC2 datasets using GDAL.
- **Registration**:
  - Align TMC2 images to OHRC imagery using common control points or metadata.

#### **1.3.3 DFSAR (Radar Data)**
- **Denoising**:
  - Apply wavelet-based denoising for subsurface clarity.
- **Region Filtering**:
  - Isolate radar returns corresponding to PSRs based on metadata.

#### **1.3.4 IIRS (Spectral Data)**
- **Spectral Selection**:
  - Select high-confidence bands for materials of interest (e.g., OH groups for water ice).
- **Dark Correction**:
  - Subtract pre-imaging dark data for accurate spectral reflectance.

---

### **1.4 Integration of Preprocessed Data**
- Align all datasets to a consistent coordinate system, such as Moon 2000/IAU CRS.
- Resample datasets to the same resolution (e.g., 10m/pixel).
- Store preprocessed data in `/preprocessed_data`.

---

## **Phase 2: Model Development**

### **2.1 Goals**
- Enhance low-light OHRC imagery using advanced deep learning models.
- Generate high-resolution outputs.

---

### **2.2 Deep Learning Framework**

#### **2.2.1 DCGAN (Deep Convolutional GAN)**
- **Purpose**: Enhance low-light images by improving SNR.
- **Input**: Low-light OHRC images.
- **Output**: Brightened and denoised images.
- **Loss Functions**:
  - **Generator**: Perceptual loss.
  - **Discriminator**: Binary cross-entropy.

#### **2.2.2 ESRGAN (Enhanced Super-Resolution GAN)**
- **Purpose**: Upscale images to higher resolutions while retaining details.
- **Input**: Enhanced OHRC images.
- **Output**: High-resolution images.
- **Enhancements**:
  - Use TMC2 DEM to constrain elevation-based artifacts.

#### **2.2.3 Integration**
- **Fusion**:
  - Overlay enhanced OHRC images with TMC2 and DFSAR for validation.
- **Validation**:
  - Use IIRS data to ensure material consistency.

---

### **2.3 Training Details**
1. **Training Data**:
   - Train on illuminated OHRC images as ground truth.
2. **Augmentation**:
   - Apply rotation, cropping, and noise for robustness.
3. **Hardware**:
   - Use NVIDIA GPUs with CUDA support.

---

## **Phase 3: Integration, Deployment, and Validation**

### **3.1 Data Integration**
- Merge DFSAR data to highlight subsurface structures.
- Validate surface features using IIRS composition data.

---

### **3.2 Deployment**

#### **3.2.1 Pipeline Automation**
- Automate preprocessing, enhancement, and integration using Python scripts.
- Use Airflow for workflow orchestration.

#### **3.2.2 Hosting Options**
- **Cloud**: AWS (EC2 for processing, S3 for storage).
- **Local**: Dockerized container for portability.

---

### **3.3 Validation**
1. **SNR Metrics**:
   - Ensure 30% improvement in SNR.
2. **Resolution Metrics**:
   - Validate 25% resolution enhancement using independent datasets.

---

### **3.4 Documentation**
1. **Technical Report**:
   - Include preprocessing steps, model architectures, and validation metrics.
2. **User Guide**:
   - Provide instructions for dataset access and system usage.

---

## **Conclusion**
This revised plan corrects methodologies, aligns data processing steps, and ensures a deployable system for PSR image enhancement and analysis. Let me know if you'd like further refinements!
