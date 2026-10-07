# Андрей Макаров

**Python Backend / AI Developer** · Иркутск (UTC+8) · Junior+

Разрабатываю backend-сервисы на Python: асинхронные очереди, REST API, 
RAG-пайплайны. Фокус — отказоустойчивость, наблюдаемость и тесты. 
Активно использую AI-инструменты (Claude Code) в ежедневной работе.

---

## 🎯 Чем занимаюсь

- **Асинхронные очереди и фоновые задачи** — Taskiq, RabbitMQ, Redis, retry, DLQ
- **REST API на FastAPI** — SQLAlchemy 2.0, PostgreSQL, JWT, Alembic
- **AI-агенты и RAG** — LangChain, LangGraph, Ollama, ChromaDB
- **Инфраструктура** — Docker, CI/CD (GitHub Actions), Prometheus, Structlog

---

## 🛠 Технические компетенции

| Область | Технологии | Уровень |
|---|---|---|
| **Язык** | Python 3.12 | Expert |
| **Web** | FastAPI, Starlette | Strong |
| **ORM/БД** | SQLAlchemy 2.0, PostgreSQL, Redis | Strong |
| **Очереди** | Taskiq, RabbitMQ, asyncio | Strong |
| **AI/ML** | LangChain, LangGraph, Ollama, PyTorch | Strong |
| **Инфра** | Docker, GitHub Actions, Linux | Strong |
| **Наблюдаемость** | Prometheus, Structlog | Familiar |
| **Дополнительно** | TypeScript, Next.js, Playwright | Familiar |

---

## 🚀 Избранные проекты

### [async-task-queue](https://github.com/SmailsZX/async-task-queue) — распределённая очередь задач

**Проблема:** нужен отказоустойчивый обработчик фоновых задач, который 
не теряет задачи при падении воркеров и не дублирует side effects.

**Решение:** FastAPI принимает задачи через REST → Taskiq кладёт их в 
RabbitMQ → N воркеров обрабатывают параллельно на asyncio → статусы 
хранятся в PostgreSQL (персистентно), результаты — в Redis.

**Что реализовано:**
- Retry с экспоненциальной задержкой + Dead Letter Queue для упавших задач
- Timeout через `TASK_TIMEOUT` — защита от зависших воркеров
- Защита от гонки при отмене задачи (флаг `cancelled` читается из PostgreSQL, не из Redis)
- Prometheus-метрики: статусы, latency, retry count, DLQ size
- Structlog — структурированные логи с request_id
- Rate limiting на Redis (100 req/min на API)

**Что осознанно не реализовано:** idempotency key для внешних side effects. 
Понимаю, что для production с send_email/HTTP нужен outbox pattern + 
идемпотентный получатель, или manual ack. Текущая конфигурация — at-least-once 
(Taskiq `WHEN_EXECUTED`), защита от дублей — на стороне получателя.

**Стек:** FastAPI, asyncio, Taskiq, RabbitMQ, Redis, PostgreSQL, SQLAlchemy 2.0, Alembic, Prometheus, Structlog, Docker  
**40 тестов · CI/CD · Docker Compose (6 сервисов)**

---

### [chutye-quotes](https://github.com/SmailsZX/chutye-quotes) — in-memory витрина с оптимизацией памяти

**Проблема:** сервис должен принимать снимок каталога до 340 000 записей 
(до 110 МБ) раз в несколько минут, укладываясь в лимит 256 МБ памяти 
и 0.5 CPU, при этом держать копию каталога локально.

**Решение:** FastAPI-сервис с in-memory хранилищем, потоковым парсером 
и circuit breaker для защиты каталога.

**Что реализовано:**
- **Оптимизация памяти:** 146 MiB вместо 237 MiB на 340 000 записей (–38%) 
  за счёт хранения JSON-строк в `OrderedDict` вместо Python-словарей
- **Потоковый парсер:** снимок до 110 МБ разбирается по чанкам без 
  загрузки тела целиком в память. Инкрементальный UTF-8 декодер для 
  многобайтных символов на границах чанков
- **Двухфазный импорт:** `begin_snapshot` → `insert_from_snapshot` → 
  `finish_snapshot` с `rollback_snapshot` при ошибке — POST с мусором 
  не теряет данные
- **Circuit breaker** для каталога + уважение `Retry-After` при `503`
- **LRU-эвикция** с TTL и учётом реального размера JSON-строк

**Стек:** Python 3.12, FastAPI, httpx, orjson  
**50 тестов · CI/CD · Docker (memory=256m, cpus=0.5)**

---

### [task-tracker-api](https://github.com/SmailsZX/task-tracker-api) — REST API с JWT

**Стек:** FastAPI 0.115, SQLAlchemy 2.0 (typed Mapped API), PostgreSQL 16, 
Alembic, JWT (python-jose) + bcrypt, Pydantic v2  
**13 тестов · CI/CD · Docker**

5 эндпоинтов: регистрация, логин, CRUD задач, смена статуса, фильтрация. 
Пароли — bcrypt (не sha256). JWT с `sub` и `exp`. Каждый видит только свои задачи.

---

### [rag-telegram-bot](https://github.com/SmailsZX/rag-telegram-bot) — RAG без облака

Telegram-бот с RAG-пайплайном на локальной LLM. Данные не уходят в облако.

**Стек:** aiogram 3.15, LangChain 0.3, ChromaDB 0.5, Ollama (Qwen2.5 7B), 
pypdf, SQLite  
**10 тестов · CI/CD · Docker**

Пайплайн: PDF → чанки (1000 символов, overlap 200) → эмбеддинги 
`nomic-embed-text` → ChromaDB → top-3 поиск → Qwen2.5 → ответ. 
Системный промпт с grounding и защитой от галлюцинаций.

---

### [ai-agent-langchain](https://github.com/SmailsZX/ai-agent-langchain) — ReAct-агент

ReAct-агент на LangGraph с tool use (калькулятор, погода, RAG-поиск). 
Работает полностью локально.

**Стек:** LangChain 1.x, LangGraph 1.x, Streamlit, Ollama (Qwen2.5 7B)  
**9 тестов · CI/CD**

LLM сам решает, какой инструмент вызвать, комбинирует шаги рассуждения 
и действия. Погода — через OpenWeatherMap API (опционально).

---

### [thermal-diagnosis](https://github.com/SmailsZX/thermal-diagnosis) — нейросетевая диагностика

Диагностика электрооборудования по термограммам. Три класса: 
НОРМА / ПЕРЕГРЕВ / НЕИСПРАВНОСТЬ.

**Стек:** PyTorch, OpenCV, scikit-learn  
**14 тестов · CI/CD · Docker**  
**Точность: ~85–90%** на валидации

---

## 🔧 Open Source

- **[hololinked](https://github.com/hololinked-dev/hololinked/pull/191)** — 
  PR #191: поддержка docstring под определением Property. 
  AST-парсер в `ThingMeta`, заполняет `Property.doc` только если 
  он не задан явно. Graceful fallback для REPL/ноутбуков. 4 теста.

---

## 📊 GitHub Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=SmailsZX&show_icons=true&theme=default&hide_border=true&include_all_commits=true)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=SmailsZX&layout=compact&hide_border=true)

---

## 📫 Контакты

- **Email:** amak04@yandex.ru
- **Telegram:** [@BalumbaZX](https://t.me/BalumbaZX)
- **GitHub:** [github.com/SmailsZX](https://github.com/SmailsZX)

Открыт к предложениям **Python Backend / AI Developer** (Junior+ / Middle), 
удалённо или гибрид.
