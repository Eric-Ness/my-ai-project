<!-- project-docs/app_flow.md -->

# Application Flow & Wireframes

## 1. High‑Level User Journey

1. **Signup / Login**  
   - User visits `/auth/signup` or `/auth/login`  
   - User submits credentials  
   - JWT issued & stored in client

2. **Dashboard**  
   - GET `/projects` → List projects  
   - “Create New Project” button → opens project creation modal

3. **Project Workspace**  
   - Sidebar: docs, code snippets, tests  
   - Main pane: AI chat interface + code preview  
   - Top bar: “Generate Feature” dropdown

4. **Feature Generation**  
   - Developer selects “Auth Module” → AI ingests PRD & rules  
   - Agent returns code + suggested tests  
   - Inline diff view for review & commit

5. **Review & Merge**  
   - Developer clicks “Approve & Commit”  
   - POST `/projects/{id}/snippets` → saves snippet  
   - Trigger CI pipeline

---

## 2. Endpoint Wireframes

```mermaid
flowchart LR
  A[Login Page] --> B[Dashboard]
  B --> C[Project Workspace]
  C --> D[AI Chat]
  C --> E[Docs Browser]
  C --> F[Code Preview]
  C --> G[Commit History]
