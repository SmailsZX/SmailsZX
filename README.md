<div align="center">

# 👋 Привет, я Андрей Макаров

### 🐍 Python Backend / AI Developer

**Иркутск (UTC+8)** · **Junior+** · **Открыт к удалёнке и гибриду**

[![Telegram](https://img.shields.io/badge/Telegram-@BalumbaZX-26A5E4?logo=telegram&logoColor=white)](https://t.me/BalumbaZX)
[![Email](https://img.shields.io/badge/Email-amak04@yandex.ru-EA4335?logo=gmail&logoColor=white)](mailto:amak04@yandex.ru)
[![GitHub](https://img.shields.io/badge/GitHub-SmailsZX-181717?logo=github&logoColor=white)](https://github.com/SmailsZX)

</div>

---

<div align="center">

### 💡 Разрабатываю backend-сервисы на Python

Асинхронные очереди · REST API · AI-агенты и RAG

**Фокус:** отказоустойчивость, наблюдаемость, тесты.

</div>

---

## 🛠 Технические компетенции

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

### ⚙️ Инфраструктура
![Docker](https://img.shields.io/badge/Docker-24-2496ED?logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?logo=githubactions&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Ubuntu-E95420?logo=linux&logoColor=white)

![Prometheus](https://img.shields.io/badge/Prometheus-metrics-E6522C?logo=prometheus&logoColor=white)
![Structlog](https://img.shields.io/badge/Structlog-structured%20logs-2C3E50)

</td>
<td valign="top" width="50%">

### 🎨 Дополнительно
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-15-000000?logo=nextdotjs&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-E2E-2EAD33?logo=playwright&logoColor=white)

</td>
</tr>
</table>

---

## 🚀 Избранные проекты

<table>
<tr>
<td width="50%" valign="top">

### 📦 [async-task-queue](https://github.com/SmailsZX/async-task-queue)

> Распределённая очередь фоновых задач с отказоустойчивостью

**Что решает:** обработка фоновых задач без потерь при падении воркеров

**Реализовано:**
- ✅ Retry с экспоненциальной задержкой
- ✅ Dead Letter Queue (`tasks.dlq`)
- ✅ Timeout через `TASK_TIMEOUT`
- ✅ Prometheus-метрики (статусы, latency, retry count)
- ✅ Rate limiting на Redis

![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![Taskiq](https://img.shields.io/badge/Taskiq-FF6F61)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?logo=rabbitmq&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)

**`40 тестов`** · **`CI/CD`** · **`Docker`**

</td>
<td width="50%" valign="top">

### 🧠 [chutye-quotes](https://github.com/SmailsZX/chutye-quotes)

> In-memory витрина с оптимизацией памяти

**Что решает:** приём снимка 340k записей (110 МБ) при лимите 256 МБ

**Реализовано:**
- ✅ Хранение JSON-строк: **146 MiB вместо 237 MiB (–38%)**
- ✅ Потоковый парсер до 110 МБ без загрузки в память
- ✅ Двухфазный импорт с rollback
- ✅ Circuit breaker + `Retry-After`
- ✅ LRU-эвикция с TTL

![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![httpx](https://img.shields.io/badge/httpx-3.x-2C3E50)
![orjson](https://img.shields.io/badge/orjson-fast-FF6F00)

**`50 тестов`** · **`CI/CD`** · **`Docker`**

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ✅ [task-tracker-api](https://github.com/SmailsZX/task-tracker-api)

> REST API с JWT-авторизацией и CRUD

**Реализовано:**
- ✅ JWT (access + refresh) + bcrypt
- ✅ SQLAlchemy 2.0 typed Mapped API
- ✅ Alembic-миграции
- ✅ Каждый пользователь видит только свои задачи

![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?logo=sqlalchemy&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?logo=jsonwebtokens&logoColor=white)

**`13 тестов`** · **`CI/CD`** · **`Docker`**

</td>
<td width="50%" valign="top">

### 💬 [rag-telegram-bot](https://github.com/SmailsZX/rag-telegram-bot)

> RAG на локальной LLM — без облака

**Что решает:** ответы по документам без отправки данных наружу

**Пайплайн:** PDF → чанки → эмбеддинги → ChromaDB → top-3 → Qwen2.5

![aiogram](https://img.shields.io/badge/aiogram-3.15-2CA5E0?logo=telegram&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?logo=langchain&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-FF6F00)
![Ollama](https://img.shields.io/badge/Ollama-000000)

**`10 тестов`** · **`CI/CD`** · **`Docker`**

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🤖 [ai-agent-langchain](https://github.com/SmailsZX/ai-agent-langchain)

> ReAct-агент на LangGraph с tool use

**Что делает:** LLM сам решает, какой инструмент вызвать

**Инструменты:** калькулятор · погода · RAG-поиск

![LangGraph](https://img.shields.io/badge/LangGraph-FF6F61)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?logo=langchain&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000)

**`9 тестов`** · **`CI/CD`**

</td>
<td width="50%" valign="top">

### 🔍 [thermal-diagnosis](https://github.com/SmailsZX/thermal-diagnosis)

> Нейросетевая диагностика электрооборудования

**Что делает:** классификация термограмм — НОРМА / ПЕРЕГРЕВ / НЕИСПРАВНОСТЬ

**Точность:** ~85–90% на валидации

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?logo=opencv&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)

**`14 тестов`** · **`CI/CD`** · **`Docker`**

</td>
</tr>
</table>

---

## 🔧 Open Source

<div align="center">

### 🌿 [hololinked](https://github.com/hololinked-dev/hololinked/pull/191) — PR #191

**Поддержка docstring под определением Property**

AST-парсер в `ThingMeta` заполняет `Property.doc` из строкового литерала, 
стоящего сразу после определения. Explicit `doc="..."` имеет приоритет. 
Graceful fallback для REPL/ноутбуков. 4 теста.

[![PR #191](https://img.shields.io/badge/PR%20%23191-open-yellow?logo=github)](https://github.com/hololinked-dev/hololinked/pull/191)

</div>

---

## 📊 GitHub Stats

<div align="center">

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=SmailsZX&show_icons=true&theme=default&hide_border=true&include_all_commits=true&count_private=true" />
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SmailsZX&layout=compact&hide_border=true&langs_count=8" />

</div>

---

<div align="center">

## 📫 Связаться со мной

[![Telegram](https://img.shields.io/badge/Telegram-@BalumbaZX-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/BalumbaZX)
[![Email](https://img.shields.io/badge/Email-amak04@yandex.ru-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:amak04@yandex.ru)
[![GitHub](https://img.shields.io/badge/GitHub-SmailsZX-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/SmailsZX)

---

### 💼 Открыт к предложениям

**Python Backend / AI Developer** (Junior+ / Middle)

Удалённо · Гибрид · Релокация

</div>

---

<div align="center">
<sub>⭐ Если мои проекты полезны — поставь звезду!</sub>
</div>
