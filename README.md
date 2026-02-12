# Medical-Chatbot

## How to Run

### Step 1: Clone the Repository

```bash
git clone https://github.com/SaiAkhil-ds/Medical-Chatbot.git
cd Medical-Chatbot
```

### Step 2: Create a Conda Environment

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

### Step 3: Install the Requirements

```bash
pip install -r requirements.txt
```

Perfect 👍
Below is your clean, properly formatted README section.

You can directly copy-paste this into your README.md.

# Medical Chatbot

## 🚀 Setup Instructions

### 1️⃣ Create a `.env` file in the root directory

Add your Pinecone and Groq credentials:

```
PINECONE_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
GROQ_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

> If using OpenAI instead of Groq:
```
OPENAI_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

---

### 2️⃣ Store Embeddings in Pinecone

Run the following command:

```bash
python store_index.py
```

This will:
- Generate embeddings
- Store them in your Pinecone index

---

### 3️⃣ Run the Flask Application

```bash
python app.py
```

Now open your browser and go to:

```
http://localhost:8080
```

---

## 🛠️ Tech Stack Used

- Python
- LangChain
- Flask
- Groq / OpenAI
- Pinecone
- AWS (EC2, ECR)
- GitHub Actions (CI/CD)

---

# ☁️ AWS CI/CD Deployment Guide

## 1️⃣ Login to AWS Console

---

## 2️⃣ Create IAM User for Deployment

Provide the following permissions:

- **AmazonEC2ContainerRegistryFullAccess**
- **AmazonEC2FullAccess**

---

## 3️⃣ Create ECR Repository

Create a new repository in ECR.

Example URI:

```
315865595366.dkr.ecr.us-east-1.amazonaws.com/medicalbot
```

Save this URI — you will need it.

---

## 4️⃣ Create EC2 Instance (Ubuntu)

Launch an EC2 instance using Ubuntu.

---

## 5️⃣ Install Docker on EC2

### Update System

```bash
sudo apt-get update -y
sudo apt-get upgrade -y
```

### Install Docker

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

---

## 🐳 Deployment Flow

1. Build Docker image of source code  
2. Push Docker image to ECR  
3. Launch EC2 instance  
4. Pull image from ECR into EC2  
5. Run Docker container on EC2  

---

## 6️⃣ Configure EC2 as Self-Hosted GitHub Runner

Go to:

```
GitHub Repo → Settings → Actions → Runners → New Self Hosted Runner
```

Choose your OS (Linux) and run the given commands inside EC2 one by one.

---

## 7️⃣ Setup GitHub Secrets

Go to:

```
GitHub Repo → Settings → Secrets and Variables → Actions
```

Add the following secrets:

```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
PINECONE_API_KEY
GROQ_API_KEY   (or OPENAI_API_KEY if using OpenAI)
```

---

# ✅ Final Result

After CI/CD setup:

- Push code to GitHub
- GitHub Actions builds Docker image
- Pushes image to ECR
- EC2 pulls and runs container automatically

Your chatbot is now deployed on AWS 🚀

---
