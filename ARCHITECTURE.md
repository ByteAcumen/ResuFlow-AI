# Architecture & System Design: CareerForge

## 🎯 Goal
Build **CareerForge**, a comprehensive, open-source **Career Acceleration Platform** deployed for **FREE**.
The system leverages generous **Free Tiers** of managed services to avoid the cost of self-hosting heavy AI models and databases.

## 🛠️ Tech Stack (Free Tier Optimized)

### Frontend: **Next.js 14**
- **Hosting**: **Vercel** (Free Hobby Tier).
- **UI**: **Shadcn/UI** + **Tailwind CSS**.
- **Icons**: **Lucide React**.

### Backend: **FastAPI (Python)**
- **Hosting**: **Render** (Free Web Service).
- **Runtime**: Python 3.10+.
- **Why**: Python is the native language of AI, and Render allows for easy containerized deployment.

### Database & Auth: **Supabase**
*Replaces traditional Postgres/Redis/MinIO setup with a managed serverless platform.*
- **Database**: PostgreSQL (500MB Free).
- **Auth**: Email/Password + Social Login (Unlimited).
- **Storage**: For Resume PDFs (1GB Free).
- **Vector Search**: `pgvector` enabled for RAG (Retrieval Augmented Generation).

### AI Engine: **Google Gemini API**
- **Model**: **Gemini 1.5 Flash**.
- **Cost**: Free (within rate limits).
- **Capabilities**: Large context window (ideal for reading full PDF resumes) and high speed.

## 🏗️ High-Level Architecture

```mermaid
graph TD
    User[User Device] -->|HTTPS| Vercel[Vercel (Next.js Frontend)]
    User -->|API Calls| Render[Render (FastAPI Backend)]
    
    subgraph "Managed Services (Free Tiers)"
        Render -->|Auth/Data| Supabase[Supabase (Auth + DB + Vector)]
        Render -->|Store Files| SupabaseStorage[Supabase Storage]
        Render -->|AI Inference| Gemini[Google Gemini API]
    end
```

## 🧩 Modules

### 1. Resume Intelligence
- **Upload**: Secure upload to Supabase Storage.
- **Analysis**: Text extraction and analysis using Gemini 1.5.
- **Chat**: Q&A with your resume ("Roast my resume", "Rewrite this bullet point").

### 2. Interview Prep
- **Mock Interview**: Voice-based practice interacting with the AI.
- **Question Bank**: Community-sourced questions tagged by Company/Role.

### 3. Career Growth
- **Roadmaps**: Step-by-step guides for technical roles.
- **Referrals**: Peer-to-peer referral board.

## 🛣️ Build Roadmap

1.  **Project Setup**: Initialize Monorepo (Web + API).
2.  **Infrastructure**: Setup Supabase Project and get Gemini API Keys.
3.  **Core Dev**: 
    - Implement Auth.
    - Build Resume Upload & Chat.
    - Build Interview Mock mode.
4.  **Deployment**:
    - Push Web to Vercel.
    - Push API to Render.
