# 🚗 Vehicle Insurance Prediction – MLOps Project

---

## 🧠 Business Problem

Insurance companies often struggle with identifying which customers are likely to purchase vehicle insurance. Sending offers to the wrong audience wastes time and money, while missing out on the right prospects can hurt business growth.

The goal of this project is to build a machine learning system that predicts whether a customer is likely to buy vehicle insurance based on their profile — age, region, vehicle type, driving history, etc. This helps insurance companies target the right users with personalized offers and optimize marketing strategies.

---

## ⚙️ Project Overview

This project isn’t just about building a model — it’s about building an entire **production-ready ML system**. It covers everything from local development and data pipelines to cloud deployment and CI/CD automation. The structure follows modern MLOps practices to make the system scalable, reliable, and easy to maintain.

---

## 🔨 Project Workflow (Step-by-Step)

---

### 🔧 1. Project Structure & Local Setup

- A base project template is created to organize the files and folders logically.
- `setup.py` and `pyproject.toml` are used to package the project like a professional Python library, allowing imports across modules.
- A virtual environment is set up using Conda to keep dependencies isolated.
- Required libraries are listed in `requirements.txt` and installed.
- `pip list` confirms all dependencies (including local packages) are correctly installed.

---

### 🗄️ 2. MongoDB Atlas (Cloud Database Setup)

- Sign up on MongoDB Atlas and create a new cluster for free.
- Set up a secure username and password.
- Enable access from all IP addresses to allow connections during development.
- Get the connection string (Python driver) and replace your password inside it.
- A sample notebook is created to load your dataset and push it to MongoDB.
- You can verify data upload by checking your MongoDB collection in key-value format.

---

### 🪵 3. Logging & Exception Handling

- A custom logger is created to track everything that happens in the system — from warnings to successful runs.
- An exception handler is written to catch and describe errors cleanly during development and production.
- Both are tested using demo scripts.

---

### 🧠 4. EDA & Feature Engineering

- Exploratory Data Analysis is done in a Jupyter notebook.
- Key patterns, correlations, and insights are discovered from the data.
- Features are cleaned, encoded, and transformed to prepare for modeling.

---

### 🧺 5. Data Ingestion Component

- Constant variables like paths and keys are declared centrally in a config file.
- MongoDB connection logic is written to fetch the data programmatically.
- The ingested data is converted to a DataFrame and prepared for further processing.
- Config and artifact schemas are created to keep data flow consistent and structured.
- The ingestion module is wired into a training pipeline and tested via a demo file.

---

### ✅ 6. Data Validation Component

- A schema file (`schema.yaml`) defines what the input data should look like — including columns, types, and allowed values.
- The validation module checks incoming data against this schema to catch problems early.

---

### 🔄 7. Data Transformation Component

- Handles all preprocessing steps like encoding, scaling, or imputation.
- A custom transformer is added to apply transformations consistently during both training and inference.

---

### 🧪 8. Model Training Component

- A classifier is trained to predict whether a customer will buy vehicle insurance or not.
- The trained model is saved and prepared for version control and deployment.

---

### ☁️ 9. AWS Setup for Model Registry

- AWS IAM user is created for programmatic access.
- Access keys are stored as environment variables for security.
- An S3 bucket is created to store trained model files.
- Python code is written to push and pull models to/from the S3 bucket.
- These cloud interactions are handled using `aws_storage` and `s3_estimator` modules.

---

### 📊 10. Model Evaluation & Model Pusher

- Model evaluation checks if the new model performs better than the existing version using a defined score threshold.
- If the new model is better, it is automatically pushed to the model registry in the cloud.
- This ensures only the best-performing models are used.

---

### 🌍 11. Web App & Prediction Pipeline

- A Flask-based web application is created to allow users to input customer details and get insurance predictions in real time.
- HTML templates and static assets are added to improve UI.
- A separate prediction pipeline loads the model and handles user input.

---

### 🔁 12. CI/CD Pipeline (GitHub Actions + AWS EC2)

- Dockerfile and workflow scripts are added to containerize the app.
- GitHub Actions automates the build, test, and deploy pipeline.
- AWS ECR is used to store Docker images.
- An EC2 instance is set up as a self-hosted runner to receive deployments directly from GitHub.
- GitHub secrets are configured to securely pass AWS credentials to the pipeline.

---

### 🚀 13. Launch & Access the App

- The EC2 instance is configured to allow incoming traffic on a custom port (e.g., 5080).
- Once the pipeline runs, the app becomes live and can be accessed via the EC2 public IP.
- A separate route is available to trigger model training directly from the browser.

---

## 🧰 Tools & Technologies Used

- **Python 3.10**
- **MongoDB Atlas**
- **AWS (S3, EC2, ECR, IAM)**
- **GitHub Actions**
- **Docker**
- **Flask**
- **Conda**
- **Pandas, Scikit-learn**

---

## 💡 Final Thoughts

This project isn’t just about predicting insurance purchases — it’s about building smart, deployable systems that scale in the real world. From raw data to live prediction, every step reflects what real MLOps work looks like.
