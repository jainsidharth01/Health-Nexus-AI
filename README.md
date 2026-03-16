# 🏥 Health Nexus AI – RAG-Based Medical Chatbot

Health Nexus AI is an **AI-powered medical assistant** that answers user queries using **Retrieval Augmented Generation (RAG)**. The system retrieves relevant medical information from a vector database and uses a **Large Language Model (LLM)** to generate contextual responses.

The application demonstrates **end-to-end AI deployment**, combining:

* Retrieval Augmented Generation (RAG)
* Vector databases
* Cloud infrastructure
* Docker containerization
* Automated CI/CD pipelines

The system is deployed using **AWS EC2, Docker, and GitHub Actions CI/CD automation**.

---

# 🚀 Project Overview

This project demonstrates how to build and deploy a **production-style AI application** using modern DevOps practices.

The chatbot works by:

1. Converting user queries into embeddings
2. Retrieving relevant medical documents from a vector database
3. Passing retrieved context to a Large Language Model
4. Generating accurate and contextual responses

This significantly **reduces hallucinations compared to standalone LLM systems**.

---

# 🏗️ System Architecture

The system architecture consists of **two major components**:

* AI Inference Architecture (RAG Pipeline)
* Cloud Deployment & CI/CD Pipeline

---

# AI Inference Architecture (RAG Pipeline)

```id="ragarch"
User Query
   │
   ▼
Flask Web Application
   │
   ▼
LangChain RAG Pipeline
   │
   ├── Query Embedding
   │        │
   │        ▼
   │   Pinecone Vector Database
   │        │
   │   Semantic Search
   │        │
   │   Retrieve Relevant Documents
   │
   ▼
Prompt Construction (Context + Query)
   │
   ▼
Large Language Model (Groq / GPT)
   │
   ▼
Generated Response
   │
   ▼
Flask API Response → User Interface
```

---

# DevOps & Deployment Architecture

```id="devopsarch"
Developer Push Code
        │
        ▼
GitHub Repository
        │
        ▼
GitHub Actions CI/CD Pipeline
        │
        ├── Install Dependencies
        ├── Build Docker Image
        ├── Authenticate to AWS
        ├── Push Image to AWS ECR
        │
        ▼
AWS Elastic Container Registry (ECR)
        │
        ▼
AWS EC2 Instance
        │
        ├── Pull Docker Image
        ├── Run Containerized Flask App
        │
        ▼
Public API Endpoint
        │
        ▼
Users Access Chatbot
```

---

# ✨ Key Features

* AI-powered **Medical Question Answering System**
* **Retrieval Augmented Generation (RAG)** architecture
* **Vector similarity search** using Pinecone
* LangChain based **AI orchestration pipeline**
* **Docker containerized application**
* Automated **CI/CD deployment using GitHub Actions**
* **Cloud deployment on AWS EC2**
* Secure environment variable management

---

# 🛠️ Tech Stack

## Backend

* Python
* Flask

## AI / Machine Learning

* LangChain
* Groq / GPT LLM
* Pinecone Vector Database

## DevOps & Cloud

* Docker
* AWS EC2
* AWS ECR
* GitHub Actions

## Supporting Tools

* YAML
* Python virtual environments
* Environment Variables (.env)

---

# 📂 Project Structure

```id="projectstructure"
├── app.py
├── store_index.py
├── requirements.txt
├── Dockerfile
├── .github
│   └── workflows
│       └── deployment.yml
├── templates
├── static
└── README.md
```

---

# ⚙️ Local Setup & Installation

## 1 Clone the Repository

```bash
git clone https://github.com/jainsidharth01/health-nexus-ai.git
cd health-nexus-ai
```

---

## 2 Create Virtual Environment

Using Conda

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

---

## 3 Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4 Configure Environment Variables

Create a `.env` file in the root directory

```
PINECONE_API_KEY=your_pinecone_api_key
OPENAI_API_KEY=your_openai_api_key
```

---

## 5 Generate Vector Embeddings

Run the following command to process documents and store embeddings in Pinecone

```bash
python store_index.py
```

---

## 6 Run the Application

```bash
python app.py
```

Open in browser

```
http://localhost:5000
```

---

# 🐳 Docker Setup

## Build Docker Image

```bash
docker build -t medical-chatbot .
```

## Run Docker Container

```bash
docker run -p 5000:5000 medical-chatbot
```

---

# ☁️ AWS Deployment with CI/CD

The project uses **GitHub Actions CI/CD pipeline** for automated deployment.

### Deployment Workflow

```
Code Push
   │
   ▼
GitHub Actions Pipeline
   │
   ├ Build Docker Image
   ├ Push Image to AWS ECR
   └ Deploy Container to AWS EC2
```

---

# 🔐 AWS Setup Steps

## 1 Create IAM User

Required permissions

* EC2 Access
* ECR Access

Policies

```
AmazonEC2ContainerRegistryFullAccess
AmazonEC2FullAccess
```

---

## 2 Create ECR Repository

Example

```
aws_account_id.dkr.ecr.region.amazonaws.com/medicalbot
```

---

## 3 Launch EC2 Instance

Recommended configuration

* Ubuntu Server
* t2.micro / t3.micro
* Allow inbound traffic on port **5000**

---

## 4 Install Docker on EC2

```bash
sudo apt update
sudo apt install docker.io -y
sudo usermod -aG docker ubuntu
newgrp docker
```

---

## 5 Configure GitHub Self Hosted Runner

Go to

```
Repository → Settings → Actions → Runners
```

Add a **self-hosted runner** and run the setup commands provided by GitHub.

---

# 🔑 GitHub Secrets Configuration

Add the following repository secrets

```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
PINECONE_API_KEY
OPENAI_API_KEY
```

---

# 📊 DevOps Highlights

* Containerized the application using **Docker**
* Built an automated **CI/CD pipeline using GitHub Actions**
* Used **AWS ECR** for container image storage
* Deployed AI application on **AWS EC2**
* Implemented **automated build and deployment workflow**

---

# 🎯 Learning Outcomes

This project provided hands-on experience with:

* Retrieval Augmented Generation (RAG)
* AI system deployment
* Vector databases
* Docker containerization
* CI/CD pipeline automation
* Cloud infrastructure on AWS

---

# 📌 Future Improvements

* Add authentication system
* Integrate larger medical datasets
* Deploy with Kubernetes
* Add monitoring with Prometheus & Grafana
* Implement production-grade logging

---

# 👨‍💻 Author

Siddharth Jain

Cloud & DevOps Engineer | AI Systems | Linux

GitHub
https://github.com/jainsidharth01

LinkedIn
https://linkedin.com/in/siddharth-jain

---

# ⭐ If you found this project useful, consider giving it a star
