# ResuFlow-AI 🚀

**The Enterprise-Grade, Open-Source AI Resume Chatbot & Formatter**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Tech Stack](https://img.shields.io/badge/Stack-Next.js%20|%20FastAPI%20|%20Kafka%20|%20K8s-blue)](https://github.com/topics/tech)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

**ResuFlow-AI** is a powerful, self-hosted platform that transforms static PDF resumes into interactive, conversational agents. Built with a "Best and Free" philosophy, it leverages top-tier open-source technologies to deliver a premium experience without the premium price tag.

---

## 📖 Table of Contents
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Features

-   **📄 Smart Resume Parsing**: Automatically extracts text and structure from PDF resumes using advanced OCR and layout analysis.
-   **💬 Conversational AI**: Chat with any resume using local LLMs (Llama 3 via Ollama) - ask about experience, skills, or fit.
-   **✨ AI Enhancement**: Get actionable suggestions to improve resume impact and ATS visibility.
-   **⚡ Event-Driven Architecture**: Built on Apache Kafka for robust, asynchronous document processing.
-   **🐳 Cloud-Native Ready**: Fully containerized with Docker and ready for Kubernetes scaling.
-   **🔒 Privacy-First**: All processing happens locally or on your private cloud. No data leaves your control.

---

## 🏗️ Architecture

ResuFlow-AI follows a microservices architecture designed for scalability and resilience.

```mermaid
graph TD
    User[User / Recruiter] -->|HTTP/WebSocket| Ingress[Nginx Ingress]
    Ingress --> Frontend[Next.js Frontend]
    Ingress --> Backend[FastAPI Backend]
    
    Backend -->|Publish Upload Event| Kafka[Apache Kafka]
    Backend -->|Query| PG[PostgreSQL]
    Backend -->|Vector Search| VectorDB[Qdrant/Chroma]
    Backend -->|Chat Generation| Ollama[Ollama (LLM)]
    
    subgraph "Async Worker"
    Worker[Python Worker] -->|Consume Event| Kafka
    Worker -->|Extract Text| PDFLib[PyPDF]
    Worker -->|Generate Embeddings| Ollama
    Worker -->|Store Vectors| VectorDB
    end
```

---

## 🛠️ Tech Stack

| Component | Technology | Description |
|-----------|------------|-------------|
| **Frontend** | Next.js 14 | React framework with Tailwind CSS for a premium UI. |
| **Backend** | FastAPI | High-performance, async Python API. |
| **AI Engine** | Ollama | Local inference for Llama 3 / Mistral (Free & Private). |
| **Vector DB** | Qdrant | High-speed vector search engine for RAG. |
| **Database** | PostgreSQL | Reliable relational storage for user data. |
| **Queue** | Apache Kafka | Enterprise-grade event streaming. |
| **DevOps** | Docker & K8s | Containerization and orchestration. |

---

## 🚀 Getting Started

### Prerequisites
-   **Docker Desktop** (with Kubernetes enabled optional but recommended)
-   **Node.js 18+**
-   **Python 3.10+**

### Quick Start (Docker Compose)

1.  **Clone the repository**
    ```bash
    git clone https://github.com/ByteAcumen/ResuFlow-AI.git
    cd ResuFlow-AI
    ```

2.  **Start the services**
    ```bash
    docker compose up -d
    ```

3.  **Access the application**
    -   Frontend: `http://localhost:3000`
    -   API Docs: `http://localhost:8000/docs`

---

## 🗺️ Roadmap

### Phase 1: Foundation (Current)
- [x] Architecture Design
- [ ] Basic PDF Upload & Parsing
- [ ] Chat Interface with Ollama Integration

### Phase 2: Enhancement
- [ ] Resume Scoring & Improvement Suggestions
- [ ] Multi-Resume Comparison
- [ ] User Authentication (OAuth2)

### Phase 3: Enterprise
- [ ] Kubernetes Helm Charts
- [ ] CI/CD Pipelines
- [ ] Role-Based Access Control (RBAC)

---

## 🤝 Contributing

We welcome contributions from the community! Whether it's a bug fix, new feature, or documentation improvement, we'd love to have your help.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
