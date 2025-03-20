# Understand MLOps

**Goal:** Understand what MLOps is, why it matters, and the end-to-end MLOps lifecycle

## What is MLOps?

**MLOps**(Machine Learning Operations) is the practice of combining machine learning (ML) and **DevOps** principles to streamline the entire lifecycle of
ML models from experimentation to production and monitoring.

it's a set of practices to:

- Manage and deploy ML models efficiently
- Improve automation, collaboration, and monitoring
- Make ML models reproducible, scalable, and maintainable

## Why MLOps is important?

- **CI/CD for ML:** Automating the training and deployment process.
- **Reproducibility:** Ensuring models and experiments can be repeated.
- **Monitoring and Retraining:** Ensuring models remain accurate over time.
- **Collaboration:** Allows ML Engineers, Data scientists & DevOps Engineers to work together.

## MLOps Lifecycle

**Stage 1: Data management and Experimentation**

- Data collection
- Data versioning
- Feature engineering
- Model training and experiment tracking

**Stage 2: Model deployment**

- Model packaging (Docker, Python packages)
- API serving (FastAPI, Flask)
- Deploy to cloud or Kubernetes

**Stage 3: CI/CD Automation**

- Automate training, test and deployment (Github Actions, Jenkins)

**Stage 4: Monitoring and Observability**

- Service monitoring (Prometheus, Grafana)
- Model performance monitoring (drift detection)

**Stage 5: Continuous training**

- Auto retrain performance degrades (CT pipelines)

## MLOps Tools Overview

| category | Tools |
| -------- | ----- |
| Experiment Tracking | MLFlow, Neptune.ai, Weights & Biases |
| Data & Model versioning | DVC, Git, MLflow registry |
| CI/CD pipelines | Jenkins, Github Actions, Gitlab CI |
| Containerization | Docker, podman |
| Orchestration | Kubernetes, Kubeflow, ArgoCD |
| Serving | FastAPI, Flask, Seldon Core, BentoML |
| Monitoring | Prometheus, Grafana, ELK Stack |
| Cloud Providers | AWS, GCP, Azure |

## Real world use case

For example, companies like Netflix, Spotify, and Uber use MLOps pipeline to:

- Continuously deliver recommendation models
- Detect anamolies
- Serve models globally with high uptime and scalability


