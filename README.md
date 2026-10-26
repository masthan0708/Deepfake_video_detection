
# DeepFake Video Detection Using Machine Learning

A web-based DeepFake video detection application that uses a deep learning model to classify video content and provide a prediction with confidence.

## 📌 Project Overview

DeepFake videos are manipulated media generated using artificial intelligence and deep learning techniques. Detecting such content is an important challenge for maintaining the authenticity and reliability of digital media.

This project implements a web-based DeepFake detection system using Python, Flask, and PyTorch. The application processes video frames and uses a deep learning architecture combining ResNeXt-50 and LSTM to perform classification.

Users can interact with the system through a web interface, upload video content, and view the resulting prediction.

## 🎯 Key Features

- Web-based DeepFake video detection
- Video processing using OpenCV
- Face-related processing using `face_recognition`
- ResNeXt-50 based feature extraction
- LSTM-based temporal sequence processing
- Real/Fake classification
- Prediction confidence score
- Model-based visualization using heatmaps
- Flask-based web interface
- Multiple trained model configurations

## 🧠 System Workflow

```text
Input Video
     ↓
Video / Frame Processing
     ↓
Face Processing
     ↓
ResNeXt-50
     ↓
Feature Extraction
     ↓
Adaptive Average Pooling
     ↓
LSTM
     ↓
Dropout
     ↓
Fully Connected Layer
     ↓
Softmax
     ↓
Prediction + Confidence
     ↓
Result Display
````

## 🏗️ Model Architecture

The implemented model uses a pretrained ResNeXt-50 32×4d network as the spatial feature extraction backbone.

The extracted feature representations are processed as a sequence using an LSTM network. The final LSTM representation is passed through dropout and a fully connected layer to obtain the classification output.

The implemented architecture can be summarized as:

```text
Video Frames
     ↓
ResNeXt-50 32×4d
     ↓
Spatial Feature Maps
     ↓
Adaptive Average Pooling
     ↓
LSTM
     ↓
Dropout (0.4)
     ↓
Fully Connected Layer
     ↓
Softmax
     ↓
Classification
```

The model processes input frames at a spatial size of 112 × 112 pixels.

## 🛠️ Technologies Used

* Python
* PyTorch
* Torchvision
* Flask
* OpenCV
* NumPy
* Pandas
* Matplotlib
* face_recognition
* HTML
* JavaScript

## 📁 Project Structure

```text
Deepfake/
│
├── app.py
├── requirements.txt
├── .gitignore
│
├── models/
│   └── Trained PyTorch model files
│
├── static/
│   └── Static web resources
│
├── templates/
│   ├── first.html
│   ├── login.html
│   ├── chart.html
│   ├── index.html
│   ├── uploader.html
│   ├── uploader.js
│   ├── results.html
│   ├── result.html
│   └── LandingPage.html
│
└── website_screenshots/
    ├── deepLanding.png
    ├── upload.png
    └── result.png
```


## ⚙️ Installation

Clone the repository:

```bash
git clone <repository-url>
cd Deepfake
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate the virtual environment on macOS/Linux:

```bash
source venv/bin/activate
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## ▶️ Running the Application

Start the Flask application:

```bash
python app.py
```

Then open the local address provided by Flask in your web browser.

## 🤖 Trained Models

The project contains multiple trained PyTorch model configurations.

The trained model files are not included in this GitHub repository because each model is approximately 216 MB, which exceeds GitHub's standard individual file-size limit.

The application expects the trained model files to be placed inside:

```text
models/
```

The repository's `.gitignore` excludes the large `.pt` model files from normal Git tracking.

## 📊 Results

The project contains multiple trained model configurations with different video-frame settings.

The model filenames indicate different reported accuracy configurations, including models associated with 10, 20, 40, 60, and 100 video frames.

Detailed performance values should be interpreted together with the corresponding experimental setup and evaluation methodology.

## ⚠️ Limitations / Notes

* The trained model files are excluded from the repository because of their large size.
* The application requires the appropriate trained model files to be placed in the `models/` directory.
* Model performance depends on the training configuration and input video characteristics.
* The repository focuses on the implementation and web application; research papers, reports, and presentation materials are maintained separately.

## 👨‍💻 Author

**Masthanaiah Pillimetla**

````

### ⭐ One thing I deliberately changed

I **didn't write "97% accuracy" as the project accuracy**.

Your filenames contain things like:

```text
model_97_acc_60_frames_FF_data.pt
model_97_acc_100_frames_FF_data.pt
````

but a filename alone isn't enough evidence to claim that **97% is the final system accuracy**. It's better to be academically honest on GitHub.

Also, I included your actual architecture from `app.py`:

**ResNeXt-50 → Adaptive Average Pooling → LSTM → Dropout → Fully Connected → Softmax.**



