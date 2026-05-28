🧠 Diabetes Prediction using Autoencoders and Random Forest
(Now deployed using Docker & AWS EC2 🚀)
This project explores two machine learning pipelines for predicting diabetes using biomedical data:

Baseline Model – Random Forest Classifier (RFC) with GridSearchCV
Enhanced Model – Autoencoder-based dimensionality reduction + RFC
A production-ready FastAPI application has been deployed using Docker and AWS EC2.

📁 Dataset
The dataset includes anonymized biomedical measurements and a binary label indicating diabetes status.

Target
CLASS
N = Non-diabetic
P = Diabetic
Features
AGE
BMI
HbA1c
Cr, Urea, TG, HDL, LDL, Chol
Gender (F/M)
🔍 Project Workflow
1. Data Preprocessing
Cleaned inconsistent labels
Encoded categorical variables (Gender: F → 0, M → 1)
Standardized and validated all feature inputs
2. Exploratory Data Analysis
Correlation heatmap
Feature distribution and patterns
3. Modeling
Train-test split (80/20)
RFC with and without autoencoder
Hyperparameter tuning using GridSearchCV (5-fold CV)
4. Evaluation
Accuracy, Precision, Recall, F1-score
Confusion Matrix
Feature Importance
✅ Model 1: Random Forest Classifier (Baseline)
Uses raw preprocessed features
Tuned using GridSearchCV
Identified important predictors like:
HbA1c
BMI
AGE
Accuracy: ~97%

🚀 Model 2: Autoencoder + Random Forest
Built a PyTorch-based autoencoder
Compressed 11 input features into a 4-dimensional latent vector
Applied RFC to latent representation
Tuned with GridSearchCV
Achieved similar performance with improved representation learning
Accuracy: ~97%

📈 Results Comparison
Model	Accuracy	Notes
RFC Baseline	~97%	Works well on raw features
AE + RFC	~97%	Captures deeper nonlinear feature interactions
📊 Example Outputs
Correlation Heatmap
Confusion Matrix
Feature Importance Plot
Latent Representation Visualization
📁 Notebooks
1_RFC_Baseline.ipynb – RFC + GridSearchCV
2_Autoencoder_RFC.ipynb – Autoencoder + RFC + GridSearchCV
🛠️ Tech Stack
Python 3.10
PyTorch (Autoencoder)
Scikit-learn (RFC + GridSearchCV)
Matplotlib, Seaborn
Pandas, NumPy
Joblib
FastAPI
Docker
AWS EC2
🚀 Deployment (Docker + AWS EC2)
This project includes a fully deployed FastAPI application using Docker and AWS EC2.

🧱 Docker Containerization
The project contains a dockerfile that packages:

FastAPI backend
Autoencoder model (encoder_model.pth)
Random Forest model (AE_RFC.joblib)
Scaler (Scaler.joblib)
HTML Template files
Build Docker Image
docker build -t diabetes-app .
☁️ AWS EC2 Deployment
The application is hosted on:

Ubuntu 24.04 LTS EC2 Instance (t3.micro — Free Tier Eligible)
Docker installed on EC2
GitHub repository cloned into the instance
Application served using Uvicorn inside Docker
SSH into the server
ssh -i "your-key.pem" ubuntu@your-ec2-ip
Run the container on EC2
docker run -d -p 9000:8000 diabetes-app
🌐 Permanent Hosting using Elastic IP
An Elastic IP (EIP) ensures the public IP never changes, even after stopping or restarting the EC2 instance.

Example final deployment URL:
http://13.48.100.101:9000/
✔ Key Learnings from Deployment
Containerizing ML applications using Docker
Running Docker containers on AWS EC2
Configuring security groups for external access
Assigning Elastic IP for stable hosting
Serving ML models using FastAPI
Building reproducible, production-ready ML pipelines
📌 Summary
This project demonstrates:

Classical ML (Random Forest)
Deep learning (Autoencoders)
Hybrid modeling approaches
Hyperparameter tuning techniques
End-to-end deployment on cloud infrastructure
It showcases how to combine machine learning, representation learning, and DevOps (Docker + AWS) to build real-world production ML applications.

About
No description, website, or topics provided.
Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 0 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Contributors
1
@Indrakaran1411
Indrakaran1411
Languages
Jupyter Notebook
98.3%
 
Other
1.7%
Footer
