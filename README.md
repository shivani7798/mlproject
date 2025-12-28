# mlproject
## End to End ML project
Student Performance Prediction — Dataset & Project Overview
📌 1️⃣ Problem Statement

Predicting student performance is a common educational analytics problem. The goal of this project is to build a machine learning model that can accurately predict a student's math score based on demographic and academic features like reading and writing scores, parental education level, and preparation status.

Correctly predicting student performance can help:

Identify students who may need extra support

Provide insights for educators and administrators

Personalize learning pathways

This is a regression problem where the target variable (math score) is predicted using features that reflect a student’s background and prior academic performance.

📊 2️⃣ Dataset

The dataset used in this project is from Kaggle:

🔗 https://www.kaggle.com/datasets/rdeb26/stud-csv

Summary of the dataset
Column	Description
gender	Student gender (male/female)
race/ethnicity	Ethnic group
parental level of education	Highest education level of parents
lunch	Type of lunch (standard / free or reduced)
test preparation course	Whether completed test prep
reading score	Score in reading (0–100)
writing score	Score in writing (0–100)
math score	Target variable: the score to predict

This dataset consists of students’ scores and related demographic information, and it serves as the foundation for building a predictive model.

🧠 3️⃣ Model
Model Pipeline

Data preprocessing

Handle categorical variables

Apply scaling/encoding for model-ready input

Training

Fit a regression model to predict math scores

Store both the preprocessor and trained model

Artifacts

preprocessor.pkl – handles transformations for new data

model.pkl – trained regression model

These artifacts are saved and then loaded inside the Flask app for prediction.

💻 4️⃣ How to Run Locally
Prerequisites

Python 3.11+

Docker

Git

Clone the repository
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

Create a virtual environment
python3 -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

Install dependencies
pip install -r requirements.txt

Prepare artifacts

Ensure you have:

artifacts/model.pkl
artifacts/preprocessor.pkl

Run Flask app locally
python app.py


Open in browser:

http://localhost:5001

🐳 5️⃣ Docker Instructions
Build the Docker image
docker build -t studentperformance .

Run locally with Docker
docker run -p 5001:5001 studentperformance


The app will be available at:

http://localhost:5001

🚀 6️⃣ Live Demo
🔗 Production URL

Access your live deployed app here:

👉 https://studentperformance-latest.onrender.com

This link shows the Flask web app powered by the ML model and hosted on Render using your CI/CD pipeline.

🛠 7️⃣ Additional Notes
CI/CD

GitHub Actions builds Docker image on push

Manual approval step for production deployment

Deploy hook triggers Render to pull updated image

Model Updates

To update your model:

Retrain locally

Update artifacts/model.pkl and/or preprocessor.pkl

Commit & push

Workflow rebuilds image

Render redeploys updated service

🎯 Summary

This project illustrates a complete ML engineering workflow:

Data exploration with a real-world dataset

Model training and artifact management

REST API using Flask

Containerization using Docker

Continuous deployment with GitHub Actions and Render
![Build & Deploy](https://github.com/shivani7798/mlproject/actions/workflows/docker-deploy.yml/badge.svg)


[![Production](https://img.shields.io/badge/Production-Live-brightgreen)](https://studentperformance-latest.onrender.com)

![Python](https://img.shields.io/badge/python-3.11-blue)
![Docker](https://img.shields.io/badge/docker-enabled-blue)
![CI/CD](https://img.shields.io/badge/CI/CD-GitHub_Actions-green)
