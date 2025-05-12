<!-- project-docs/implementation_plan.md -->

# Implementation Plan

**Objective:** Build “Auth Module” feature end‑to‑end using AI assistant.

---

## Phase 1: Setup & Scaffolding (Day 1)
1. **Initialize Repo**  
   - Create `git` repository  
   - Add README, `.gitignore`, `requirements.txt`  
   - Commit initial skeleton  
2. **Create Base FastAPI App**  
   - `app = FastAPI()` in `src/main.py`  
   - Health‑check endpoint (`GET /health`)  
   - Dockerfile + docker‑compose.yml  
3. **PRD Ingestion**  
   - Place `prd.md` and all docs in `/project-docs`  
   - Write `.cursor/rules` to “always read prd.md & project-docs/*”

---

## Phase 2: Database & Models (Day 2)
1. **Define ORM Models**  
   - `User`, `Project` in `src/models.py` using SQLModel  
2. **Create Migrations**  
   - Alembic setup  
   - Initial migration for `users` & `projects` tables  
3. **Database Connection**  
   - Async engine in `src/db.py`  
   - Dependency injections for session in `src/deps.py`

---

## Phase 3: Auth Endpoints (Day 3)
1. **Signup**  
   - `POST /auth/signup` → create user, hash pw, return JWT  
   - Unit tests for password hashing & token generation  
2. **Login**  
   - `POST /auth/login` → verify creds, issue JWT  
   - Error handling (invalid creds)  
3. **Protected Route**  
   - `GET /users/me` → return current user’s profile  
   - Test unauthorized access handling

---

## Phase 4: CI/CD & Testing (Day 4)
1. **Write PyTest Suites**  
   - Auth tests in `tests/test_auth.py`  
   - Use TestClient for API calls  
2. **GitHub Actions Workflow**  
   - Run lint, format check, pytest on push to `main`  
3. **Docker Build & Push**  
   - Build multi‑stage image, push to registry on tag

---

## Phase 5: Review & Polish (Day 5)
1. **Documentation**  
   - Update README with usage, env vars, examples  
   - Add code snippets cheatsheet in `/project-docs`  
2. **Error Handling & Logging**  
   - Integrate Sentry or similar  
   - Standardize error responses  
3. **Final Demo**  
   - Record short video of signup → protected route → CI pass  
   - Gather feedback & iterate