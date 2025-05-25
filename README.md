# DevSecOpsForAWS-web-app

This project demonstrates a complete DevSecOps pipeline for building, securing, and deploying any web application onto AWS. The pipeline leverages Jenkins for CI/CD automation, incorporating various security scanning tools at different stages

## Project Overview

The goal of this project is to implement a robust CI/CD pipeline that not only automates the deployment process but also integrates security practices (DevSecOps) throughout the software development lifecycle

## Deployment Stages Diagram

The following diagram illustrates the key stages in our DevSecOps pipeline:

![image](https://github.com/user-attachments/assets/1d8608fc-b85b-409a-a70f-46da039054d9)

## Key Technologies & Tools

*   **CI/CD Automation:** Jenkins
*   **Cloud Platform:** AWS (EC2 for hosting Jenkins, SonarQube, and the application container)
*   **Containerization:** Docker
*   **Container Registry:** DockerHub
*   **Static Application Security Testing (SAST):** SonarQube
*   **Software Composition Analysis (SCA) / Filesystem Scan:** OWASP FS Scan
*   **Container Image Vulnerability Scanning:** Trivy, Docker Scout
*   **Application:** Starbucks Clone (Any sample web application)

## Pipeline Breakdown & Visuals

1.  **Git Checkout:** The Jenkins pipeline automatically checks out the latest code.
2.  **SonarQube Analysis:** Code analyzed for vulnerabilities

       ![image](https://github.com/user-attachments/assets/9f96d2ac-b332-46c1-9679-19f3806a4ca0)

3.  **Quality Gate:** SonarQube Quality Gate checks standards

       ![image](https://github.com/user-attachments/assets/eb5812ac-d968-4df7-8967-9b649dbb6d93)

4.  **OWASP FS SCAN:** Scan for known vulnerabilities in dependencies

       ![image](https://github.com/user-attachments/assets/8012089b-40f3-4058-9035-5c85d7ef5bee)

5.  **Trivy File Scan:** Trivy scans project files

       ![image](https://github.com/user-attachments/assets/27e3073d-761e-4614-90c9-ed679e93405b)

6.  **Build Docker Image:** Docker image for the application is built

7.  **Tag & Push to DockerHub:** Image pushed to DockerHub

       ![image](https://github.com/user-attachments/assets/bddbb571-35e1-4d83-bf3e-ed0fa4634bd2)

8.  **Docker Scout Image:** Analyzes the pushed image

       ![image](https://github.com/user-attachments/assets/cdfc2759-cb5b-4d4e-a3b1-6eddf9504dba)

9.  **Deploy to Container:** Application container deployed
       Screenshot provided at the end


## Setup & Configuration Steps 

These are the general steps followed to set up the environment:

1.  **Create an EC2 Instance:**

       ![image](https://github.com/user-attachments/assets/e46dca78-dae5-4915-8f1a-bd7e5a47f07b)

2.  **Install Packages:** 
       AWS CLI, Jenkins, Docker, Trivy, Docker scout

3.  **Deploy SonarQube Container:**

       ![image](https://github.com/user-attachments/assets/c68a2aa3-cc6b-424a-b191-87802d02c6a0)

4.  **Configure Jenkins:**

       ![image](https://github.com/user-attachments/assets/d3789760-22f2-4f8e-a06a-5e150e408a77)

5.  **Create Secrets:**

       ![image](https://github.com/user-attachments/assets/bad9f529-4930-4a91-8f14-59014439f93b)

6.  **Write the Jenkins Pipeline Script:**

       Provided as jenkinsfile

7.  **Configure Jenkins Job:**

       ![image](https://github.com/user-attachments/assets/990afdd2-fa25-4c3b-a16a-9434c0cdf6d3)

8.  **Deploy and Test:**

       ![image](https://github.com/user-attachments/assets/c9bcced4-3e2d-4df2-a1c8-d0b7d983fe6a)

       ![image](https://github.com/user-attachments/assets/9ec06d98-2ec9-4cd9-b686-46e8929045d3)


## How to Run 

1.  Ensure all prerequisites and configurations mentioned in "Setup & Configuration Steps" are completed
2.  Push your application code, `Dockerfile` to a Git repository
3.  Trigger the Jenkins pipeline job
4.  Observe the pipeline execution
5.  Access the deployed application
