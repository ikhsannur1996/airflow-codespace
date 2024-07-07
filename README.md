**Running Apache Airflow with GitHub Codespaces**
================================================

### Introduction
----------------

Apache Airflow is a powerful workflow management platform designed for data engineering pipelines. It allows users to programmatically define, schedule, and monitor workflows. In this guide, we will explore how to run Airflow using GitHub Codespaces, a cloud-based development environment provided by GitHub.

### Step 1: Fork the Repository
Fork this repository on GitHub.

### Step 2: Create a New Codespaces Project
Create a new GitHub Codespaces project on your fork. Ensure it uses at least 2 cores.

### Step 3: Create Subdirectories
Inside the directory, create three subdirectories: `dags`, `logs`, `plugins` and config. These will be used to store DAG files, logs, and plugins respectively:
```bash
mkdir -p ./dags ./logs ./plugins ./config
echo -e "AIRFLOW_UID=$(id -u)" > .env
```

### Step 4: Initialize Airflow Database
Initialize the Airflow database by running the following command:
```bash
docker-compose up airflow-init
```
This command will create the necessary database schema for Airflow.


### Step 5: Start Airflow Services
Start all Airflow services by running the following command:
```bash
docker-compose up
```
This command will start the scheduler, webserver, worker, and other services defined in the `docker-compose.yaml` file.

### Step 6: Access the Airflow UI
Access the main UI of Airflow by clicking on the Ports tab and opening the forward URL for port 8080. If there is an error, check the URL for example:
```bash
https://ideal-meme-6rg6gqq554j25vq9-8080.app.github.dev:8080/home
```
Remove the **:8080** from the URL and the web UI will run again.
```bash
https://ideal-meme-6rg6gqq554j25vq9-8080.app.github.dev/home
```
### Step 7: Log in to Airflow
Log in to the Airflow UI using the credentials user: **airflow** and password:**airflow**.

### Step 8: The Main UI of Airflow
After successful login, the main UI will be shown.

### References
--------------

- **Apache Airflow Documentation**: https://airflow.apache.org/docs/apache-airflow/2.0.2/index.html
- **Docker Documentation**: https://docs.docker.com/get-started/

Citations:
[1] https://github.com/TJaniF/airflow-elt-blueprint
