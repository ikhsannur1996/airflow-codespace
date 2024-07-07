**Running Apache Airflow with GitHub Codespaces**
================================================

### Introduction
----------------

Apache Airflow is a powerful workflow management platform designed for data engineering pipelines. It allows users to programmatically define, schedule, and monitor workflows. In this guide, we will explore how to run Airflow using GitHub Codespaces, a cloud-based development environment provided by GitHub.

### Step 1: Fork the Repository
Fork this repository on GitHub.

### Step 2: Create a New Codespaces Project
Create a new GitHub Codespaces project on your fork. Ensure it uses at least 2 cores.

![Screenshot (384)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/097e99ad-b186-4fa4-8c6a-b12655deafba)

![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/da88544c-e882-47e8-b479-4f6c081477fc)

### Step 3: Create Subdirectories
Inside the directory, create three subdirectories: `dags`, `logs`, `plugins` and config. These will be used to store DAG files, logs, and plugins respectively:
```bash
mkdir -p ./dags ./logs ./plugins ./config
echo -e "AIRFLOW_UID=$(id -u)" > .env
```

![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/ff475473-c753-49dd-91b4-23ff9484db2b)


### Step 4: Initialize Airflow Database
Initialize the Airflow database by running the following command:
```bash
docker-compose up airflow-init
```
This command will create the necessary database schema for Airflow.

![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/a49306fd-1222-4321-8d75-2972664cf371)



### Step 5: Start Airflow Services
Start all Airflow services by running the following command:
```bash
docker-compose up
```
This command will start the scheduler, webserver, worker, and other services defined in the `docker-compose.yaml` file.


![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/4de3a603-6c93-43cf-92a9-9afc242bae68)


### Step 6: Access the Airflow UI
Access the main UI of Airflow by clicking on the Ports tab and opening the forward URL for port 8080. 
![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/941804da-5c0d-4d7d-8f21-39791308c85b)

If there is an error, check the URL for example:
```bash
https://ideal-meme-6rg6gqq554j25vq9-8080.app.github.dev:8080/home
```
Remove the **:8080** from the URL and the web UI will run again.
```bash
https://ideal-meme-6rg6gqq554j25vq9-8080.app.github.dev/home
```
### Step 7: Log in to Airflow
Log in to the Airflow UI using the credentials user: **airflow** and password:**airflow**.
![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/03f6d366-9c31-4605-a353-c4eae56da6c0)


### Step 8: The Main UI of Airflow
After successful login, the main UI will be shown.
![image](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/eea5383c-ab70-48da-afe0-9eae828ee966)


### References
--------------

- **Apache Airflow Documentation**: https://airflow.apache.org/docs/apache-airflow/2.0.2/index.html
- **Docker Documentation**: https://docs.docker.com/get-started/

Citations:
[1] https://github.com/TJaniF/airflow-elt-blueprint
