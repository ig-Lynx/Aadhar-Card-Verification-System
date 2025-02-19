# 🆔 Aadhar Card Verification System

## 📌 Overview
This project is a web-based application that verifies Aadhar cards by processing uploaded images. The system utilizes machine learning for text extraction and validation. The backend is powered by Flask, and it employs YOLO (You Only Look Once) for object detection, OpenCV for image processing, and Tesseract OCR for text recognition.

## 🌟 Features
- 📤 Upload an Aadhar card image in JPG/JPEG format
- 🔍 Extract and verify the Aadhar number using the Verhoeff algorithm
- ✅ Provide validation feedback to users
- 📜 Log the verification process for debugging and monitoring

## 🛠️ Technologies Used
### 1. 🏗️ Flask (Python Web Framework)
- Used to create the web application and handle HTTP requests.
- Routes include:
  - 🏠 `/` - Home page for file upload
  - 🆔 `/verify` - Processes and verifies the Aadhar card
- Provides error handling and logging mechanisms.

### 2. 🎯 YOLO (You Only Look Once) for Object Detection
- Utilizes the `ultralytics` library to load a YOLOv8 model trained on Aadhar card detection.
- Detects and extracts relevant text regions (Aadhar number, name, DOB, etc.).
- YOLO model is downloaded from Hugging Face Hub (`arnabdhar/YOLOv8-nano-aadhar-card`).
- **Pre-trained YOLOv8 Model**: The model is fine-tuned specifically for detecting Aadhar card features, making it highly effective for recognizing printed text and structured elements.
- The model processes images efficiently, ensuring accurate detection and extraction of the Aadhar number.

### 3. 🖼️ OpenCV (Computer Vision Library)
- Converts images to NumPy arrays for processing.
- Extracts Regions of Interest (ROI) from detected bounding boxes.

### 4. 🔠 Tesseract OCR (Optical Character Recognition)
- Extracts text from images to retrieve the Aadhar number.
- Configured with the local installation path (`C:\Program Files\Tesseract-OCR\tesseract.exe`).

### 5. 🔢 Verhoeff Algorithm (Checksum Validation)
- Ensures Aadhar numbers are valid using the Verhoeff algorithm.
- Implements a series of permutation and inverse operations to detect errors.

### 6. 📝 Logging (Monitoring and Debugging)
- Logs every step of the verification process.
- Helps track errors and debugging information.

## ⚙️ Installation & Setup
1. **📦 Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
2. **▶️ Run the Flask application**
   ```bash
   python app.py
   ```
3. **🌍 Access the application**
   - Open a web browser and navigate to `http://127.0.0.1:5000/`

## 📂 File Structure
```
├── app.py                 # Flask main application
├── Testing.py             # Aadhar card processing logic
├── templates/             # HTML templates (page2.html, success.html, failure.html, error.html)
├── uploads/               # Directory to store uploaded images
├── models/                # Directory to store YOLO model
├── static/                # CSS, JS, images
└── requirements.txt       # Required Python libraries
```

## 🚀 Usage
1. 📤 Upload an Aadhar card image.
2. 🔍 The system extracts the Aadhar number and validates it.
3. ✅ If valid, the success page is displayed with the extracted number.
4. ❌ If invalid, an error message is shown.

## 🔮 Future Enhancements
- 🖼️ Expand supported file types (PNG, PDF)
- 🎯 Improve accuracy using better OCR preprocessing
- 🎨 Integrate a frontend framework for enhanced UI

## 👨‍💻 Contributors
- **Your Name** (your.email@example.com)
- **Additional Contributors** (if any)

## 📜 License
This project is licensed under the MIT License.

