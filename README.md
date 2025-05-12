# Project Template

This repository serves as a template for creating new projects with a well-defined structure and documentation. It includes an example project setup that demonstrates how to organize and document your application development process.

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
├── tests/               # Test files directory
└── requirements.txt     # Project dependencies
```

## How to Use This Template

1. Clone this repository to start a new project
2. Review and modify the following files to match your project requirements:
   - `prd.md`: Update with your project's specific requirements
   - `project-docs/*.md`: Customize each document to reflect your project's needs
3. The `.cursor` directory contains rules and configurations for the development environment

## Documentation

The template includes comprehensive documentation to guide your project development:

- **PRD (Product Requirements Document)**: Define your project's goals, features, and requirements
- **Project Documentation**:
  - Application Flow: Document your application's architecture and user flows
  - Database Schema: Define your data models and relationships
  - Implementation Plan: Break down the development process into manageable steps
  - Tech Stack: Specify the technologies and tools you'll use

## Getting Started

1. Clone this repository
2. Review the example project documentation in `prd.md` and `project-docs/`
3. Modify the documentation to match your project requirements
4. Start implementing your project following the structure and guidelines provided

## Cursor Rules

This template includes Cursor rules in the `.cursor` directory that help maintain consistent code quality and project structure. To activate these rules:

1. Make sure you have Cursor IDE installed
2. The rules will be automatically detected when you open the project in Cursor
3. The rules will help guide the development process and maintain consistency with the project's structure
4. You can modify the rules in the `.cursor` directory to match your specific project requirements

## Note

This template is designed to be a starting point for new projects. Feel free to modify the structure and documentation to better suit your specific needs while maintaining the organized approach to project development.
