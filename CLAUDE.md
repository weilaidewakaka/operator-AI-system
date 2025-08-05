# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an AI-powered development framework that implements a multi-agent system for software project management and development. The system follows a hierarchical agent architecture where a human operator issues commands to a Task Orchestration Agent (TOA), which then coordinates specialized agents to execute specific tasks.

## Core Architecture

### Agent Hierarchy
- **Human Operator**: Defines tasks, provides constraints, and gives reference materials
- **TOA (Task Orchestration Agent)**: Central coordinator that parses human instructions and delegates tasks to specialized agents
- **Specialized Agents**: Domain experts that execute specific tasks:
  - `ArchitectAgent`: Maintains technical architecture and design documents
  - `ProductManagerAgent`: Manages product requirements and UX design
  - `BackendEngineerAgent`: Implements server-side functionality
  - `FrontendEngineerAgent`: Implements client-side functionality  
  - `QAAgent`: Creates and executes test cases
  - `ProjectAdminAgent`: Maintains project documentation and workflows

### Document Structure
```
core_documents/
├── library/
│   ├── prd.md              # Product requirements (human-created)
│   ├── structure.md        # Technical architecture (human-created)
│   ├── uiux.md            # UI/UX design (human-created)
│   ├── service.md         # API definitions (agent-maintained)
│   ├── database.md        # Database schema (agent-maintained)
│   ├── workflow.md        # Business processes (agent-maintained)
│   └── develop_plan/      # Version development plans (agent-maintained)
├── agents/                # Agent definitions and capabilities
├── docs_index.md         # Project documentation map
├── project_rules.md      # Coding standards and project rules
└── memory.md            # Project knowledge base
```

## Agent Responsibilities Matrix

| Document/Directory | Maintainer Agent | Key Responsibilities |
|-------------------|------------------|---------------------|
| `prd.md` | ProductManagerAgent | User stories and product requirements |
| `uiux.md` | ProductManagerAgent | UI/UX design and interaction flows |
| `structure.md` | ArchitectAgent | High-level technical architecture |
| `database.md` | ArchitectAgent | Database schema and relationships |
| `service.md` | ArchitectAgent | API endpoint definitions |
| `workflow.md` | ArchitectAgent | Business process flows |
| `develop_plan/` | ArchitectAgent | Version development planning |
| `frontend/` | FrontendEngineerAgent | All frontend code |
| `backend/` | BackendEngineerAgent | All backend code |
| `test_instances/` | QAAgent | Test cases and reports |
| `project_rules.md` | ProjectAdminAgent | Project standards and Git workflows |
| `docs_index.md` | ProjectAdminAgent | Documentation index and summaries |
| `history_record/` | ProjectAdminAgent | Change history records |
| `memory.md` | ProjectAdminAgent | Project knowledge and learnings |

## Core Working Principles

1. **Human-in-the-Loop**: All tasks must be initiated by human operators; agents never self-initiate
2. **State-Aware**: Agents must read current project state before executing tasks
3. **Dependency-Driven**: Tasks must respect dependencies (e.g., architecture before implementation)
4. **Stateless**: Agents store no persistent knowledge; all state is in documents

## Available Workflows

The TOA supports these predefined workflows:
- `PLAN_VERSION_WORKFLOW`: Create version development plans
- `PLAN_FEATURE_WORKFLOW`: Break down feature development tasks
- `DEVELOP_FEATURE_WORKFLOW`: Implement new features end-to-end
- `BUILD_TESTS_WORKFLOW`: Create comprehensive test suites
- `OPTIMIZE_UX_WORKFLOW`: Improve user experience
- `CODE_AUDIT_WORKFLOW`: Review code compliance
- `EXPLAIN_FEATURE_WORKFLOW`: Document feature implementations
- `REFACTOR_CODE_WORKFLOW`: Restructure existing code

## Task Execution Pattern

1. **TOA receives human instruction**
2. **TOA builds cognition** by reading `docs_index.md` and agent definitions
3. **TOA parses instruction** into structured intent and entities
4. **TOA selects workflow** and generates detailed execution plan
5. **TOA reports plan** to human and waits for approval
6. **TOA executes plan** by delegating to specialized agents in dependency order
7. **TOA provides summary** report to human upon completion

## Key Files to Understand

- `core_documents/agents/TOA.md`: Complete TOA agent specification
- `核心思想2.md`: Core architectural philosophy and design decisions
- `core_documents/agents/agent_statement.md`: Agent behavioral guidelines
- Agent definition files in `core_documents/agents/`: Individual agent specifications

## Development Guidelines

When working with this codebase, always:
1. Understand the agent hierarchy and delegation patterns
2. Respect document ownership and maintenance responsibilities  
3. Follow the human-initiated, agent-executed workflow model
4. Maintain clear separation between planning (architecture) and execution (engineering) phases
5. Update relevant documentation when making changes to agent capabilities or workflows