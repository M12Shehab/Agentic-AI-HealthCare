# 🏥 Agentic-AI Healthcare platform

An AI-driven healthcare platform that enables patient-doctor interaction through intelligent agents, secure APIs, and multilingual interfaces.

## 🌟 Key Features

- 🤖 **Agentic AI System** using the MCP (Model Context Protocol)	
- 🧠 **LLM-powered Diagnosis and Recommendations**
- 🌍 **Multilingual Support** (English, French and Arabic)
- 🔐 **Role-based Access Control (RBAC)** for patients and doctors
- 📅 **Appointment Management** with personal history tracking
- 💬 **Explainable AI**: Transparent reasoning for each diagnosis	
- 🌐 **Web-based Chat** Interface built with React	
---

## 🧠 Architecture Overview

```mermaid
graph LR
    UserUI(React Chat UI)
    UserUI -->|HTTP| API(FastAPI Backend)
    API --> |streamable-http| MCP(MCP Server)
    MCP --> Agent1(Symptom Checker Agent)
    MCP --> Agent2(Medication Agent)
    MCP --> Agent4(Appointments Agent)
    API --> MongoDB[(MongoDB Database)]
````

* Agents are coordinated and executed by the MCP agent controller	
* Data is stored securely and queried via RESTful endpoints

---

## 🚀 Getting Started

### Requirements

* Python 3.10+
* Node.js + npm
* Docker (optional)

### Clone the Repository

```bash
git clone https://github.com/m12shehab/Agentic-AI-HealthCare.git
cd smart-healthcare-mcp
```

### Backend (FastAPI + MCP)

```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

### Frontend (React App)

```bash
cd frontend
npm install
npm start
```

### MCP Server (Separate Container or Process)

```bash
cd mcp_server
pip install -r requirements.txt
python main.py
```

---

## 🧪 Example Use Case

1. User describes symptoms:

   > "My throat is sore and I'm sneezing..."

2. MCP routes input to:

   * Symptom Checker → Diagnosis Agent → Medication Agent

3. Output:

   * Diagnosis: Acute Viral Rhinosinusitis
   * Suggestions: Hydration, rest, nasal spray
   * Severity: Medium
   * Language: English / العربية / Français

---

## 🛠️ Tech Stack

| Layer       | Technology              |
| ----------- | ----------------------- |
| Frontend    | React, Tailwind CSS     |
| Backend API | FastAPI, Python         |
| MCP Core    | FastMCP (custom agents) |
| Database    | MongoDB                 |
| Auth        | JWT, RBAC               |
| Deployment  | Docker, Uvicorn, Nginx  |

---

## 🔮 Future Plans

* Add speech-to-text input for patients
* Integrate with public medical databases (e.g. FDA API)
* Export medical summaries as PDF
* Launch demo with persistent cloud backend
* Add admin dashboard and analytics

---

## 📄 License

MIT License — Open source and freely modifiable with attribution.

---



## 🐳 Docker Compose Commands

You can easily run the entire platform using Docker Compose. Here are the essential commands:

### 🔧 Build & Run All Services

```bash
docker-compose up --build
````

> Builds images for all services (frontend, backend, mcp\_server, mongo) and starts them.

---

### 🚀 Start Without Rebuilding (Faster)

```bash
docker-compose up -d
```

> Runs containers in detached mode using previously built images.

---

### ⛔ Stop All Services

```bash
docker-compose down
```

> Stops and removes all containers, keeping the volumes.

---

### 🧹 Stop & Remove Containers + Volumes

```bash
docker-compose down -v
```

> Use this to clean everything, including the MongoDB data.

---

### 🧾 Check Running Containers

```bash
docker ps
```

---

### 🛠️ Access a Running Container (e.g., backend)

```bash
docker exec -it smart-healthcare-mcp-backend-1 bash
```




Developed by [Mohammed Shehab](https://github.com/m12shehab), AI Engineer & Instructor.

