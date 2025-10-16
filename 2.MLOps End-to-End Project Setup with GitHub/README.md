# Day-2



Create a GitHub repo and open any code editor [VS-Code].

Once open in VsCode the follow following steps:

Ctrl + Shift + P then Select Git:Clone and Pate the GitHub repo Like It will more HelpFull.

Source ------------ Pipeline ------------> Destigination

From Source to Destigination is called Pipeline.

[MLOPs Flow](https://res.cloudinary.com/canonical/image/fetch/f_auto,q_auto,fl_sanitize,c_fill,w_1082/https%3A%2F%2Fubuntu.com%2Fwp-content%2Fuploads%2Fc74e%2Fmlops.jpg)

Go through the Project setup

Running the file template.py will help to setup fodler / project easy..

what is the Usages of Each folder and file:

![alt text](image.png)

-----------------------------------------------------

.github/ - Contains GitHub-specific configurations like CI/CD workflows, issue templates, and GitHub Actions for automated testing, deployment, and MLOps pipelines.

-----------------------------------------------------

experiment/ - Houses experimental notebooks, exploratory data analysis (EDA), and prototype code. Keeps research separate from production code.

-----------------------------------------------------

src/ - Contains the main source code for your ML application. This is your production-ready, modular, reusable code (data processing, model training, inference, etc.).

-----------------------------------------------------
tests/ - Holds unit tests, integration tests, and validation scripts to ensure code quality and catch bugs early in the development cycle.
📄 Files

-----------------------------------------------------
init_setup.sh - Shell script to automate initial project setup (creating virtual environments, installing dependencies, setting up pre-commit hooks, etc.).

-----------------------------------------------------
pyproject.toml - Modern Python project configuration file (PEP 518). Defines project metadata, dependencies, build system, and tool configurations (replaces setup.py in many cases).

-----------------------------------------------------
README.md - Project documentation explaining what the project does, how to set it up, and how to use it. Essential for collaboration.

-----------------------------------------------------
requirements_dev.txt - Development dependencies (testing tools, linters, formatters like pytest, black, flake8) separate from production requirements.

-----------------------------------------------------
requirements.txt - Production dependencies needed to run the ML application.

-----------------------------------------------------
setup.cfg - Configuration for various Python tools (flake8, pytest, mypy). Centralizes tool settings.

-----------------------------------------------------
setup.py - Python package installation script. Makes your src/ code installable as a package (pip install -e .).

-----------------------------------------------------

template.py - Likely a script to auto-generate this project structure, making it easy to start new MLOps projects with the same organization.

-----------------------------------------------------
tox.ini - Configuration for Tox, which automates testing across multiple Python environments to ensure compatibility.

-----------------------------------------------------



# Day-3

------------------------------------------------

`What is Package:` Meaning of “Package” (General Software Context)

A package is a collection of code, files, or modules bundled together so it can be easily shared, reused, or installed.

Example:

In Python, a package is a folder with an __init__.py file that contains modules (e.g., numpy, pandas).

In Node.js, a package is a directory with a package.json file (e.g., express, react).

In Java, a package organizes classes (e.g., java.util, java.io).

👉 Purpose:
Organizing, reusing, and distributing software in a structured and version-controlled way.

-----------------------------------------
| Component                   | Description                                                                                     |
| --------------------------- | ----------------------------------------------------------------------------------------------- |
| **Model Artifacts**         | Trained model file (`.pkl`, `.pt`, `.onnx`, etc.)                                               |
| **Code**                    | Preprocessing, feature engineering, and inference scripts                                       |
| **Dependencies**            | Libraries like TensorFlow, scikit-learn, pandas, etc. (`requirements.txt` or `environment.yml`) |
| **Configurations**          | Hyperparameters, API keys, environment variables                                                |
| **Metadata**                | Model version, metrics, experiment logs                                                         |
| **Docker Image (Optional)** | Full container with OS + dependencies + model code                                              |

---------------------------------------

| Tool                         | Purpose                                                                    |
| ---------------------------- | -------------------------------------------------------------------------- |
| **Docker**                   | Packages your entire ML application (code + dependencies) into a container |
| **MLflow**                   | Packages and tracks ML models; lets you deploy using `mlflow models serve` |
| **TensorFlow Serving**       | Packages and serves TensorFlow models via REST API                         |
| **ONNX**                     | Packages models in a standard format for cross-framework deployment        |
| **PyInstaller / setuptools** | Turns Python ML scripts into installable executables or wheels             |

-----------------------------------------------------


| Context                  | Meaning of “Package”                                                     |
| ------------------------ | ------------------------------------------------------------------------ |
| **Software Development** | A bundle of reusable modules or libraries                                |
| **Python**               | Folder of modules with `__init__.py`                                     |
| **MLOps**                | Complete deployable unit containing model, code, and dependencies        |
| **DevOps / CI-CD**       | Packaged artifact ready for deployment (e.g., Docker image, `.whl` file) |



---------------------------------------------------



`How mongoDB works with MLOPs and ML:`
MongoDB is a NoSQL database (document-oriented) that stores data as JSON-like documents.
In MLOps, MongoDB is used to store:

Training data or features (semi-structured)

Model metadata (accuracy, version, timestamp)

Experiment tracking

Predictions / Inference logs

User feedback loops for model retraining

🔁 Example Workflow:

Raw data collected → stored in MongoDB

ML pipeline reads data from MongoDB → trains model

Predictions and feedback → stored back into MongoDB

MLOps tools (like MLflow, Airflow) use MongoDB for metadata tracking

👉 MongoDB acts as the Data Layer in MLOps pipelines.

---------------------------------------------------

`How to connect mongoDB to ML Application:`
MongoDB → Python (via pymongo) → Pandas/NumPy → Model training/inference

---------------------------------------------------

`What is Testing in MLOPs:`
Testing in MLOps ensures your ML system works correctly end-to-end, not just the model.

🔍 Types of Testing:
Type	Purpose
Unit Testing	Test individual functions or components (e.g., data cleaning function)
Integration Testing	Test combined systems like model + API + DB
Model Testing	Test model performance (accuracy, precision, drift)
Data Validation Testing	Detect missing, corrupted, or drifted data
CI/CD Testing	Automatically test model pipeline before deployment

🧠 Example:
You can use pytest, Great Expectations, or TensorFlow Model Analysis (TFMA) for testing ML pipelines.

---------------------------------------------------

`What is Integration in MLOPs:`
Integration = Connecting all components of the ML lifecycle into one automated system.

⚙️ Integration covers:

Data pipelines (ETL / MongoDB → ML)

Model pipelines (training → testing → deployment)

CI/CD pipelines (GitHub Actions, Jenkins, or Azure DevOps)

Monitoring (Prometheus, Grafana)

Cloud services (AWS, GCP, Azure)

📊 Example:
When you push code to GitHub → it automatically trains model → tests it → deploys API → stores metrics in MongoDB.

---------------------------------------------------

`What is Components in MLOPs Project Setup:`

A complete MLOps project typically includes:

Component	Purpose
Data Source	MongoDB, S3, or SQL database
Data Pipeline	Airflow, Prefect, or custom ETL
Feature Store	Stores processed features (Feast, Hopsworks)
Model Training	TensorFlow, PyTorch, scikit-learn
Experiment Tracking	MLflow, Weights & Biases
Model Registry	Tracks model versions
Deployment	Docker, FastAPI, Flask, Kubernetes
Monitoring	Prometheus, Grafana, Evidently AI
CI/CD	GitHub Actions, Jenkins

---------------------------------------------------

`Server b/w MongoDB and ML Application:`
You often use an API server (backend) between the ML model and MongoDB.

Example Architecture:
MongoDB  ←→  FastAPI/Flask Server  ←→  ML Model  ←→  Frontend

Responsibilities:

Server: Handles requests (predict, insert data, fetch logs)

Model: Runs inference (predicts outputs)

MongoDB: Stores input data, predictions, and results

📦 This server ensures security, scalability, and clean separation between data and model logic.

---------------------------------------------------

`How Atlas helps in MLOps For MongoDB:`
MongoDB Atlas is the cloud-managed version of MongoDB.

🌐 How it helps:
Feature	Description
Cloud-hosted DB	No local setup needed; scales automatically
Secure Connection	TLS/SSL encrypted connections for ML apps
Data API	REST API for ML pipelines without managing servers
Monitoring	Performance dashboards and alerts
Global Clusters	Low latency for distributed MLOps workloads
Integration Ready	Works with AWS, GCP, and Azure ML tools

👉 Atlas = production-ready data infrastructure for MLOps projects.

---------------------------------------------------

`What is Python Client:`
A Python Client is a library or interface that allows Python code to communicate with external services or databases.

Examples:
Service	Python Client
MongoDB	pymongo
Elasticsearch	elasticsearch
AWS	boto3
MLflow	mlflow
Google Cloud	google-cloud-storage

🧩 In MLOps:

You use the Python client to send or receive data from databases (like MongoDB)

Also to connect to APIs or ML services (like MLflow tracking servers)

---------------------------------------------------


| Concept                   | Summary                                              |
| ------------------------- | ---------------------------------------------------- |
| **Package**               | Bundle of model + code + dependencies                |
| **MongoDB in MLOps**      | Stores training data, model logs, predictions        |
| **Connect MongoDB to ML** | Using `pymongo` or Atlas Data API                    |
| **Testing**               | Ensures correctness, stability, and data quality     |
| **Integration**           | Linking all MLOps components into a single pipeline  |
| **Components**            | Data → Model → CI/CD → Monitoring stack              |
| **Server Layer**          | Connects frontend/model with MongoDB (Flask/FastAPI) |
| **Atlas**                 | Cloud MongoDB service for scalable MLOps             |
| **Python Client**         | Interface to interact with databases/APIs in Python  |


--------------------------------------------------

# How and Why to create the Package in MLOPs Applications:

Why Create a Package in MLOps Applications

Creating a package is crucial in MLOps because it ensures that your ML system is:

1️⃣ Reproducible

Other team members or environments can run the same code and model without errors.

Example: Same preprocessing, same model, same dependencies → consistent predictions.

2️⃣ Portable

A packaged model + code can be deployed anywhere: local machine, cloud (AWS/GCP/Azure), or Kubernetes cluster.

Example: Docker container or Python wheel (.whl).

3️⃣ Maintainable

Separates code, configs, and dependencies into a structured, reusable unit.

Makes updates or retraining easier and cleaner.

4️⃣ Version Controlled

Packages can be versioned so you know which model + code combination is running in production.

Example: model_v1.0, model_v1.1.

5️⃣ Supports CI/CD

Packages integrate well with MLOps pipelines: testing, deployment, and monitoring become automated.

=====================================================