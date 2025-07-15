# System-Wide Testing with Multi-Agent Analysis

Comprehensively test the entire codebase by first understanding the system, then deploying specialized testing agents.

## Process Overview

### 1. Deep Codebase Analysis & Understanding

#### 1.1 Comprehensive Project Discovery
- **Project Documentation**: Read ALL existing documentation files:
  - `README.md`, `PLANNING.md`, `CLAUDE.md`, `initial.md`
  - Complete `/docs/` directory analysis
  - `TASK.md`, `QUICKSTART.md`, `SETUP.md`
  - Any specifications, design documents, or architecture files
- **Research Repository**: Examine existing research thoroughly:
  - Complete `/research/` directory analysis
  - `research-log.md` for research history
  - All feature-specific research subdirectories
  - Past MCP research findings and context
- **Configuration Analysis**: Check all configuration files:
  - `package.json`, `requirements.txt`, `.env.example`
  - Docker configurations, deployment configs
  - CI/CD pipeline configurations
  - Database configurations and connection strings
- **Git History**: Review recent commits to understand:
  - Current development trajectory
  - Recent feature implementations
  - Code quality and testing patterns
  - Active development areas

#### 1.2 Complete System Inventory
```python
# Use TodoWrite to track analysis progress
TodoWrite([
    {"content": "Analyze project structure and dependencies", "status": "in_progress"},
    {"content": "Inventory all features and components", "status": "pending"},
    {"content": "Map system architecture and data flow", "status": "pending"},
    {"content": "Identify all testing entry points", "status": "pending"}
])
```

#### 1.3 Comprehensive Feature and Component Discovery
- **Use Glob** to find all source files: `**/*.py`, `**/*.js`, `**/*.tsx`, etc.
- **Use Grep** to identify and catalog:
  - **API endpoints and routes**: Complete API surface area
  - **Database models and schemas**: All data structures and relationships
  - **React components and pages**: UI component hierarchy
  - **Service classes and utilities**: Business logic and helpers
  - **Configuration and environment variables**: System configuration
  - **Existing tests and test patterns**: Current testing coverage and approaches
  - **TODO comments and incomplete features**: Work in progress
  - **Error handling patterns**: How errors are currently managed
  - **Authentication and authorization**: Security implementation
  - **External integrations**: Third-party services and APIs

#### 1.4 Technology Stack Analysis
- **Framework Detection**: Identify React, Vue, Django, Flask, FastAPI, etc.
- **Database Systems**: PostgreSQL, MongoDB, SQLite, Redis, etc.
- **Build Tools**: Webpack, Vite, npm scripts, Docker, etc.
- **Testing Tools**: Jest, Pytest, Playwright, Cypress, etc.
- **Deployment**: Docker, Kubernetes, cloud platforms, etc.

#### 1.5 Complete System Architecture Mapping
- **Frontend Architecture**: Components, routing, state management, build process
- **Backend Architecture**: API structure, services, middleware, request flow
- **Database Architecture**: Tables, relationships, migrations, indexing
- **Integration Points**: External APIs, services, webhooks, message queues
- **Authentication**: Auth systems, permissions, security, session management
- **File Structure**: How code is organized and modularized
- **Data Flow**: How data moves through the system
- **Deployment Architecture**: How the system is deployed and scaled
- **Monitoring and Logging**: Existing observability and debugging tools

### 2. MCP Research Phase

#### 2.1 Technology Documentation Research
```python
# For each technology found in the codebase
mcp__Context7__resolve-library-id(libraryName="{discovered_library}")
mcp__Context7__get-library-docs(
    context7CompatibleLibraryID="/org/library",
    tokens=10000,
    topic="testing best practices"
)
```

#### 2.2 Testing Strategy Research
```python
# Research testing approaches for the discovered stack
mcp__perplexity-ask__perplexity_ask(
    messages=[{
        "role": "user",
        "content": "What are the best testing strategies for {technology_stack}? Include unit tests, integration tests, e2e tests, and performance testing approaches."
    }]
)
```

#### 2.3 Current Testing Patterns Research
```python
# Find current testing examples and patterns
mcp__brave-search__brave_web_search(
    query="{framework} {testing_framework} testing examples 2024 2025",
    count=20
)
```

### 3. Testing Strategy Development

#### 3.1 Test Plan Generation
Use `mcp__sequential-thinking__sequentialthinking` to create comprehensive test plan:
- **Unit Testing**: Individual components and functions
- **Integration Testing**: Service interactions and API endpoints
- **End-to-End Testing**: Complete user workflows
- **Performance Testing**: Load, stress, and scalability
- **Security Testing**: Authentication, authorization, data validation

#### 3.2 Test Environment Setup
- **Development Environment**: Local testing setup
- **Test Database**: Separate test data and cleanup
- **Mock Services**: External API mocking
- **Test Data**: Fixtures and seed data

### 4. Multi-Agent Testing Deployment

#### 4.1 Agent Specialization Based on System Analysis

**Service Agent**:
- Responsibilities: Start all discovered services (web server, database, cache, etc.)
- Tools: Docker, npm/pip commands, service monitoring
- Focus: System health, resource usage, service connectivity

**API Testing Agent**:
- Responsibilities: Test all discovered API endpoints
- Tools: HTTP clients, API testing frameworks
- Focus: Request/response validation, error handling, performance

**Database Agent**:
- Responsibilities: Test database operations and data integrity
- Tools: Database clients, migration tools
- Focus: CRUD operations, relationships, constraints, performance

**Web UI Agent** (if web application detected):
- Responsibilities: **YOU must directly test** all web interfaces and user interactions
- Tools: **Playwright MCP** (`browser_navigate`, `browser_click`, `browser_type`, `browser_take_screenshot`)
- Focus: UI functionality, user workflows, visual testing - never assume functionality works
- **Direct Testing Required**: YOU must interact with every discovered web page and feature

**Security Agent**:
- Responsibilities: Test authentication, authorization, and security
- Tools: Security testing tools, penetration testing
- Focus: Access control, input validation, security vulnerabilities

**Performance Agent**:
- Responsibilities: Test system performance and scalability
- Tools: Load testing tools, performance monitoring
- Focus: Response times, throughput, resource usage

#### 4.2 Agent Coordination Protocol

**Shared Communication**: `/tmp/system-test-log.md`
```markdown
[TIMESTAMP] [AGENT_ROLE] [STATUS] [MESSAGE]
2025-07-15 14:30:00 SERVICE_AGENT STARTED All services running - Web:3000, API:8000, DB:5432
2025-07-15 14:30:05 WEB_UI_AGENT TESTING Testing login workflow with Playwright MCP
2025-07-15 14:30:10 API_AGENT TESTING Testing /api/auth endpoints - 15 endpoints found
2025-07-15 14:30:15 DATABASE_AGENT TESTING Testing user table operations - 8 tables found
```

### 5. Comprehensive Testing Execution

#### 5.1 System Startup and Health Check
1. **Service Agent** starts all discovered services
2. **All agents** wait for "SYSTEM_READY" status
3. **Health checks** on all services and dependencies

#### 5.2 Parallel Testing Execution
- **API Agent**: Tests all discovered endpoints systematically
- **Web UI Agent**: **YOU must use Playwright MCP** to directly test all pages and user flows - never assume functionality works
- **Database Agent**: Tests all models, relationships, and queries
- **Security Agent**: Tests authentication and authorization
- **Performance Agent**: Runs load tests on critical paths

#### 5.3 Issue Discovery and Documentation
Each agent documents findings in `/tmp/system-test-issues.md`:
```markdown
## Issue #001
**Agent**: WEB_UI_AGENT
**Type**: UI Bug
**Component**: Login Form
**Description**: Password reset link not working
**Location**: /login page, password reset modal
**Expected**: Should send reset email and show confirmation
**Actual**: Button click shows 404 error
**Screenshot**: /tmp/login-reset-issue.png
**Priority**: High
**Status**: NEEDS_FIX
```

### 6. Fix Agent Deployment

#### 6.1 System Fix Agent
- **Specialized for system-wide issues**
- **Uses MCP tools** for comprehensive research
- **Prioritizes by impact**: Critical system issues first
- **Coordinates with testing agents** for verification

#### 6.2 Fix-Test Communication Loop
1. **Fix Agent** addresses documented issues using MCP research
2. **Relevant Testing Agent** re-tests specific issues
3. **For Web Issues**: **YOU must use Playwright MCP** to directly verify fixes - never assume they work
4. **Cross-Agent Validation**: Other agents verify no regressions
5. **Continue until all issues resolved**

### 7. System Validation and Reporting

#### 7.1 Complete System Validation
- **All agents** run full test suites
- **Integration testing** between all components
- **End-to-end workflows** - **YOU must use Playwright MCP** to directly test all user journeys
- **Performance benchmarks** established
- **Security validation** completed
- **Direct Web Testing**: YOU must verify every web feature works through direct interaction

#### 7.2 Comprehensive Test Report
Generate `/system-test-report.md`:
```markdown
# System Test Report
**Date**: {current_date}
**Duration**: {test_duration}
**System**: {discovered_system_description}

## System Analysis Summary
- **Technology Stack**: {discovered_technologies}
- **Components Found**: {component_count}
- **API Endpoints**: {endpoint_count}
- **Database Tables**: {table_count}
- **Web Pages**: {page_count}

## Test Execution Summary
- **Total Tests**: {test_count}
- **Passed**: {passed_count}
- **Failed**: {failed_count}
- **Issues Found**: {issue_count}
- **Issues Fixed**: {fixed_count}

## Agent Performance
{Performance metrics for each agent}

## Issues Summary
{Summary of all issues found and resolved}

## Performance Metrics
{Response times, throughput, resource usage}

## Security Assessment
{Security test results and recommendations}

## Recommendations
{Improvement suggestions based on findings}
```

### 8. Success Criteria

The `/test-system` command succeeds when:
1. ✅ Complete system analysis and architecture mapping
2. ✅ All components and features identified
3. ✅ Appropriate testing agents deployed
4. ✅ Playwright MCP used for all web testing
5. ✅ All issues discovered and documented
6. ✅ Fix agents resolve all critical issues
7. ✅ Complete system validation passes
8. ✅ Comprehensive test report generated

### 9. Research Documentation

Save all findings to `/research/system-testing/`:
- `complete-system-analysis.md` - Comprehensive system inventory and architecture
- `existing-research-utilized.md` - Summary of existing research that was leveraged
- `technology-research.md` - Technology documentation and testing strategies
- `test-strategy.md` - Testing approach and rationale based on discovered architecture
- `agent-reports/` - Individual agent test reports
- `performance-data/` - Performance test results
- `security-assessment.md` - Security test findings
- `integration-points.md` - Analysis of all system integration points

## Example Usage

```bash
/test-system
```

This will:
1. Analyze the entire codebase to understand the system
2. Research appropriate testing strategies
3. Deploy specialized testing agents
4. Use Playwright MCP for web testing
5. Fix all discovered issues
6. Generate comprehensive test report

## Key Features

- **Automatic System Discovery**: No manual configuration needed
- **Technology-Aware Testing**: Adapts to discovered tech stack
- **Playwright MCP Integration**: YOU must directly test all web functionality - never assume it works
- **Multi-Agent Coordination**: Parallel testing with communication
- **Issue Resolution**: Fix agents resolve problems automatically
- **Comprehensive Reporting**: Detailed analysis and recommendations
- **Direct Web Testing**: YOU must interact with and test websites yourself