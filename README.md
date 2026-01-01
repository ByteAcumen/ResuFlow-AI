# CareerForge 🚀

**The Open-Source Career Acceleration Platform**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stack](https://img.shields.io/badge/Stack-Next.js%20|%20FastAPI%20|%20Supabase%20|%20Gemini-blue)](https://github.com/topics/tech)

**CareerForge** (formerly ResuFlow-AI) is a free, open-source platform designed to help developers land their dream jobs. It combines **AI Resume Intelligence**, **Mock Interviews**, and **Community Referrals** into a single powerful application.

All built on a **Zero-Cost Serverless Stack**.

---

## ✨ Features

- **📄 AI Resume Builder & Chat**: Upload your resume and chat with it. Get instant feedback, "roasts", and optimization tips using Google Gemini 1.5.
- **🎤 AI Mock Interviews**: Voice-enabled practice sessions with real-time feedback on your answers.
- **🗺️ Career Roadmaps**: Detailed guides and skill gap analysis for roles like Full Stack Dev, Data Scientist, etc.
- **🤝 Community Referrals**: Connect with verified peers for job referrals.

## 🏗️ Architecture

We use a modern **Serverless** approach to ensure the project is free to run:

- **Frontend**: Next.js 14 (App Router) on **Vercel**.
- **Backend**: FastAPI (Python) on **Render**.
- **Database & Auth**: **Supabase** (Postgres + Auth).
- **AI Engine**: **Google Gemini 1.5 Flash** (Free Tier).

See [ARCHITECTURE.md](./ARCHITECTURE.md) for deep technical details.

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- Python 3.10+
- A [Supabase](https://supabase.com) Account (Free)
- A [Google AI Studio](https://aistudio.google.com) Key (Free)

### Local Development

1.  **Clone the repo**
    ```bash
    git clone https://github.com/StartItUpOne/CareerForge.git
    cd CareerForge
    ```

2.  **Install Dependencies**
    ```bash
    # Coming soon: Monorepo setup script
    npm install
    ```

3.  **Run Development Server**
    ```bash
    npm run dev
    ```

## 🤝 Contributing

We welcome contributions! Please check the issues tab.

## 📄 License

MIT License.
