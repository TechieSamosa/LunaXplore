### **Project Overview**:
**Title**: Enhancement of Permanently Shadowed Regions (PSR) of Lunar Craters Captured by OHRC of Chandrayaan-2  
**Goal**: Create a software solution to enhance low-light images of PSR areas on the Moon to produce higher Signal-to-Noise Ratio (SNR) images suitable for interpretation, geomorphological studies, and potential landing site selection.  
**Data Sources**:
   - **Primary**: OHRC (Orbiter High Resolution Camera) images
   - **Secondary**: DFSAR (Radar for topographical insights), IIRS (Spectral analysis), CLASS (Elemental abundance data), and SPICE (geometric positioning and timing data)

---

### **Phase 1: Data Acquisition and Preprocessing**

1. **Download and Preprocess OHRC Data**:
   - **Goal**: Load and clean raw OHRC images. Since these images are low-light and noisy, they will need significant preprocessing.
   - **Implementation**: Use Python with libraries like OpenCV, NumPy, and SciPy.
   - **Steps**:
     - **Load OHRC Images**: Load OHRC raw image files (binary format).
     - **Format Conversion**: Convert OHRC binary images to more manageable formats (e.g., PNG, TIFF).
     - **Normalization**: Normalize pixel values to enhance contrast in preparation for noise reduction.
   
   ```python
   import cv2
   import numpy as np

   def load_ohrc_image(filepath):
       # Assuming binary format - adjust based on actual file specifics
       with open(filepath, 'rb') as f:
           binary_data = np.fromfile(f, dtype=np.uint8)
           img = binary_data.reshape((height, width))  # Set correct height and width
       return img

   def preprocess_image(img):
       img = cv2.normalize(img, None, 0, 255, cv2.NORM_MINMAX)
       return img
   ```

2. **DFSAR and SPICE Data for Contextual Analysis**:
   - **SPICE**: Provides spacecraft geometry (e.g., time, orientation) to understand the spatial configuration of the images.
   - **DFSAR**: Adds terrain information, especially height and roughness, for better understanding crater structure.
   
   ```python
   import spiceypy as spice

   def load_spice_kernels(kernel_list):
       for kernel in kernel_list:
           spice.furnsh(kernel)

   def get_spacecraft_position(et_time):
       # Example for getting position data
       state, _ = spice.spkezr('CHANDRAYAAN-2', et_time, 'J2000', 'NONE', 'MOON')
       return state[:3]  # x, y, z
   ```

3. **Spectral Enhancement Using IIRS and CLASS**:
   - **Goal**: Use IIRS (infrared spectral data) and CLASS (elemental abundance) to improve image quality, specifically around PSR regions.
   - **Approach**: Extract spectral bands from IIRS, then use CLASS data to identify elemental compositions to apply context-based contrast adjustments.

---

### **Phase 2: Low-Light Image Enhancement**

1. **Noise Reduction and De-Noising Algorithms**:
   - **Goal**: Remove noise that obscures details in low-light regions.
   - **Algorithm**: Non-Local Means Denoising (OpenCV), and a deep-learning-based denoiser (e.g., DnCNN).
   - **Implementation**:
   
   ```python
   def denoise_image(img):
       # Non-local Means Denoising
       denoised_img = cv2.fastNlMeansDenoising(img, None, 30, 7, 21)
       return denoised_img
   ```

2. **Contrast Enhancement with Histogram Equalization**:
   - **Goal**: Enhance contrast in shadowed areas.
   - **Algorithm**: Contrast Limited Adaptive Histogram Equalization (CLAHE).
   
   ```python
   def enhance_contrast(img):
       clahe = cv2.createCLAHE(clipLimit=2.0, tileGridSize=(8, 8))
       enhanced_img = clahe.apply(img)
       return enhanced_img
   ```

3. **Deep Learning Model for Low-Light Enhancement**:
   - **Model**: Implement a deep learning-based low-light enhancement model (e.g., Zero-DCE or EnlightenGAN).
   - **Training**: Fine-tune a pre-trained model if available, or use transfer learning on a small dataset.
   - **Library**: TensorFlow or PyTorch for model training.

   ```python
   # Placeholder for model inference
   def enhance_low_light(img):
       # Pass the image through a pre-trained model
       enhanced_img = model.predict(img)  # Model should be preloaded
       return enhanced_img
   ```

---

### **Phase 3: Auxiliary Data Integration**

1. **Overlaying DFSAR and IIRS Data**:
   - Use DFSAR’s terrain maps to highlight elevation changes in PSR regions.
   - IIRS data for spectral analysis could overlay color-coded elemental data on the enhanced images.
   
   ```python
   import matplotlib.pyplot as plt

   def overlay_dfsar_terrain(image, terrain_data):
       plt.imshow(image, cmap='gray')
       plt.contour(terrain_data, colors='red')
       plt.show()
   ```

2. **Coordinate Alignment with SPICE**:
   - Use SPICE to align and geo-reference images.

---

### **Phase 4: Frontend Development**

1. **Frontend Interface**:
   - **Framework**: Flask for a web interface that allows users to upload, enhance, and view images.
   - **Features**: 
       - **Upload OHRC Images**: Allow users to upload OHRC images for enhancement.
       - **Enhancement Options**: Provide sliders for adjusting contrast, brightness, and noise levels.
       - **Overlay Features**: Enable toggling between DFSAR terrain overlays and CLASS-based elemental color maps.

2. **Web Interface Code (Flask)**:
   
   ```python
   from flask import Flask, request, render_template, send_file
   import cv2
   import numpy as np

   app = Flask(__name__)

   @app.route('/')
   def index():
       return render_template('index.html')

   @app.route('/upload', methods=['POST'])
   def upload_image():
       file = request.files['file']
       img = cv2.imdecode(np.frombuffer(file.read(), np.uint8), cv2.IMREAD_GRAYSCALE)
       enhanced_img = preprocess_image(img)
       # Save or display enhanced image
       return send_file(enhanced_img, mimetype='image/png')
   
   if __name__ == '__main__':
       app.run(debug=True)
   ```

3. **User Interface Enhancements**:
   - **Dashboard**: Display metadata such as location coordinates, timestamps, and enhancement options.
   - **Image Analysis Tools**: Pan, zoom, adjust brightness/contrast on the enhanced image for more detailed inspection.

---

### **Phase 5: Deployment and Testing**

1. **Testing**:
   - Use real data from PSR regions, tuning the model and algorithms to maximize clarity without amplifying noise.
   - Ensure all modules work together smoothly and validate against known landmarks or features.

2. **Deployment**:
   - Deploy the Flask app on an environment like AWS or Google Cloud.
   - Integrate a database to manage different datasets and user interactions.

3. **User Documentation and Training**:
   - Provide clear documentation for users on using the app and interpreting the enhanced PSR images.
   - Integrate tutorials for scientific interpretation.

---

### **Summary**

This project combines image processing techniques, deep learning, and data integration to enhance low-light images from lunar PSR regions. By leveraging multiple data types from Chandrayaan-2, including OHRC, DFSAR, SPICE, and IIRS, it enables a comprehensive tool for both scientific research and practical applications. This structured approach provides the foundation for creating enhanced lunar PSR imagery and developing a user-friendly interface. 
