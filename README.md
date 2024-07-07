**Running Apache Airflow with GitHub Codespaces**
================================================

### Introduction
----------------

Apache Airflow is a powerful workflow management platform designed for data engineering pipelines. It allows users to programmatically define, schedule, and monitor workflows. In this guide, we will explore how to run Airflow using GitHub Codespaces, a cloud-based development environment provided by GitHub.

### Setting Up
--------------

### Step 1: Fork the Repository
Fork this repository on GitHub.

### Step 2: Create a New Codespaces Project
Create a new GitHub Codespaces project on your fork. Ensure it uses at least 2 cores.

### Step 3: Start the Airflow Project
Open Terminal in Code Space and run the following command:
```bash
docker-compose up
```
### Creating Subdirectories
-------------------------

### Step 4: Create Subdirectories
Inside the `airflow` directory, create three subdirectories: `dags`, `logs`, and `plugins`. These will be used to store DAG files, logs, and plugins respectively:
```bash
mkdir dags logs plugins
```

### Initialize Airflow
----------------------

### Step 5: Initialize Airflow Database
Initialize the Airflow database by running the following command:
```bash
docker-compose up airflow-init
```
This command will create the necessary database schema for Airflow.

### Start Airflow Services
-------------------------

### Step 6: Start Airflow Services
Start all Airflow services by running the following command:
```bash
docker-compose up
```
This command will start the scheduler, webserver, worker, and other services defined in the `docker-compose.yaml` file.

### Access the Airflow UI
-------------------------

### Step 7: Access the Airflow UI
Access the Airflow UI by clicking on the **Ports** tab and opening the forward URL for port 8080.

### References
--------------

- **Apache Airflow Documentation**: https://airflow.apache.org/docs/apache-airflow/2.0.2/index.html
- **Docker Documentation**: https://docs.docker.com/get-started/

Citations:
[1] https://github.com/TJaniF/airflow-elt-blueprint
