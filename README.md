
# 🧠 Diabetes Prediction using Autoencoders and Random Forest  
### *(Deployed using Docker & AWS EC2 🚀)*

This project explores two machine learning pipelines for predicting diabetes using biomedical data:

- **Baseline Model** – Random Forest Classifier (RFC) with GridSearchCV  
- **Enhanced Model** – Autoencoder-based dimensionality reduction + RFC  

A production-ready FastAPI application has been deployed using Docker and AWS EC2.

---

## 📁 Dataset

The dataset contains anonymized biomedical measurements and a binary diabetes classification label.

### 🎯 Target Variable

| Label | Meaning |
|-------|---------|
| N | Non-diabetic |
| P | Diabetic |

### 📊 Features

- AGE  
- BMI  
- HbA1c  
- Cr  
- Urea  
- TG  
- HDL  
- LDL  
- Chol  
- Gender (F/M)

---

## 🔍 Project Workflow

### 1️⃣ Data Preprocessing

- Cleaned inconsistent labels  
- Encoded categorical variables (`F → 0`, `M → 1`)  
- Standardized feature values  
- Validated all input data  

### 2️⃣ Exploratory Data Analysis

- Correlation heatmap  
- Feature distributions  
- Relationship analysis between variables  

### 3️⃣ Model Development

- Train-test split (80/20)  
- Random Forest training  
- Autoencoder-based feature extraction  
- Hyperparameter tuning using GridSearchCV (5-fold CV)

### 4️⃣ Evaluation Metrics

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  
- Feature Importance  

---

# ✅ Model 1: Random Forest Classifier (Baseline)

- Uses raw preprocessed features  
- Optimized using GridSearchCV  
- Important predictors identified:
  - HbA1c  
  - BMI  
  - AGE  

### 📈 Accuracy: ~97%

---

# 🚀 Model 2: Autoencoder + Random Forest

- Built using a PyTorch-based Autoencoder  
- Reduced 11 input features into a 4-dimensional latent representation  
- Random Forest applied on compressed features  
- Tuned using GridSearchCV  

### 📈 Accuracy: ~97%

---

## 📊 Results Comparison

| Model | Accuracy | Description |
|-------|-----------|-------------|
| RFC Baseline | ~97% | Strong performance on raw features |
| AE + RFC | ~97% | Learns deeper nonlinear feature representations |

---

## 📷 Example Outputs

- Correlation Heatmap  
- Confusion Matrix  
- Feature Importance Plot  
- Latent Space Visualization  

---

## 📁 Project Notebooks

| Notebook | Description |
|----------|-------------|
| `1_RFC_Baseline.ipynb` | Random Forest + GridSearchCV |
| `2_Autoencoder_RFC.ipynb` | Autoencoder + RFC + GridSearchCV |

---

## 🛠️ Tech Stack

- Python 3.10  
- PyTorch  
- Scikit-learn  
- FastAPI  
- Docker  
- AWS EC2  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Joblib  

---

# 🚀 Deployment using Docker & AWS EC2

The application is fully containerized and deployed on AWS EC2 using Docker.

---

## 🧱 Docker Containerization

The Docker image packages:

- FastAPI backend  
- Autoencoder model (`encoder_model.pth`)  
- Random Forest model (`AE_RFC.joblib`)  
- Standard scaler (`Scaler.joblib`)  
- HTML templates  

### 🔨 Build Docker Image

```bash
docker build -t diabetes-app .
```

---

## ☁️ AWS EC2 Deployment

Hosted on:

- Ubuntu 24.04 LTS EC2 Instance (`t3.micro`)  
- Docker installed on EC2  
- Uvicorn server running inside Docker  

### 🔐 Connect to EC2

```bash
ssh -i "your-key.pem" ubuntu@your-ec2-ip
```

### ▶️ Run the Container

```bash
docker run -d -p 9000:8000 diabetes-app
```

---

## 🌐 Elastic IP Hosting

Elastic IP ensures a stable public IP address even after restarting the EC2 instance.

### Example Deployment URL

```text
http://13.48.100.101:9000/
```

---

# ✔ Key Learnings

- Machine Learning model deployment  
- Docker containerization  
- AWS EC2 hosting  
- FastAPI backend development  
- Production-ready ML pipelines  
- Feature representation learning using Autoencoders  

---

# 📌 Project Summary

This project demonstrates:

- Classical Machine Learning using Random Forest  
- Deep Learning using Autoencoders  
- Hybrid AI modeling techniques  
- Hyperparameter optimization  
- Cloud deployment with Docker and AWS  

The project showcases how ML, Deep Learning, and DevOps can be integrated to build scalable real-world healthcare AI applications.

---

## 👨‍💻 Contributors

- [@Indrakaran1411](https://github.com/Indrakaran1411)

---

## ⭐ Repository Stats

- ⭐ Stars: 0  
- 👀 Watchers: 0  
- 🍴 Forks: 0  

---

## 📜 License

This project is open-source and available under the MIT License.
````
