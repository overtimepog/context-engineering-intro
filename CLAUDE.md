# Context Engineering Project Guidelines & MCP Integration
**Version:** 2025-07-14  
**Mandate:** Define operating principles for AI instances using this context engineering starter template.

## Table of Contents

1. [Core Principles](#core-principles)
2. [Sequential Thinking & Planning](#sequential-thinking--planning)
3. [MCP Tool Integration](#mcp-tool-integration)
4. [Project Awareness & Research](#project-awareness--research)
5. [Code Structure & Organization](#code-structure--organization)
6. [Testing & Quality Assurance](#testing--quality-assurance)
7. [Documentation & Knowledge Management](#documentation--knowledge-management)
8. [Task Management](#task-management)
9. [Environment & Container Management](#environment--container-management)
10. [Security & Compliance](#security--compliance)

---

## Core Principles

* **KISS** – Keep it simple, avoid over-engineering
* **YAGNI** – Build only what's needed today
* **SOLID** – Adhere to SOLID design principles
* **Plan > Prompt** – Articulate specs and plans *before* writing code
* **Fail Fast** – Surface rich errors immediately; never silently retry
* **Real Data Only** – Use validated real data from MCP tools and verified sources
* **Observability-First** – Embed logging and tracing from the start

---

## Sequential Thinking & Planning

### Chain-of-Thought Protocol

* **Structured Reasoning:** Decompose every non-trivial goal into explicit, validated steps
* **Extended Thinking Gating:** Before implementation, *stop and plan* using graduated cues:
  - `think` < `think hard` < `think harder` < `ultrathink` (reserve for complex work)
  - Use `mcp__sequential-thinking__sequentialthinking` for complex problem decomposition
  - Execute only after the plan receives user or orchestrator approval

### Task Decomposition with TodoWrite

* **Use TodoWrite proactively for:**
  - Complex multi-step tasks (3+ steps)
  - Non-trivial implementations requiring planning
  - Tracking progress across MCP tool usage
  - Demonstrating thoroughness to users

### Multi-Phase Implementation

1. **Research → Plan:** Use MCP tools to gather context → Create task list
2. **Plan → Refine:** Augment with edge-cases, error handling, performance
3. **Implement → Validate:** Execute with continuous testing and validation
4. **Document → Checkpoint:** Update docs and create git checkpoints

---

## MCP Tool Integration

### Available MCP Tools

| Tool | Purpose | Usage Pattern |
|------|---------|---------------|
| **mcp__Context7__resolve-library-id** | Resolve library names to IDs | Always use before get-library-docs |
| **mcp__Context7__get-library-docs** | Get up-to-date library docs | Use for external library documentation |
| **mcp__perplexity-ask__perplexity_ask** | AI-powered research | Use for fact verification and complex queries |
| **mcp__brave-search__brave_web_search** | Privacy-first web search | Use for current events and general research |
| **mcp__sequential-thinking__sequentialthinking** | Complex problem solving | Use for multi-step reasoning |
| **Playwright MCP** | Web testing & automation | Use for e2e testing and web validation |

### Research Workflow

1. **Unknown Concepts**: Start with `mcp__perplexity-ask__perplexity_ask` for overview
2. **Current Information**: Use `mcp__brave-search__brave_web_search` for latest updates
3. **Library Documentation**: 
   - First: `mcp__Context7__resolve-library-id` to get library ID
   - Then: `mcp__Context7__get-library-docs` with the resolved ID
4. **Complex Problems**: Use `mcp__sequential-thinking__sequentialthinking` to break down
5. **Web Testing**: Configure and use Playwright MCP for automated testing

### MCP Tool Best Practices

* **Parallel Research**: Invoke multiple MCP tools simultaneously for efficiency
* **Citation Requirements**: Always include source URLs and retrieval dates
* **Version Awareness**: Note library versions when using Context7
* **No Hallucination Policy**: Every technical detail must be verified through MCP tools
* **Research Volume**: Conduct comprehensive research (30-100 sources for new features)

---

## Project Awareness & Research

### Initial Setup
- **Always read `PLANNING.md`** at conversation start for architecture understanding
- **Check `TASK.md`** before starting new tasks
- **Review `research-log.md`** for past research context

### Documentation Sources
- **MCP Tools First**: Use MCP tools for all external documentation needs
- **Official Sources Only**: Stick to official documentation pages
- **Research Organization**: Store all research in `/research/[topic]/` directories
- **Citation Format**: Include source, date, and tool used for each finding

### Research Process
1. Use MCP tools to gather documentation
2. Create comprehensive notes in `/research/[topic]/[source].md`
3. Reference research files in implementations
4. Update `research-log.md` with queries and findings

---

## Code Structure & Organization

### Directory Layout
```
context-engineering-intro/
├── .claude/
│   ├── project/         # Project-specific AI context
│   ├── commands/        # Custom Claude commands
│   └── settings.local.json
├── src/                 # Source code (domain-driven structure)
├── tests/              # Test files mirroring src/
│   └── e2e/           # Playwright end-to-end tests
├── docs/               # Documentation
│   ├── decisions/      # ADR files
│   └── specs/         # Feature specifications
├── research/           # MCP tool research outputs
├── PRPs/              # Product Requirement Prompts
├── config/            # Configuration files
└── scripts/           # Build and utility scripts
```

### File Organization Rules
- **Max file size**: 500 lines (excluding comments/blanks)
- **Single responsibility**: Each file has one clear purpose
- **Domain-driven**: Group by feature/domain, not technical layer
- **Naming conventions**: 
  - Python: `snake_case`
  - JavaScript/TypeScript: `camelCase`
  - Classes: `PascalCase`

### Module Structure
For agents/features:
- `agent.py` - Main agent definition and execution
- `tools.py` - Tool functions used by the agent
- `prompts.py` - System prompts
- `__init__.py` - Public API surface

---

## Testing & Quality Assurance

### Testing Requirements
- **Coverage**: ≥ 85% test coverage requirement
- **Test Types**: Unit, integration, regression, and e2e tests
- **Test Organization**: Mirror source structure in `/tests`
- **Playwright Tests**: Store in `tests/e2e/` with `[feature].spec.ts` naming

### Playwright MCP Integration
```yaml
# Configure Playwright MCP for web testing
playwright:
  command: "npx"
  args: ["@playwright/mcp@latest", "--headless"]
  capabilities:
    - browser_snapshot
    - browser_click
    - browser_navigate
    - browser_take_screenshot
    - browser_generate_playwright_test
```

### Test-Driven Development
1. **Write tests first** using existing patterns
2. **Run tests** after each implementation section
3. **Pass → Git checkpoint** → Next section
4. **Use Playwright MCP** for web UI validation

### Validation Gates
```bash
# Python projects
ruff check --fix && mypy .
pytest tests/ -v --cov=src --cov-report=term-missing

# Web projects - use Playwright MCP
# The AI will use browser_generate_playwright_test tool
# Then execute the generated tests
```

---

## Documentation & Knowledge Management

### Documentation Structure
```
docs/
├── decisions/          # ADR-###-[title].md files
├── specs/             # Feature specifications
├── api/               # API documentation
└── capability-matrix.md  # What the project can/cannot do
```

### Research Documentation
- **Location**: `/research/[topic]/[source].md`
- **Format**: Include tool used, date, source URL, key findings
- **Research Log**: Update `research-log.md` with all queries

### Documentation Requirements
- **No README > 500 lines**: Split into focused documents
- **API Docs**: Auto-generate from code when possible
- **Decision Records**: Document all architectural decisions
- **Capability Matrix**: Maintain current feature inventory

---

## Task Management

### Using TASK.md
- **Check before starting**: Look for existing tasks
- **Add new tasks**: Include description and date
- **Mark completed**: Update immediately after completion
- **Discovered work**: Add under "Discovered During Work" section

### Task Documentation Pattern
```markdown
## Task-001: Implement Feature X
**Date**: 2025-07-14
**Status**: In Progress
**MCP Tools Used**: Context7, Perplexity
**Research**: /research/feature-x/
**Implementation**: /src/features/feature-x/
```

---

## Environment & Container Management

### Docker/Container Usage
- **All operations in containers**: Use Docker/Dagger for isolation
- **Environment specs**: Single source of truth (requirements.txt, package.json, etc.)
- **Python projects**: Use venv/virtualenv, never global packages
- **Container testing**: Run all tests inside containers for parity

### Playwright MCP Container Config
```yaml
# For isolated browser testing
playwright:
  command: "docker"
  args: ["run", "-i", "--rm", "--init", "mcr.microsoft.com/playwright/mcp"]
```

---

## Security & Compliance

### Security Rules
- **No hardcoded secrets**: Use environment variables
- **Input validation**: Sanitize all external data
- **Least privilege**: Minimal permissions for all operations
- **Audit trails**: Log all significant actions

### MCP Tool Security
- **API Keys**: Store in `.env` files (never commit)
- **Rate Limiting**: Respect all API limits
- **Data Privacy**: Be mindful of data sent to external services

---

## Style & Conventions

### Python Development
- **Follow PEP8** with type hints
- **Format with `black`**
- **Use `pydantic` for validation**
- **Docstrings**: Google style for all functions
- **Environment**: Use `python-dotenv` for config

### Import Order
1. Standard library imports
2. Third-party imports  
3. Local application imports
4. Relative imports (sparingly)

### Error Handling
- **Explicit errors**: Never suppress exceptions
- **Defensive programming**: Use assertions and fallbacks
- **Actionable messages**: Include context and recovery steps

---

## AI Behavior Rules

### MCP Tool Usage
- **Research unknown concepts** immediately with Perplexity/Brave
- **Verify all technical details** through MCP tools
- **Document sources** with citations and dates
- **Use sequential thinking** for complex problems
- **Test with Playwright MCP** for web features

### Context Management
- **Track token usage** continuously
- **Compact at 80%** of context window
- **Prioritize relevant** information
- **Use research files** to offload context

### Implementation Guidelines
- **Never assume**: Always verify with MCP tools
- **Never hallucinate**: Only use verified information
- **Always validate**: Run tests and fix issues
- **Document everything**: Update docs as you go

---

## Quick Reference: MCP Tool Commands

```python
# Research with Perplexity
mcp__perplexity-ask__perplexity_ask(messages=[...])

# Web search with Brave
mcp__brave-search__brave_web_search(query="...", count=10)

# Get library documentation
# First resolve the library ID
mcp__Context7__resolve-library-id(libraryName="playwright")
# Then get docs with resolved ID
mcp__Context7__get-library-docs(context7CompatibleLibraryID="/microsoft/playwright")

# Complex reasoning
mcp__sequential-thinking__sequentialthinking(
    thought="...",
    thoughtNumber=1,
    totalThoughts=5,
    nextThoughtNeeded=True
)

# Playwright testing (configured via MCP server)
# Use browser_* tools for web automation
```

Remember: **Always use MCP tools for research, never rely on training data alone!**