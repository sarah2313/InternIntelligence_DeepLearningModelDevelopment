# 🧠 Deep Learning Flask API  

A Flask API for making predictions using a deep learning model. The API takes an image (28x28 grayscale) as input and returns a predicted label.

---

## 🚀 Features  
- Loads a pre-trained deep learning model (`model.h5`).  
- Accepts image input as JSON and returns a prediction.  
- Simple Flask API for easy integration.  

---

## 📚 Project Structure  

```
DeepLearning-FlaskApp/
│── model/                 # Folder for trained model files
│   ├── model.h5           # Saved Keras/TensorFlow model
│── notebooks/             # Jupyter Notebooks
│   ├── DeepLearningModel.ipynb  # Main notebook
│── app/                   # Flask application
│   ├── app.py             # Flask API script
│── tests/                 # Testing scripts
│   ├── test_request.py    # Test script for API
│── requirements.txt       # Required Python packages
│── README.md              # Documentation
│── .gitignore             # Ignore unnecessary files
│── LICENSE                # (Optional) Open-source license
```

---

## 🛠 Installation  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/YOUR_USERNAME/DeepLearning-FlaskApp.git
cd DeepLearning-FlaskApp
```

### **2️⃣ Create a Virtual Environment (Recommended)**  
```bash
python -m venv venv
source venv/bin/activate  # For Mac/Linux
venv\Scripts\activate     # For Windows
```

### **3️⃣ Install Dependencies**  
```bash
pip install -r requirements.txt
```

---

## 🚀 Running the Flask API  

### **1️⃣ Start the Flask App**  
```bash
python app/app.py
```

### **2️⃣ Send a Prediction Request**  
You can send a request using `request.py` or manually with Python:

#### **request.py**
```python
import requests
import json
import numpy as np

url = "http://127.0.0.1:5000/predict"

# Generate a random 28x28 image
sample_image = np.random.rand(28, 28).tolist()

data = json.dumps({"image": sample_image})
response = requests.post(url, data=data, headers={"Content-Type": "application/json"})

print(response.json())
```

#### **Expected Response Example:**
```json
{"predicted_label": 7}
```

---

## ✅ Testing the API  
To run tests:  
```bash
pytest tests/test_request.py
```

---

## 📝 License  
This project is licensed under the **MIT License**.

