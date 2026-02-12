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

