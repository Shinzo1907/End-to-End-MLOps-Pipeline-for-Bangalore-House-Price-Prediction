# End-to-End MLOps Pipeline for House Price Prediction

This repository presents an end-to-end MLOps pipeline for predicting house prices, built using Apache Airflow, Kubernetes, and other Azure services. The pipeline automates data ingestion, processing, model training, and deployment, providing a robust infrastructure for machine learning operations.

## Project Overview

The project aims to build a scalable and automated pipeline for house price prediction, incorporating data ingestion, preprocessing, model training, and deployment with efficient orchestration and monitoring.

## Tools Used

- **Docker Compose**: For containerizing applications and services.
- **Apache Airflow**: Manages and orchestrates the pipeline’s workflows.
- **Azure Container Registry**: Stores Docker images.
- **Azure Kubernetes Service (AKS)**: Manages deployment and scaling of Airflow on Kubernetes.
- **Azure DataLake**: Stores raw and cleaned data.
- **Azure Databricks**: Handles data processing and model training.
- **Streamlit**: Provides a web application for users to interact with the trained model.

## Project Workflow

1. **Data Ingestion**  
   - Uses Apache Airflow DAG to scrape data from the Magic Bricks website and stores it in Azure DataLake.

2. **Data Processing and Model Training**  
   - Airflow triggers a job in Azure Databricks to clean data and train the ML model.

3. **Deployment**  
   - The trained model and preprocessing artifacts are deployed to Azure Web App using CI/CD, making predictions accessible via a Streamlit app.

4. **Artifact Management**  
   - Models and preprocessed data are stored in GitHub for version control.

## Core Components

### Apache Airflow
- **DAGs**: Define workflows for data scraping, cleaning, and model training.
- **Scheduler**: Automates task scheduling based on time triggers.
- **Webserver and UI**: Provides a management interface for DAGs and tasks.
- **Executor**: Manages task execution across worker nodes.

### Kubernetes (AKS)
- **Nodes and Pods**: Deploys Airflow and its components as containers within Kubernetes.
- **Services**: Provides endpoints for inter-service communication and load balancing.
- **Ingress**: Manages external access to the Airflow UI.

### Azure Databricks
- **Clusters**: Run Spark jobs for data processing and model training.
- **Notebooks**: Scripts for data cleaning and training, linked to Airflow DAGs for automation.

### Connections
- **DataLake and Databricks**: Data transfers are facilitated using SAS tokens.
- **Databricks and GitHub**: Stores model artifacts using GitHub’s API.

## Links
- **Streamlit Web App**: [Streamlit Application](https://houserent0908.streamlit.app/)
