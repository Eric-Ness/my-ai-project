# LLM-Assisted Project Development Template

This repository provides a structured template for LLM-assisted project development, focusing on creating comprehensive Product Requirement Documents (PRDs) and project documentation with AI assistance. It's designed to work seamlessly with LLMs and Cursor IDE to help you build your project from requirements to implementation.

## Overview

This template facilitates an interactive workflow where:
1. You work with LLMs to gather and refine project requirements
2. The template guides you through creating a complete PRD
3. Project documentation is generated with AI assistance
4. The structured codebase is ready for LLM-assisted implementation

## Project Structure

```
.
├── prd.md                 # Product Requirements Document template
├── project-docs/          # Detailed project documentation
│   ├── app_flow.md       # Application flow and architecture
│   ├── db_schema.md      # Database schema and relationships
│   ├── implementation_plan.md  # Step-by-step implementation guide
│   └── tech_stack.md     # Technology stack and dependencies
├── src/                  # Source code directory
│   ├── config/          # Configuration files
│   ├── data/           # Data models and database interactions
│   ├── services/       # Business logic and service layer
│   ├── utils/          # Utility functions and helpers
│   │   └── logger.py   # Logger module
│   └── main.py         # Application entry point
├── tests/               # Test files directory
└── requirements.txt     # Project dependencies
```

## LLM-Assisted Workflow

### 1. PRD Creation
- Start with the `prd.md` template
- Work with your LLM assistant to:
  - Define project goals and scope
  - List features and requirements
  - Specify technical constraints
  - Outline user stories and acceptance criteria

### 2. Project Documentation
Use LLM assistance to generate comprehensive documentation:
- **Application Flow**: Document architecture and user flows
- **Database Schema**: Design data models and relationships
- **Implementation Plan**: Break down development into manageable steps
- **Tech Stack**: Select appropriate technologies and tools

### 3. Implementation
Once documentation is complete:
- Use Cursor IDE with LLM assistance for code generation
- Follow the implementation plan step by step
- Leverage the structured codebase for consistent development
- Utilize the logger module for debugging and monitoring

## Getting Started

1. Clone this repository
2. Open the project in Cursor IDE
3. Start with `prd.md` and work with your LLM assistant to:
   - Fill in project requirements
   - Generate necessary documentation
   - Plan implementation steps
4. Use the generated documentation to guide LLM-assisted code development

## Cursor IDE Integration

This template is optimized for use with Cursor IDE and LLM assistance:
- The `.cursor` directory contains rules for consistent code quality
- The project structure is designed for easy LLM navigation
- Documentation is formatted for clear LLM understanding
- Code templates are ready for LLM-assisted implementation

## Logger Module

The logger module has been designed for LLM-friendly debugging and monitoring:

```python
from utils.logger import get_logger, setup_file_logging

# Set up file logging (optional)
setup_file_logging(log_dir="logs", filename="myapp.log")

# Get a logger for your module
logger = get_logger(__name__)

# Use the logger
logger.info("Application started")
logger.error("Something went wrong")
```

The logger provides color-coded output for different log levels:
- DEBUG: Dark grey
- INFO: Grey
- WARNING: Yellow
- ERROR: Red
- CRITICAL: Bold red

## Best Practices for LLM-Assisted Development

1. **Documentation First**: Complete PRD and project docs before coding
2. **Iterative Refinement**: Use LLM feedback to improve requirements
3. **Structured Development**: Follow the template structure for consistency
4. **Regular Validation**: Test LLM-generated code against requirements
5. **Version Control**: Maintain clear commit history for LLM context

## References

- [Cursor IDE Documentation](https://cursor.sh/docs)
- [LLM-Assisted Development Guide](https://www.aitidbits.ai/p/sahar-ai-coding)
- [Project Structure Best Practices](https://gist.github.com/Dowwie/151d8efea738ea486ddec9208ddb3a19)
- [Cursor Rules](https://cursor.directory/rules/python)