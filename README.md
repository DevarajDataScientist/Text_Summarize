# 📚 End-to-End Text Summarizer Project

This project implements an **End-to-End Text Summarization** pipeline that leverages a streamlined workflow for configuration, pipeline creation, and deployment. It includes an interactive web application for summarizing text efficiently.

---

## 🛠 Workflows

1. **Update config.yaml**: Define project-wide configurations.
2. **Update params.yaml**: Set hyperparameters and model parameters.
3. **Update entity**: Define entities for the project.
4. **Update the configuration manager in `src/config`**: Manage configurations effectively.
5. **Update the components**: Build modular, reusable components.
6. **Update the pipeline**: Construct the data and ML pipeline.
7. **Update the `main.py`**: Define the project’s entry point.
8. **Update the `app.py`**: Create a web application for text summarization.

---

## 🚀 How to Run?

### **STEPS**:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/entbappy/End-to-end-Text-Summarization
   ```
2. **Create a Conda environment**:
   ```bash
   conda create -n summary python=3.8 -y
   conda activate summary
   ```
3. **Install the requirements**:
   ```bash
   pip install -r requirements.txt
   ```
4. **Run the application**:
   ```bash
   python app.py
   ```

5. Open your local host and port to access the application.

---

## ✍️ Author

- **Devaraj Veeravel**  
  *Data Scientist*  
  Email: [devarajveeravel@gmail.com](mailto:devarajveeravel@gmail.com)

---

# 🛡️ AWS CI/CD Deployment with GitHub Actions

This project supports **AWS CI/CD Deployment** using **GitHub Actions**, ensuring seamless deployment of the text summarizer application.

### Deployment Steps:

1. **Login to AWS Console**:
   - Create an **IAM user** for deployment with the following policies:
     - `AmazonEC2ContainerRegistryFullAccess`
     - `AmazonEC2FullAccess`

2. **Prepare AWS Resources**:
   - **ECR**: Create a repository in Elastic Container Registry to store the Docker image.
     - Save the URI (e.g., `566373416292.dkr.ecr.us-east-1.amazonaws.com/text-s`).
   - **EC2**: Launch an Ubuntu EC2 instance to host the application.

3. **Install Docker on EC2**:
   ```bash
   sudo apt-get update -y
   sudo apt-get upgrade -y
   curl -fsSL https://get.docker.com -o get-docker.sh
   sudo sh get-docker.sh
   sudo usermod -aG docker ubuntu
   newgrp docker
   ```

4. **Deploy the Application**:
   - **Build the Docker image** of the source code.
   - **Push the Docker image to ECR**.
   - **Pull the Docker image in EC2** and launch it.

5. **Configure EC2 as a Self-Hosted Runner**:
   - Navigate to `Settings > Actions > Runners > New self-hosted runner`.
   - Follow the provided commands to set up the runner.

6. **Setup GitHub Secrets**:
   Add the following secrets in your GitHub repository:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `AWS_REGION` (e.g., `us-east-1`)
   - `AWS_ECR_LOGIN_URI` (e.g., `566373416292.dkr.ecr.us-east-1.amazonaws.com`)
   - `ECR_REPOSITORY_NAME` (e.g., `text-s`)

---

## 📜 Summary of Deployment

1. **Build Docker image** of the application.
2. **Push the image to ECR** for storage.
3. **Launch an EC2 instance** and pull the Docker image.
4. **Run the application** on EC2 as a Docker container.

This setup ensures reliable, scalable, and automated deployment for production-ready applications.
