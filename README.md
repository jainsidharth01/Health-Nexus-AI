# 🏥 Health Nexus AI – RAG-Based Medical Chatbot

An **AI-powered medical assistant** that uses **Retrieval Augmented Generation (RAG)** to provide accurate responses to medical queries by retrieving relevant information from a knowledge base.

The system integrates **LangChain, Pinecone Vector Database, and LLMs** to enhance response accuracy and reduce hallucinations. The application is deployed using **Docker, AWS EC2, and CI/CD automation with GitHub Actions**.

---

# 🚀 Project Overview

This project demonstrates an **end-to-end AI system deployment** that combines:

* Large Language Models (LLMs)
* Vector Search
* Cloud Infrastructure
* DevOps CI/CD automation

The chatbot retrieves context from indexed medical documents and uses an LLM to generate informed responses.

---

# 🏗️ System Architecture

```
User Query
   │
   ▼
Flask Backend API
   │
   ▼
LangChain RAG Pipeline
   │
   ├── Retrieve Context → Pinecone Vector Database
   │
   ▼
LLM (Groq / GPT Model)
   │
   ▼
Generated Medical Response
```

---

# ✨ Key Features

* AI-powered **Medical Question Answering**
* **Retrieval Augmented Generation (RAG)** pipeline
* Vector similarity search using **Pinecone**
* **LangChain orchestration framework**
* Cloud deployment on **AWS EC2**
* Containerized using **Docker**
* Automated deployment using **GitHub Actions CI/CD**
* Secure credential management using **environment variables**

---

# 🛠️ Tech Stack

### Backend

* Python
* Flask

### AI / Machine Learning

* LangChain
* LLM (Groq / GPT)
* Pinecone Vector Database

### DevOps & Cloud

* Docker
* AWS EC2
* AWS ECR
* GitHub Actions (CI/CD)

### Other Tools

* YAML
* Environment Variables (.env)

---

# 📂 Project Structure

```
├── app.py
├── store_index.py
├── requirements.txt
├── Dockerfile
├── .github/workflows
│   └── deployment.yml
├── templates
├── static
└── README.md
```

---

# ⚙️ Local Setup & Installation

## 1️⃣ Clone the Repository

```bash
git clone https://github.com/jainsidharth01/health-nexus-ai.git
cd health-nexus-ai
```

---

# 2️⃣ Create Virtual Environment

Using Conda:

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

---

# 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 4️⃣ Configure Environment Variables

Create a `.env` file in the root directory.

```
PINECONE_API_KEY=your_pinecone_api_key
OPENAI_API_KEY=your_openai_api_key
```

---

# 5️⃣ Generate Vector Embeddings

Run the following command to process documents and store embeddings in Pinecone.

```bash
python store_index.py
```

---

# 6️⃣ Start the Application

```bash
python app.py
```

Open your browser and navigate to:

```
http://localhost:5000
```

---

# 🐳 Docker Setup

## Build Docker Image

```bash
docker build -t medical-chatbot .
```

## Run Container

```bash
docker run -p 5000:5000 medical-chatbot
```

---

# ☁️ AWS Deployment with CI/CD

This project uses **GitHub Actions for automated deployment** to AWS.

### Deployment Workflow

```
Code Push
   │
   ▼
GitHub Actions Pipeline
   │
   ├── Build Docker Image
   ├── Push Image to AWS ECR
   └── Deploy Container to EC2
```

---

# 🔐 AWS Setup Steps

## 1️⃣ Create IAM User

Grant access for:

* EC2
* ECR

Policies:

```
AmazonEC2ContainerRegistryFullAccess
AmazonEC2FullAccess
```

---

# 2️⃣ Create ECR Repository

Example:

```
aws_account_id.dkr.ecr.region.amazonaws.com/medicalbot
```

---

# 3️⃣ Launch EC2 Instance

Recommended:

* Ubuntu
* t2.micro / t3.micro
* Allow inbound traffic on port **5000**

---

# 4️⃣ Install Docker on EC2

```bash
sudo apt update
sudo apt install docker.io -y
sudo usermod -aG docker ubuntu
newgrp docker
```

---

# 5️⃣ Configure GitHub Self Hosted Runner

Go to:

```
Repository → Settings → Actions → Runners
```

Add **Self Hosted Runner** and follow the setup commands.

---

# 🔑 GitHub Secrets Configuration

Add the following secrets in your repository:

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

* Containerized application using **Docker**
* Implemented **CI/CD pipeline using GitHub Actions**
* Deployed AI system to **AWS EC2**
* Used **AWS ECR for container registry**
* Automated build and deployment workflow

---

# 🎯 Learning Outcomes

Through this project I gained hands-on experience with:

* AI system deployment
* Retrieval Augmented Generation (RAG)
* Vector databases
* Cloud infrastructure
* DevOps CI/CD pipelines
* Containerized applications

---

# 📌 Future Improvements

* Add **user authentication**
* Integrate **medical knowledge datasets**
* Deploy with **Kubernetes**
* Add **monitoring with Prometheus & Grafana**

---

# 👨‍💻 Author

**Siddharth Jain**

Cloud & DevOps Engineer | AI Systems | Linux

GitHub
https://github.com/jainsidharth01

LinkedIn
https://linkedin.com/in/siddharth-jain

---

# ⭐ If you found this project useful, consider giving it a star!
