
🚀 Airflow DAGs Repository

This repository contains DAGs (Directed Acyclic Graphs) for Apache Airflow. These DAGs define workflows that are executed within an Airflow environment.

🔄 Automated Deployment with GitHub Actions
This repository includes a GitHub Actions workflow that automatically deploys DAGs to an Airflow instance whenever changes are pushed to the main branch.

⚙️ How it Works

On push to main, the workflow runs.
It checks out the repository and finds all .py files inside the dags/ folder.
It sends an HTTP request to the Airflow API to trigger each DAG via curl.
Each DAG gets triggered remotely in the Airflow environment.

🔑 Required Secrets

To securely connect to Airflow, GitHub Actions uses repository secrets. You must configure the following secrets in your repository:


AIRFLOW_URL	The base URL of your Airflow instance (e.g., https://your-ngrok-url.ngrok.io)

AIRFLOW_USER	The username for authenticating with Airflow API

AIRFLOW_PASSWORD	The password for authenticating with Airflow API

To set up secrets in GitHub Actions:

Go to Settings → Secrets and variables → Actions.
Click New repository secret and add the required values.
🚀 Running the Workflow

Commit and push your DAG files (dags/*.py) to the main branch.
GitHub Actions will automatically trigger the workflow and send the DAGs to Airflow.
You can monitor the workflow execution under Actions in your GitHub repository.

🎯 Notes

Ensure your Airflow instance is publicly accessible (e.g., via ngrok).
Logs for the workflow execution are available in GitHub Actions → Workflows.
