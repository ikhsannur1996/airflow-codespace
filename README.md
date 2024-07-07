**Running Apache Airflow with GitHub Codespaces**
================================================

### Introduction
----------------

Apache Airflow is a powerful workflow management platform designed for data engineering pipelines. It allows users to programmatically define, schedule, and monitor workflows. In this guide, we will explore how to run Airflow using GitHub Codespaces, a cloud-based development environment provided by GitHub. By using GitHub Codespaces, you can run this Airflow project without installing anything locally[1][2].

### Step 1: Fork the Repository
Fork this repository on GitHub.

### Step 2: Create a New Codespaces Project
Create a new GitHub Codespaces project on your fork. Ensure it uses at least 2 cores.

![Screenshot (384)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/097e99ad-b186-4fa4-8c6a-b12655deafba)

![Screenshot (385)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/c2ef5a17-2862-4948-8033-42fc29aab90f)

### Step 3: Create Subdirectories
Inside the directory, create three subdirectories: `dags`, `logs`, `plugins` and config. These will be used to store DAG files, logs, and plugins respectively:
```bash
mkdir -p ./dags ./logs ./plugins ./config
echo -e "AIRFLOW_UID=$(id -u)" > .env
```
![Screenshot (392)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/c0fd820a-64f3-40b8-a52f-d425769dc617)


### Step 4: Initialize Airflow Database
Initialize the Airflow database by running the following command:
```bash
docker-compose up airflow-init
```
This command will create the necessary database schema for Airflow.

![Screenshot (389)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/c2825c80-d2f3-4a00-be21-61f95fe81459)

### Step 5: Start Airflow Services
Start all Airflow services by running the following command:
```bash
docker-compose up
```
This command will start the scheduler, webserver, worker, and other services defined in the `docker-compose.yaml` file.

![Screenshot (395)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/bcc01892-d708-4279-b2a0-7007a451651b)

### Step 6: Access the Airflow UI
Access the main UI of Airflow by clicking on the Ports tab and opening the forward URL for port 8080. 
![Screenshot (398)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/4d770bc0-17cd-4d48-bca8-38884b8e4ce8)

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
![Screenshot (399)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/c092d0a4-2af7-48f0-a6c2-9afa7f61958a)

### Step 8: The Main UI of Airflow
After successful login, the main UI will be shown.
![Screenshot (402)](https://github.com/ikhsannur1996/airflow-codespace/assets/32507742/87bb868d-f91b-483c-a1dc-8d811c634571)


### References
--------------
- **Apache Airflow Documentation**: https://airflow.apache.org/docs/apache-airflow/2.0.2/index.html
- **Docker Documentation**: https://docs.docker.com/get-started/

Citations:
[1] https://github.com/TJaniF/airflow-elt-blueprint
[2] https://github.com/astronomer/astro-cli-codespaces
