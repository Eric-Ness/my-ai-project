<!-- project-docs/tech_stack.md -->

# Tech Stack & Dependencies

## 1. Language & Runtime
- **Python** 3.11.4  
- **Node.js** 18.16.0 (for any front‑end or toolchain scripts)  
- **Docker** 24.0+ (for containerized deployments)

## 2. Frameworks & Libraries

| Area                    | Library / Tool      | Version     | Purpose                                    |
|-------------------------|---------------------|-------------|--------------------------------------------|
| Web framework           | FastAPI             | 0.101.1     | HTTP API server                            |
| ORM                     | SQLModel            | 0.0.8       | Declarative models + async DB access       |
| Front-end (optional)    | React               | 18.2.0      | Component-based UI                         |
| State management        | Redux Toolkit       | 1.9.5       | Predictable state container                |
| Testing                 | PyTest              | 7.4.0       | Unit & integration testing                 |
| Linting & formatting    | Black               | 23.9.1      | Auto‑formatting Python code                |
|                         | isort               | 5.12.0      | Sort imports                               |
| CI/CD                   | GitHub Actions      | latest      | Build & test workflows                     |
| AI orchestration        | LangChain           | 0.1.XX      | Prompt chaining & memory management        |
| AI model                | OpenAI o4-mini      | latest      | Code generation                            |

## 3. Dev Tools & Utilities
- **VS Code** + Python extension  
- **Cursor.ai** / **Windsurf** as AI pair‑programmer agents  
- **Docker Compose** for local multi‑service testing  
- **Postman** or **HTTPie** for manual API testing  

## 4. Infrastructure & Deployment
- **AWS ECS** (Fargate) or **DigitalOcean App Platform**  
- **RDS PostgreSQL** (db.t3.medium)  
- **S3** for static assets and AI artifact storage  
- **CloudWatch** / **Datadog** for logging & metrics

## 5. Environment Variables

```dotenv
# .env
OPENAI_API_KEY=…
DATABASE_URL=postgresql+asyncpg://user:pass@host:5432/dbname
REDIS_URL=redis://localhost:6379/0
JWT_SECRET=…
