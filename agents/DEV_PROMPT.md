# Development Prompt: Sprint 1 (Weeks 1-2)

**Project:** TalentFlow Agent
**Goal:** Core Vacancy Parser + Basic AI Matching
**Stage:** Pre-MVP

---

## 🎯 1. Sprint Goal

The primary objective for this sprint is to implement a minimal viable **Vacancy Parser** and the foundational logic for **Basic AI Matching**. This will validate the core technical feasibility of the project.

## 🛠️ 2. Tech Stack Focus

| Component | Technology | Specific Use |
| :--- | :--- | :--- |
| **Backend Framework** | FastAPI (Python 3.11+) | High-performance API endpoints. |
| **Database** | PostgreSQL, SQLAlchemy | Persistent storage for `Vacancy` and `Application` data. |
| **Parsing** | `aiohttp`, `BeautifulSoup4` | Asynchronous web scraping. |
| **Resilience** | `tenacity`, `aiolimiter` | Rate limiting (30 req/min) and retry logic (exponential backoff). |

## ✅ 3. Key Actionable Tasks

The team must execute the following tasks in priority order:

### Task 3.1: Infrastructure Setup (Deployment)
1.  Create `deployment/docker-compose.yml` to spin up:
    *   `db` service (PostgreSQL)
    *   `redis` service (for caching/queues)
    *   `backend` service (FastAPI application)
2.  Configure the FastAPI application to connect to the `db` and `redis` services.

### Task 3.2: Core Vacancy Parser Implementation (Backend)
1.  Define the SQLAlchemy model for `Vacancy` (must include fields like `title`, `company`, `url`, `description_raw`, `parsed_at`).
2.  Implement an abstract base class `VacancyParser` (as suggested in the System Prompt) with the `parse` method.
3.  Create a concrete implementation: `DjinniParser` that targets `Djinni.co`.
4.  Integrate `aiolimiter` and `tenacity` into the `DjinniParser` to handle rate limiting and retries.

### Task 3.3: API Endpoint
1.  Create a FastAPI endpoint: `POST /api/v1/vacancies/parse` that accepts a search query and triggers the parser.
2.  The endpoint should return the number of vacancies found and their IDs.

### Task 3.4: Basic AI Matching (Foundational)
1.  Create a utility function `match_candidate_to_vacancy(candidate_profile: str, vacancy_description: str) -> float`.
2.  This function should use a simple LLM call (e.g., `gpt-4.1-mini` via `openai` library) to return a match score (0.0 to 1.0) based on the two inputs.

## 📈 4. Metrics of Success

The sprint is successful if the following measurable criteria are met:

1.  **Deployment:** `docker-compose up` runs successfully and all services are connected.
2.  **Performance:** The `DjinniParser` can successfully parse **100 vacancies in under 60 seconds**.
3.  **Resilience:** The parser runs for 1000 requests without receiving a permanent ban (429 errors are handled by retries).
4.  **Functionality:** The `match_candidate_to_vacancy` function returns a valid float score for 10 consecutive test cases.

## ⚖️ 5. Trade-offs and Decisions

*   **Speed vs Quality:** We prioritize **speed to market** for the MVP. We will use simple parsing (BeautifulSoup) over complex browser automation (Selenium) for this sprint.
*   **Database:** We start with a single PostgreSQL instance. No sharding or complex replication is needed at this stage.
*   **AI:** We use a simple, single-turn LLM call for basic matching. Advanced RAG and multi-agent orchestration are deferred to Sprint 2.
