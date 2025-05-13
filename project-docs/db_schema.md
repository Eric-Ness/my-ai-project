# Database Schema and Design

## LLM-Assisted Database Design Process

### 1. Schema Design
- Use LLM to generate initial schema
- Review and refine with domain knowledge
- Validate against requirements
- Optimize for performance

### 2. Implementation
- Generate migration scripts
- Create models and relationships
- Set up indexes and constraints
- Implement data validation

## Database Schema

### Core Tables

```sql
-- Users Table
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Projects Table
CREATE TABLE projects (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    owner_id INTEGER REFERENCES users(id),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## LLM Integration Points

### Schema Design
1. **Initial Design**
   - Generate base schema
   - Define relationships
   - Set constraints
   - Plan indexes

2. **Optimization**
   - Performance tuning
   - Query optimization
   - Index strategy
   - Data partitioning

### Implementation
1. **Code Generation**
   - Migration scripts
   - Model definitions
   - Query builders
   - Data access layer

2. **Testing**
   - Schema validation
   - Performance testing
   - Data integrity tests
   - Migration tests

## Best Practices

### Database Design
1. **Normalization**
   - Follow 3NF
   - Avoid redundancy
   - Maintain integrity
   - Plan for growth

2. **Performance**
   - Index strategy
   - Query optimization
   - Connection pooling
   - Caching strategy

3. **Security**
   - Access control
   - Data encryption
   - Audit logging
   - Backup strategy

### LLM-Assisted Development
1. **Schema Design**
   - Use clear prompts
   - Review generated schema
   - Validate relationships
   - Test performance

2. **Implementation**
   - Generate migrations
   - Create models
   - Write tests
   - Document changes

3. **Maintenance**
   - Monitor performance
   - Update indexes
   - Optimize queries
   - Backup regularly

## Migration Strategy

### Version Control
1. **Schema Changes**
   - Track migrations
   - Version control
   - Rollback plan
   - Testing strategy

2. **Data Migration**
   - Backup strategy
   - Data validation
   - Performance impact
   - Rollback plan

## Monitoring and Maintenance

### Performance Monitoring
1. **Metrics**
   - Query performance
   - Connection usage
   - Index usage
   - Storage usage

2. **Optimization**
   - Regular maintenance
   - Index updates
   - Query optimization
   - Storage management

### Backup and Recovery
1. **Backup Strategy**
   - Regular backups
   - Point-in-time recovery
   - Disaster recovery
   - Testing strategy

2. **Recovery Plan**
   - Recovery procedures
   - Testing schedule
   - Documentation
   - Team training

---

```markdown
<!-- project-docs/db_schema.md -->

# Database Schema

## Overview

We're using PostgreSQL with SQLModel. All timestamps use UTC.

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

