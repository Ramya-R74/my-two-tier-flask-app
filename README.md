# Two-Tier TODO Application

## Project Overview
This project demonstrates the development, containerization, and deployment of a two-tier Python Flask-based TODO application integrated with a MySQL database. The application was deployed across multiple environments, including Minikube and AWS EKS, using both Kubernetes manifest files and Helm charts.

---

## Features
- Custom TODO app built using Python Flask.
- MySQL database for data persistence.
- Containerized application and database using Docker.
- Deployment using Kubernetes manifest files and Helm charts.
- Multi-environment deployment: Minikube and AWS EKS.

---

## Project Workflow

1. **Development:**
   - Created a custom TODO application using Python Flask.
   - The application allows users to manage their tasks effectively.

2. **Version Control:**
   - Pushed the source code to a GitHub repository for version control.

3. **Containerization:**
   - Containerized the Python Flask application and the MySQL database using Docker.
   - Created Docker images for the front-end and database services.
   - Pushed the application Docker image to a DockerHub repository.

4. **Deployment on Minikube:**
   - Deployed the containerized application on Minikube using Kubernetes manifest files.

5. **Helm Chart Creation:**
   - Developed a custom Helm chart to simplify deployment and management of the application on Kubernetes.

6. **GitHub Integration:**
   - Pushed the Helm chart and associated files to a GitHub repository for version control and collaboration.

7. **Deployment on AWS EKS:**
   - Deployed the application on AWS Elastic Kubernetes Service (EKS) using the custom Helm chart.

---

## Project Structure
```
.
├── my-two-tier-flask-app/   # Python Flask TODO application source code
├── mysql/                   # MySQL database configuration files
├── Dockerfile               # Dockerfile for building Flask app image
├── docker-compose.yml       # For local testing of containers
├── kubernetes/              # Kubernetes manifest files
│   ├── deployment.yaml      # Deployment resources
│   ├── service.yaml         # Service resources
├── helm-chart/              # Custom Helm chart for Kubernetes deployment
│   ├── templates/           # Kubernetes resource templates
│   ├── values.yaml          # Configurable parameters
├── README.md                # Project documentation
```

---

## Deployment Steps

### Local Development
1. Clone the repository:
   ```bash
   git clone https://github.com/Ramya-R74/my-two-tier-flask-app.git
   ```
2. Navigate to the project directory:
   ```bash
   cd my-two-tier-flask-app
   ```
3. Build and run the application locally using Docker Compose:
   ```bash
   docker-compose up -d
   ```

### Minikube Deployment
1. Start Minikube:
   ```bash
   minikube start
   ```
2. Apply the Kubernetes manifest files:
   ```bash
   kubectl apply -f kubernetes/
   ```
3. Access the application using the Minikube service URL.

### Helm Chart Deployment on AWS EKS
1. Install the Helm CLI if not already installed:
   ```bash
   curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
   ```
2. Authenticate to your EKS cluster:
   ```bash
   aws eks --region <region> update-kubeconfig --name <cluster-name>
   ```
3. Deploy the application using Helm:
   ```bash
   helm install flask-app helm-chart/
   ```
4. Verify the deployment:
   ```bash
   kubectl get all
   ```

---

## Technologies Used
- **Python Flask**: Backend application framework.
- **MySQL**: Relational database for task management.
- **Docker**: Containerization of the application and database.
- **Kubernetes**: Orchestration platform for managing deployments.
- **Helm**: Package manager for Kubernetes.
- **AWS EKS**: Managed Kubernetes service on AWS.

---

## Repository Links
- **Source Code**: [GitHub Repository](https://github.com/Ramya-R74/my-two-tier-flask-app)
- **Docker Images**: [DockerHub Repository](ramya74/python-flask-app:v1)

---

## Future Enhancements
- Add authentication and authorization to the TODO application.
- Implement CI/CD pipelines for automated testing and deployment.
- Integrate monitoring and logging using tools like Prometheus and Grafana.

---

## Author
This project was developed and documented by Ramya R.
