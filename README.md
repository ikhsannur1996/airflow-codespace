**Running Apache Airflow with GitHub Codespaces**

### Introduction

Apache Airflow is a powerful workflow management platform designed for data engineering pipelines. It allows users to programmatically define, schedule, and monitor workflows. In this guide, we will explore how to run Airflow using GitHub Codespaces, a cloud-based development environment provided by GitHub.

### Setting Up

#### Option 1: Using GitHub Codespaces

1. **Fork the Repository**: Fork the Airflow repository on GitHub.
2. **Create a New Codespaces Project**: Create a new GitHub Codespaces project on your fork. Ensure it uses at least 4 cores.
3. **Start the Airflow Project**: After creating the codespaces project, the Astro CLI will automatically start up all necessary Airflow components. This can take a few minutes.
4. **Access the Airflow UI**: Access the Airflow UI by clicking on the **Ports** tab and opening the forward URL for port 8080.

#### Option 2: Using the Astro CLI

1. **Install the Astro CLI**: Download and install the Astro CLI.
2. **Clone the Repository**: Clone the Airflow repository using `git clone https://github.com/astronomer/airflow-quickstart.git`.
3. **Install the Astro CLI**: Follow the Astro CLI documentation to install the necessary packages.
4. **Start the Airflow Project**: Run `astro dev start` in your cloned repository.
5. **Access the Airflow UI**: View the Airflow UI at `localhost:8080`.

### How it Works

1. **Components and Infrastructure**: The repository uses a custom codespaces container to install the Astro CLI. The GH codespaces post creation command starts up the Astro project by running `astro dev start`.
2. **Docker Containers**: Five Docker containers are created and relevant ports are forwarded:
   - Airflow scheduler
   - Airflow webserver
   - Airflow metastore
   - Airflow triggerer
   - MinIO instance (for data storage)

### Project Structure

The repository contains the following files and folders:
- `.astro`: files necessary for Astro CLI commands
- `.devcontainer`: the GH codespaces configuration
- `dags`: all DAGs in your Airflow environment

### Conclusion

Running Airflow with GitHub Codespaces provides a convenient way to manage your workflows without worrying about the underlying infrastructure. This setup allows you to focus on building and managing your workflows while leveraging the power of Airflow.

### References

- Astronomer GitHub Repository: https://github.com/astronomer/airflow-quickstart
- TJaniF GitHub Repository: https://github.com/TJaniF/airflow-elt-blueprint
- YouTube Video: Running Airflow in GitHub Codespaces: https://www.youtube.com/watch?v=-e4hHG4NK9I
- Arun R Nair's Blog: Install Airflow in Windows using Docker in 8 steps: https://arunrnair.hashnode.dev/install-airflow-in-windows-using-docker-in-8-steps

Citations:
[1] https://github.com/astronomer/airflow-quickstart
[2] https://github.com/TJaniF/airflow-elt-blueprint
[3] https://github.com/kavisek/demo-airflow
[4] https://www.youtube.com/watch?v=-e4hHG4NK9I
[5] https://arunrnair.hashnode.dev/install-airflow-in-windows-using-docker-in-8-steps
