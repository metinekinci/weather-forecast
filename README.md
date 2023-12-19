# Multi-Region Resilient Weather Forecast API

This project demonstrates a resilient, scalable web application deployment across multiple cloud regions using Terraform for infrastructure provisioning and Kubernetes for container orchestration including Go-based API that returns mock weather forecast data.

## Project Structure

- `terraform/`: Contains Terraform configurations to set up the Kubernetes clusters.
- `kubernetes/`: Holds Kubernetes manifests for deploying the web application and associated services.
- `docker/`: Includes the Dockerfile for containerizing the Go API.
- `.github/workflows/`: Defines the GitHub Actions CI/CD pipeline for automated deployment.
- `README.md`: This file, explaining the project setup and execution.

## Prerequisites

- A working knowledge of Terraform, Kubernetes, and Docker.
- Access to a cloud provider account (AWS, GCP, or Azure).
- Docker installed and configured on your local machine.
- kubectl installed and configured on your local machine.
- Helm installed (optional, if you choose to use Helm charts).

## Usage

### Set up Infrastructure with Terraform

1. Navigate to the `terraform/` directory.
2. Initialize Terraform:

    ```sh
    terraform init
    ```

3. Apply the Terraform configuration:

    ```sh
    terraform apply
    ```

### Build and Push the Docker Image

1. Navigate to the `docker/` directory.
2. Build the Docker image:

    ```sh
    docker build -t weather-api:latest .
    ```

3. Push the Docker image to your preferred container registry.

### Deploy with Kubernetes

1. Navigate to the `kubernetes/` directory.
2. Apply the Kubernetes manifests:

    ```sh
    kubectl apply -f deployment.yaml
    kubectl apply -f service.yaml
    kubectl apply -f ingress.yaml
    ```

### Accessing the Application

After deployment, access the application through the load balancer's IP or DNS name provided by your cloud provider.

### Running the CI/CD Pipeline

Push changes to your GitHub repository to trigger the GitHub Actions workflow defined in `.github/workflows/main.yaml`.

## Contributing

Contributions to this project are welcome! Please fork the repository and submit a pull request with your changes or suggestions.

## License

This project is open-sourced under the [MIT License](LICENSE).

## Acknowledgements

- Thanks to all contributors who have helped with code, documentation, and ideas.
- Special thanks to OpenAI for providing guidance on project ideas and implementation strategies.

## Contact Information

For help or questions about this project, please submit an issue in the GitHub repository.

