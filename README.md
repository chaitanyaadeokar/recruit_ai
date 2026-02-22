# RecruitAI: Agentic AI Recruitment System 🧠🚀

RecruitAI is a state-of-the-art recruitment platform powered by autonomous AI agents. It streamlines the entire hiring process—from parsing job descriptions and matching resumes to evaluating candidate performance and scheduling interviews—all while providing clear AI reasoning for every decision.

## ✨ Key Features

- **Autonomous AI Agents**: Specialized agents for Job Descriptions, Resume Matching, Shortlisting, and Interview Scheduling.
- **Explainable AI**: Real-time notifications show the 🧠 reasoning behind every autonomous decision.
- **Seamless Integration**: Connects with MongoDB, ChromaDB, OpenAI, and Google APIs (Calendar/Meet).
- **Multi-Service Architecture**: Distributed backend services for scalability and modularity.
- **Modern Frontend**: A premium, responsive UI built with Vite, React, and Tailwind CSS.

---

## 🏗️ System Architecture

The system consists of several micro-services and specialized agents:

1.  **Core Upload API (Port 8080)**: Handles job profile creation and document processing.
2.  **Shortlisting API (Port 5001)**: Evaluates candidate test performance (e.g., Codeforces data).
3.  **Interview API (Port 5002)**: Manages scheduling and Google Calendar/Meet integration.
4.  **Settings API (Port 5003)**: Manages agent prompts and system monitoring.
5.  **Analytics API (Port 5005)**: Provides recruitment funnel and performance metrics.
6.  **JD Worker**: Background worker for deep PDF parsing.
7.  **Frontend**: Vite+React application for HR dashboard.

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.11+**
- **Node.js (v18+) & npm**
- **MongoDB** (Local or Atlas)
- **OpenAI API Key** (for agent reasoning)

### 1. Repository Setup

```bash
git clone <repository-url>
cd recruit_ai
```

### 2. Backend Installation (using uv)

1.  Ensure you have **uv** installed ([Installation Guide](https://docs.astral.sh/uv/getting-started/installation/)).
2.  Install dependencies and create a virtual environment:
    ```bash
    uv sync
    ```

### 3. Frontend Installation

1.  Navigate to the `front` directory:
    ```bash
    cd front
    npm install
    ```

### 4. Configuration

1.  Create a `.env` file in the **root** directory by copying `.env.example`:
    ```bash
    cp .env.example .env
    ```
2.  Open `.env` and fill in your credentials:
    - `MONGODB_URI`: Your MongoDB connection string.
    - `OPENAI_API_KEY`: Your OpenAI key.
    - `SMTP_*`: Email server details for sending notifications.
    - `GOOGLE_*`: (Optional) For Calendar/Interview scheduling.

### 5. Running the System

#### Windows (Recommended)

Run the provided batch script to start all services simultaneously:

```bash
start_all.bat
```

#### Manual (Linux/macOS)

You will need to open multiple terminal tabs and run:

- **Upload API**: `uv run python backend/upload_api.py`
- **Shortlisting API**: `uv run python agents/shortlisting/api.py`
- **Interview API**: `uv run python agents/interview/api.py`
- **Settings API**: `uv run python backend/settings_api.py`
- **Analytics API**: `uv run python backend/analytics_api.py`
- **JD Worker**: `uv run python agents/jobdescription/main.py`
- **Frontend**: `cd front && npm run dev`

---

## 🧠 AI Agents Explained

View the detailed [AGENTIC_AI_SYSTEM.md](./AGENTIC_AI_SYSTEM.md) for a deep dive into how our autonomous agents think and act.

## 🚢 Deployment

Refer to the [DEPLOYMENT_GUIDE.md](./DEPLOYMENT_GUIDE.md) for instructions on deploying to Render (Backend) and Vercel (Frontend).

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.
