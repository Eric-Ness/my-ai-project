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

```

# Technology Stack

## Development Environment
- **IDE:** Cursor IDE with LLM integration
- **Version Control:** Git
- **Package Manager:** pip/poetry
- **Environment Management:** venv/conda

## Core Technologies
- **Language:** Python 3.x
- **Framework:** [Your Framework]
- **Database:** [Your Database]
- **API:** REST/GraphQL

## LLM Integration
- **Primary LLM:** [Your LLM Provider]
- **Development Assistant:** Cursor IDE
- **Code Generation:** [Your Code Generation Tools]
- **Documentation:** [Your Documentation Tools]

## Testing & Quality
- **Testing Framework:** pytest
- **Code Coverage:** coverage.py
- **Linting:** flake8/pylint
- **Formatting:** black
- **Type Checking:** mypy

## CI/CD
- **CI Platform:** GitHub Actions
- **Containerization:** Docker
- **Deployment:** [Your Deployment Platform]

## Monitoring & Logging
- **Logging:** Custom logger module
- **Monitoring:** [Your Monitoring Tool]
- **Error Tracking:** [Your Error Tracking Tool]

## Development Tools
- **Code Generation:**
  - Cursor IDE for LLM-assisted coding
  - AI-powered code completion
  - Automated test generation

- **Documentation:**
  - LLM-assisted documentation generation
  - Automated API documentation
  - Code comment generation

- **Quality Assurance:**
  - AI-powered code review
  - Automated testing
  - Performance optimization

## Best Practices
1. **LLM Integration**
   - Use clear, specific prompts
   - Review generated code
   - Maintain documentation
   - Follow coding standards

2. **Development Workflow**
   - Start with PRD
   - Generate documentation
   - Implement features
   - Test thoroughly
   - Deploy iteratively

3. **Code Quality**
   - Follow PEP 8
   - Write comprehensive tests
   - Document thoroughly
   - Review regularly
