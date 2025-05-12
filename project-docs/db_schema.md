
---

```markdown
<!-- project-docs/db_schema.md -->

# Database Schema

## Overview

We’re using PostgreSQL with SQLModel. All timestamps use UTC.

---

## Tables

### users
| Column      | Type             | PK  | FK  | Default     | Description                   |
|-------------|------------------|-----|-----|-------------|-------------------------------|
| id          | UUID             | ✓   |     | gen_random_uuid() | Primary key                   |
| email       | VARCHAR(255)     |     |     |             | Unique user identifier        |
| hashed_pwd  | TEXT             |     |     |             | Bcrypt‑hashed password        |
| role        | VARCHAR(20)      |     |     | 'user'      | e.g. 'user', 'admin'          |
| created_at  | TIMESTAMP WITH TZ|     |     | now()       | Record creation time          |
| updated_at  | TIMESTAMP WITH TZ|     |     | now()       | Last update time              |

### projects
| Column       | Type             | PK  | FK       | Default         | Description                        |
|--------------|------------------|-----|----------|-----------------|------------------------------------|
| id           | UUID             | ✓   |          | gen_random_uuid() | Project primary key               |
| owner_id     | UUID             |     | users.id |                 | Owner (foreign key → users)        |
| name         | VARCHAR(100)     |     |          |                 | Human‑readable project name        |
| description  | TEXT             |     |          |                 | Brief summary                      |
| created_at   | TIMESTAMP WITH TZ|     |          | now()           |                                    |
| updated_at   | TIMESTAMP WITH TZ|     |          | now()           |                                    |

### code_snippets
| Column       | Type             | PK  | FK           | Default         | Description                                    |
|--------------|------------------|-----|--------------|-----------------|------------------------------------------------|
| id           | UUID             | ✓   |              | gen_random_uuid() | Snippet primary key                           |
| project_id   | UUID             |     | projects.id  |                 | Associated project                             |
| file_path    | TEXT             |     |              |                 | Path within repo (e.g., `src/modules/auth.py`) |
| content      | TEXT             |     |              |                 | AI‑generated or revised snippet                |
| created_at   | TIMESTAMP WITH TZ|     |              | now()           |                                                |

### tests
| Column       | Type             | PK  | FK           | Default         | Description                            |
|--------------|------------------|-----|--------------|-----------------|----------------------------------------|
| id           | UUID             | ✓   |              | gen_random_uuid() | Test record primary key               |
| snippet_id   | UUID             |     | code_snippets.id |              | Which snippet this test covers       |
| status       | VARCHAR(20)      |     |              | 'pending'       | 'pending', 'passed', 'failed'         |
| last_run     | TIMESTAMP WITH TZ|     |              |                 | Last time this test was executed      |

---

## ER Diagram (ASCII)

