<div align="center">

# 👋 Hi, I'm Andrey Makarov

### 🐍 Python Backend / AI Developer

**Irkutsk (UTC+8)** · **Junior+** · **Open to remote and hybrid**

[![Telegram](https://img.shields.io/badge/Telegram-@BalumbaZX-26A5E4?logo=telegram&logoColor=white)](https://t.me/BalumbaZX)
[![Email](https://img.shields.io/badge/Email-amak04@yandex.ru-EA4335?logo=gmail&logoColor=white)](mailto:amak04@yandex.ru)
[![GitHub](https://img.shields.io/badge/GitHub-SmailsZX-181717?logo=github&logoColor=white)](https://github.com/SmailsZX)

</div>

---

<div align="center">

### 💡 Building backend services in Python

Async task queues · REST APIs · AI agents and RAG

**Focus:** reliability, observability, tests.

</div>

---

## 🛠 Technical Stack

<table>
<tr>
<td valign="top" width="50%">

### 🔧 Backend
![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688?logo=fastapi&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-D71F00?logo=sqlalchemy&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-v2-E92063?logo=pydantic&logoColor=white)

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-336791?logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-7-DC382D?logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-3-FF6600?logo=rabbitmq&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-3.1.1%20%7C%205.0-660066?logo=mqtt&logoColor=white)

</td>
<td valign="top" width="50%">

### 🤖 AI / ML
![LangChain](https://img.shields.io/badge/LangChain-1.x-1C3C3C?logo=langchain&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1.x-FF6F61)
![Ollama](https://img.shields.io/badge/Ollama-local%20LLM-000000)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0-EE4C2C?logo=pytorch&logoColor=white)

![ChromaDB](https://img.shields.io/badge/ChromaDB-vector%20db-FF6F00)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-5C3EE8?logo=opencv&logoColor=white)

</td>
</tr>
<tr>
<td valign="top" width="50%">

### ⚙️ Infrastructure
![Docker](https://img.shields.io/badge/Docker-24-2496ED?logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?logo=linux&logoColor=white)

![Prometheus](https://img.shields.io/badge/Prometheus-metrics-E6522C?logo=prometheus&logoColor=white)
![Structlog](https://img.shields.io/badge/Structlog-structured%20logs-2C3E50)

</td>
<td valign="top" width="50%">

### 🎨 Additional
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-15-000000?logo=nextdotjs&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-E2E-2EAD33?logo=playwright&logoColor=white)

</td>
</tr>
</table>

---

## 🚀 Featured Projects

<table>
<tr>
<td width="50%" valign="top">

### 📦 [async-task-queue](https://github.com/SmailsZX/async-task-queue)

> Distributed background task queue with fault tolerance

**Problem:** reliable background job processing without losing tasks on worker crashes

**Implemented:**
- ✅ Retry with exponential backoff
- ✅ Dead Letter Queue (`tasks.dlq`)
- ✅ Timeout via `TASK_TIMEOUT`
- ✅ Prometheus metrics (statuses, latency, retry count)
- ✅ Rate limiting on Redis

![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Taskiq](https://img.shields.io/badge/Taskiq-FF6F61)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)

**`40 tests`** · **`CI/CD`** · **`Docker`**

</td>
<td width="50%" valign="top">

### 🧠 [chutye-quotes](https://github.com/SmailsZX/chutye-quotes)

> In-memory store with memory optimization

**Problem:** ingesting a 340k-record snapshot (110 MB) under a 256 MB memory limit

**Implemented:**
- ✅ JSON-string storage: **146 MiB instead of 237 MiB (–38%)**
- ✅ Streaming parser for 110 MB without loading into memory
- ✅ Two-phase import with rollback
- ✅ Circuit breaker + `Retry-After`
- ✅ LRU eviction with TTL

![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![httpx](https://img.shields.io/badge/httpx-3.x-2C3E50)
![orjson](https://img.shields.io/badge/orjson-fast-FF6F00)

**`50 tests`** · **`CI/CD`** · **`Docker`**

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ✅ [task-tracker-api](https://github.com/SmailsZX/task-tracker-api)

> REST API with JWT auth and CRUD

**Implemented:**
- ✅ JWT (access + refresh) + bcrypt
- ✅ SQLAlchemy 2.0 typed Mapped API
- ✅ Alembic migrations
- ✅ Each user sees only their own tasks

![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?logo=sqlalchemy&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?logo=jsonwebtokens&logoColor=white)

**`13 tests`** · **`CI/CD`** · **`Docker`**

</td>
<td width="50%" valign="top">

### 💬 [rag-telegram-bot](https://github.com/SmailsZX/rag-telegram-bot)

> Local RAG pipeline — no cloud

**Problem:** answering questions from documents without sending data outside

**Pipeline:** PDF → chunks → embeddings → ChromaDB → top-3 → Qwen2.5

![aiogram](https://img.shields.io/badge/aiogram-3.15-2CA5E0?logo=telegram&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?logo=langchain&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F00)
![Ollama](https://img.shields.io/badge/Ollama-000000)

**`10 tests`** · **`CI/CD`** · **`Docker`**

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🤖 [ai-agent-langchain](https://github.com/SmailsZX/ai-agent-langchain)

> ReAct agent on LangGraph with tool use

**What it does:** the LLM decides which tool to call

**Tools:** calculator · weather · RAG search

![LangGraph](https://img.shields.io/badge/LangGraph-FF6F61)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?logo=langchain&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000)

**`9 tests`** · **`CI/CD`**

</td>
<td width="50%" valign="top">

### 🔍 [thermal-diagnosis](https://github.com/SmailsZX/thermal-diagnosis)

> Neural diagnostics for electrical equipment

**What it does:** thermal image classification — NORMAL / OVERHEAT / FAULT

**Accuracy:** ~85–90% on validation

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)

**`14 tests`** · **`CI/CD`** · **`Docker`**

</td>
</tr>
</table>

## 🔧 Open Source

<div align="center">

### 🌿 [hololinked](https://github.com/hololinked-dev/hololinked) — Collaborator

**Python framework for data acquisition and IoT**

- **[PR #191](https://github.com/hololinked-dev/hololinked/pull/191)** (merged): 
  attribute docstrings below property definitions — AST parser in `ThingMeta`. 
  Explicit `doc="..."` wins; graceful fallback for REPL/notebooks. 4 tests.

- **[PR #200](https://github.com/hololinked-dev/hololinked/pull/200)** (merged): 
  MQTT WebSocket transport for publisher and consumer. TLS-enabled WebSocket 
  listener, `wss://` / `ws://` TD forms. 2 e2e tests.

- **[PR #205](https://github.com/hololinked-dev/hololinked/pull/205)** (merged): 
  MQTT v5 content type from properties in consumer. Safe `getattr` fallback 
  for paho/aiomqtt. Bumped version to 0.4.2.

Merged into `main`, included in releases **v0.4.1** and **v0.4.2**.

[![PR #191](https://img.shields.io/badge/PR%20%23191-merged-brightgreen?logo=github)](https://github.com/hololinked-dev/hololinked/pull/191)
[![PR #200](https://img.shields.io/badge/PR%20%23200-merged-brightgreen?logo=github)](https://github.com/hololinked-dev/hololinked/pull/200)
[![PR #205](https://img.shields.io/badge/PR%20%23205-merged-brightgreen?logo=github)](https://github.com/hololinked-dev/hololinked/pull/205)

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=SmailsZX&show_icons=true&theme=default&hide_border=true&include_all_commits=true&count_private=true" />
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SmailsZX&layout=compact&hide_border=true&langs_count=8" />

</div>

---

<div align="center">

## 📫 Get in Touch

[![Telegram](https://img.shields.io/badge/Telegram-@BalumbaZX-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/BalumbaZX)
[![Email](https://img.shields.io/badge/Email-amak04@yandex.ru-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:amak04@yandex.ru)
[![GitHub](https://img.shields.io/badge/GitHub-SmailsZX-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SmailsZX)

---

### 💼 Open to opportunities

**Python Backend / AI Developer** (Junior+ / Middle)

Remote · Hybrid · Relocation

</div>

---

<div align="center">
<sub>⭐ If you find my projects useful — give them a star!</sub>
</div>
