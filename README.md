
# mlproject
## End-to-End Machine Learning Project

## 🎓 Student Performance Prediction

![Build & Deploy](https://github.com/shivani7798/mlproject/actions/workflows/docker-deploy.yml/badge.svg)
[![Production](https://img.shields.io/badge/Production-Live-brightgreen)](https://studentperformance-latest.onrender.com)
![Python](https://img.shields.io/badge/python-3.11-blue)
![Docker](https://img.shields.io/badge/docker-enabled-blue)
![CI/CD](https://img.shields.io/badge/CI/CD-GitHub_Actions-green)

---

## 📌 Problem Statement

Predicting student performance is a key challenge in educational analytics.  
The objective of this project is to build a **machine learning regression model** that predicts a student’s **math score** based on demographic and academic features such as:

- Gender  
- Parental education level  
- Test preparation status  
- Reading and writing scores  

Accurate predictions can help:

- Identify students who may need additional support  
- Assist educators in data-driven decision making  
- Improve learning personalization strategies  

---

## 📊 Dataset

The dataset used in this project is publicly available on Kaggle:

🔗 **Dataset Link:**  
https://www.kaggle.com/datasets/rdeb26/stud-csv

### Dataset Description

| Feature | Description |
|-------|-------------|
| gender | Student gender (male/female) |
| race/ethnicity | Student ethnicity group |
| parental level of education | Highest parental education |
| lunch | Lunch type (standard / free or reduced) |
| test preparation course | Test preparation completion status |
| reading score | Reading score (0–100) |
| writing score | Writing score (0–100) |
| math score | **Target variable** |

The dataset contains student academic performance and demographic data and is used for supervised regression modeling.

---

## 🧠 Model Overview

### Machine Learning Pipeline

1. **Data Preprocessing**
   - Handling categorical variables
   - Feature scaling and encoding

2. **Model Training**
   - Regression model trained to predict math scores
   - Pipeline created for reproducible inference

### Model Artifacts

The trained components are saved as artifacts:

- `artifacts/preprocessor.pkl` – preprocessing pipeline  
- `artifacts/model.pkl` – trained regression model  

These artifacts are loaded by the Flask application during prediction.

---

## 💻 Running the Project Locally

### Prerequisites

- Python 3.11+
- Docker
- Git

### Clone the Repository

```bash
git clone https://github.com/<your-username>/mlproject.git
cd mlproject
````

### Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate    # macOS / Linux
venv\Scripts\activate       # Windows
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Ensure Model Artifacts Exist

```text
artifacts/model.pkl
artifacts/preprocessor.pkl
```

### Run the Flask Application

```bash
python app.py
```

Open your browser at:

```
http://localhost:5001
```

---

## 🐳 Docker Usage

### Build Docker Image

```bash
docker build -t studentperformance .
```

### Run Docker Container

```bash
docker run -p 5001:5001 studentperformance
```

Access the application at:

```
http://localhost:5001
```

---

## 🚀 Live Deployment

The application is deployed using **Docker + CI/CD + Render**.

🔗 **Live Application URL:**
👉 [https://studentperformance-latest.onrender.com](https://studentperformance-latest.onrender.com)

---

## 🔁 CI/CD Pipeline

This project uses **GitHub Actions** for continuous integration and deployment:

* Docker image is built on every push to `main`
* Manual approval required for production deployment
* Docker image pushed to Docker Hub
* Render deploy hook pulls the latest image automatically

---

## 🔄 Updating the Model

To update the ML model:

1. Retrain the model locally
2. Replace:

   * `artifacts/model.pkl`
   * `artifacts/preprocessor.pkl`
3. Commit and push changes
4. CI/CD rebuilds the Docker image
5. Render redeploys the updated application

No retraining occurs on the server.

---

## 🧰 Tech Stack

* Python 3.11
* Flask
* Scikit-learn
* Pandas, NumPy
* Docker
* GitHub Actions
* Render

---

## 🎯 Project Summary

This project demonstrates a **full end-to-end ML engineering workflow**:

* Real-world dataset usage
* Model training and persistence
* Inference API using Flask
* Containerized deployment with Docker
* CI/CD automation
* Cloud hosting on Render

---

## 📎 License

This project is intended for educational and learning purposes.

---

⭐ If you found this project useful, feel free to star the repository!

