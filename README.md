# Blood-Cancer-Detection
# 🧬 Blood Cancer Detection and Segmentation System (VGG16 + U-Net)

This project is a complete deep learning and web-based solution for detecting and classifying blood cancer from blood smear images. It uses a hybrid *VGG16 + U-Net model* to both *classify the cancer stage* and *segment the affected areas* in the image. The system provides a *web interface built with Flask*, featuring user roles for doctors and admins, secure authentication, image upload, diagnosis reporting, and patient data management.

---

## ✅ Project Objectives

- To detect blood cancer and classify it as:
  - Benign
  - Malignant-Early
  - Malignant-Pre
  - Malignant-Pro
- To segment and mark the cancerous regions on the uploaded image.
- To enable doctors to diagnose patients and store their reports via a user-friendly interface.
- To manage and monitor access through a secure login system for doctors and admins.

---

## 📦 Technologies Used

| Component                | Tools/Technologies                                  |
|--------------------------|-----------------------------------------------------|
| Model Architecture       | VGG16 + U-Net (Keras, TensorFlow)                   |
| Image Preprocessing      | OpenCV, NumPy, PIL                                  |
| Web Framework            | Flask (Python)                                      |
| Frontend                 | HTML5, CSS3, JavaScript                             |
| Database                 | SQLite (can be switched to MySQL/PostgreSQL)        |
| Authentication           | Flask-Login, hashed passwords                       |
| PDF Report Generation    | ReportLab                                           |

---

## 🏗 System Architecture

User (Doctor/Admin)
↓
Flask Web Interface
↓
Image Upload → Preprocessing (OpenCV)
↓
Model Prediction (VGG16 + U-Net)
↓
Classification + Segmentation Output
↓
Diagnosis Display + Report Generation
↓
Patient Data Stored in Database


---

## 🧠 Deep Learning Model

### 🔹 Classification: VGG16
- A pre-trained VGG16 network is fine-tuned on a custom dataset of blood smear images.
- It outputs the cancer stage: Benign, Malignant (Early, Pre, Pro).
  
### 🔹 Segmentation: U-Net
- U-Net is used to perform semantic segmentation on the image.
- It marks the cancerous areas with bounding masks to assist in visualization.

---

## 🔐 Authentication Module

- Admins and Doctors can register and login securely.
- Only doctors are allowed to upload and analyze images.
- Admins can manage doctors (view/remove) and monitor system activity.

---

## 🧪 Workflow & Functionality

### 1. Doctor Login & Dashboard
- Securely logs in with email and password.
- Can upload new blood smear images for diagnosis.
- Can view previous patients and download reports.

### 2. Image Upload & Processing
- Image is validated (format, size) and uploaded.
- Preprocessing includes resizing, normalization, and noise reduction.

### 3. Model Prediction
- Processed image is passed to the VGG16 + U-Net model.
- Model returns:
  - Predicted class label with confidence score.
  - Segmented output marking affected regions.

### 4. Diagnosis Display & Report
- Results are shown on the dashboard with:
  - Cancer stage and probability.
  - Segmentation image.
- Doctors can save patient name, age, gender, and diagnosis to the database.
- A PDF report is auto-generated and can be downloaded.

### 5. Admin Dashboard
- View and manage all registered doctors.
- Monitor patient statistics and system usage logs.

---

## 🛠 Installation Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/cancer-detection-vgg16-unet.git
cd cancer-detection-vgg16-unet
