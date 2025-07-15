# Create Initial Project Definition

Transform natural language project description into comprehensive initial project documentation.

## Input: $ARGUMENTS

## Process Overview

### 1. Natural Language Analysis & Existing Codebase Discovery

#### 1.1 Parse Natural Language Input
- Parse the project description to extract key requirements
- Use `mcp__sequential-thinking__sequentialthinking` to break down complex ideas
- Identify core features, target users, and technical requirements

#### 1.2 Comprehensive Codebase Analysis
**First, thoroughly understand what already exists:**

- **Project Documentation**: Read all existing files:
  - `README.md`, `PLANNING.md`, `CLAUDE.md`, `initial.md` (if exists)
  - All files in `/docs/` directory
  - `TASK.md`, `QUICKSTART.md`, `SETUP.md`
  - Any existing specifications or design documents

- **Research Repository**: Examine all existing research:
  - Review `/research/` directory completely
  - Read `research-log.md` for past research context
  - Check all subdirectories for existing feature research
  - Identify what's already been researched vs what needs new research

- **Current Codebase Inventory**: Use `LS`, `Glob`, and `Grep` to discover:
  - **Directory Structure**: Complete project layout and organization
  - **Source Code**: All existing source files and their functionality
  - **Configuration**: All config files, environment setups, dependencies
  - **Database**: Existing schemas, models, migrations
  - **Tests**: Current test files and testing approaches
  - **Scripts**: Build scripts, deployment scripts, utilities
  - **Assets**: Static files, images, documentation assets

- **Implementation Status Assessment**:
  - What features are already implemented (partial or complete)?
  - What's in progress vs what's planned?
  - Are there TODO comments, stub functions, or placeholder code?
  - What APIs, services, or integrations already exist?
  - Review recent git commits to understand development trajectory

- **Gap Analysis**:
  - What does the natural language request ask for that already exists?
  - What would be building on existing functionality vs starting fresh?
  - Are there conflicts between the request and existing architecture?
  - What existing code, research, or documentation can be leveraged?

### 2. Comprehensive MCP Research Phase

#### 2.1 Research Strategy Based on Existing Analysis
**Determine what research is needed based on codebase analysis:**

- **If existing research exists**: Review and validate currency of existing research
- **If partial implementation exists**: Focus research on gaps and integration points
- **If starting fresh**: Conduct comprehensive domain research
- **If extending existing**: Research compatibility and enhancement patterns

#### 2.2 Project Domain Research
```python
# Research the domain and industry
mcp__perplexity-ask__perplexity_ask(
    messages=[{
        "role": "user",
        "content": "Explain {domain} industry best practices, common architectures, and key considerations for building {project_type} applications"
    }]
)
```

#### 2.2 Technology Stack Research
```python
# Find current technology recommendations
mcp__brave-search__brave_web_search(
    query="{project_type} technology stack 2024 2025 best practices",
    count=20
)
```

#### 2.3 Library and Framework Research
```python
# For each potential technology/library
mcp__Context7__resolve-library-id(libraryName="{library}")
mcp__Context7__get-library-docs(
    context7CompatibleLibraryID="/org/library",
    tokens=10000,
    topic="getting started architecture"
)
```

#### 2.4 Architecture and Design Patterns
```python
# Research architectural patterns
mcp__perplexity-ask__perplexity_ask(
    messages=[{
        "role": "user",
        "content": "What are the best architectural patterns for {project_type}? Include microservices, database design, API patterns, and security considerations"
    }]
)
```

### 3. Project Structure Analysis

#### 3.1 Feature Breakdown
Use `mcp__sequential-thinking__sequentialthinking` to:
- Decompose project into core features
- Identify dependencies between features
- Prioritize features by importance and complexity
- Map user journeys and workflows

#### 3.2 Technical Requirements
- Define system requirements and constraints
- Identify scalability needs
- Security and compliance requirements
- Performance requirements
- Integration requirements

### 4. Technology Recommendations

#### 4.1 Stack Selection
Based on MCP research, recommend:
- **Frontend**: Framework, libraries, build tools
- **Backend**: Runtime, framework, database
- **Infrastructure**: Hosting, CI/CD, monitoring
- **Development**: Tools, testing frameworks, linting

#### 4.2 Architecture Design
- System architecture diagram (text-based)
- Data flow and component interactions
- API design patterns
- Database schema considerations

### 5. Implementation Roadmap

#### 5.1 Phase Planning
- **Phase 1**: Core functionality and MVP
- **Phase 2**: Enhanced features and integrations
- **Phase 3**: Advanced features and optimizations
- **Phase 4**: Scaling and enterprise features

#### 5.2 Development Workflow
- Git branching strategy
- Testing strategy
- Deployment pipeline
- Code review process

### 6. Generate initial.md

Create comprehensive `/initial.md` file with existing codebase integration:

```markdown
# {Project Name}

## Overview
{Generated from natural language description}

## Existing Codebase Analysis
**Analysis Date**: {current_date}
**Current Implementation Status**: {existing features and completion level}
**Existing Research**: {summary of existing research found}
**Architecture Assessment**: {current tech stack and architecture}
**Gap Analysis**: {what exists vs what's requested}

## MCP Research Summary
**Research Date**: {current_date}
**Tools Used**: Context7 ({count} queries), Perplexity ({count} queries), Brave Search ({count} queries)
**Research Files**: /research/initial-project/
**Existing Research Leveraged**: {existing research files used}

## Core Features

### Existing Features
{Document all currently implemented features}

### Requested Features
{Features from natural language request}

### Feature Integration Plan
{How new features will integrate with existing ones}

### Feature Priorities
{Priority order considering existing vs new features}

## Technical Architecture

### Current Technology Stack
- **Frontend**: {existing frontend tech and versions}
- **Backend**: {existing backend tech and versions}
- **Database**: {existing database and schema}
- **Infrastructure**: {current hosting and deployment setup}

### Recommended Technology Stack
- **Frontend**: {recommendations with versions, considering existing stack}
- **Backend**: {recommendations with versions, considering existing stack}
- **Database**: {recommendations with rationale, considering existing data}
- **Infrastructure**: {hosting and deployment recommendations, considering existing setup}

### System Architecture

#### Current Architecture
{Existing system architecture and components}

#### Proposed Architecture
{Updated architecture integrating new features}

#### Migration Strategy
{How to evolve from current to proposed architecture}

### API Design

#### Existing APIs
{Current API endpoints and structure}

#### New API Requirements
{API patterns and structure for new features}

#### API Integration Plan
{How new APIs will work with existing ones}

### Database Schema

#### Current Schema
{Existing database structure and relationships}

#### Schema Extensions
{New tables, fields, relationships needed}

#### Migration Plan
{Database migration strategy}

## Implementation Roadmap

### Phase 1: Integration & Core Features ({timeline})
{Integrate with existing system and implement core requested features}

### Phase 2: Enhancement ({timeline})
{Advanced features building on existing and new foundation}

### Phase 3: Scale ({timeline})
{Performance and scaling features leveraging existing infrastructure}

## Development Setup

### Prerequisites
{System requirements and dependencies}

### Initial Setup Commands
```bash
{Step-by-step setup commands}
```

### Development Workflow
{Git workflow, testing, deployment process}

### Web Testing Requirements
**If this is a web application, YOU must:**
- Use Playwright MCP to directly test all web functionality
- Never assume web features work - test them yourself
- Use `browser_navigate`, `browser_click`, `browser_type`, `browser_take_screenshot`
- Test all user interactions and workflows directly
- Capture screenshots for visual validation

## Research References
{Links to all research files with summaries}

### Existing Research Utilized
{List of existing research files that were relevant and used}

### New Research Conducted
{List of new research files created for this analysis}

## Next Steps
1. Review and approve this initial design
2. Validate integration plan with existing codebase
3. Set up development environment (or update existing setup)
4. Create first PRP for Phase 1 Integration & Core Features
5. Begin implementation with /execute-prp

## Validation Checklist
- [ ] Existing codebase thoroughly analyzed
- [ ] All existing features documented
- [ ] All existing research reviewed and leveraged
- [ ] Gap analysis completed (existing vs requested)
- [ ] Integration plan developed
- [ ] Technology stack researched and validated (considering existing)
- [ ] Architecture design accounts for existing system
- [ ] Implementation roadmap is realistic and integration-aware
- [ ] Development workflow defined (considering existing processes)
- [ ] Research is comprehensive (30+ sources + existing research)
```

### 7. Research Documentation

Save all analysis and research to `/research/initial-project/`:
- `codebase-analysis.md` - Complete existing codebase analysis
- `existing-research-summary.md` - Summary of existing research found
- `domain-analysis.md` - Industry and domain research
- `technology-research.md` - Tech stack comparisons (considering existing)
- `architecture-patterns.md` - Design pattern research
- `integration-strategy.md` - How to integrate with existing system
- `library-docs/` - Context7 documentation
- `examples/` - Code examples from web search

### 8. Quality Assurance

#### 8.1 Completeness Check
- [ ] Existing codebase completely analyzed
- [ ] All existing documentation and research reviewed
- [ ] All aspects of project covered (existing + new)
- [ ] Technology choices justified with research (considering existing)
- [ ] Implementation roadmap is detailed and integration-aware
- [ ] Development workflow is complete (considering existing)
- [ ] At least 30 research sources used + existing research leveraged

#### 8.2 Research Validation
- [ ] Cross-referenced multiple sources
- [ ] Current/recent information (2024-2025)
- [ ] Industry best practices included
- [ ] Scalability considerations addressed
- [ ] Security aspects covered
- [ ] Integration with existing system validated
- [ ] Existing research findings incorporated

### 9. Final Output

- Save as `/initial.md` in project root
- Update `research-log.md` with all queries
- Create `/research/initial-project/summary.md` with key findings
- Create `/research/initial-project/codebase-analysis.md` with complete existing system analysis
- Output success message with integration-aware next steps

## Success Criteria

The `/create-init` command succeeds when:
1. ✅ Existing codebase completely analyzed and documented
2. ✅ All existing documentation and research reviewed
3. ✅ Comprehensive `initial.md` file created with integration plan
4. ✅ All MCP research completed and documented
5. ✅ Technology stack validated with current documentation and existing system
6. ✅ Implementation roadmap is realistic, detailed, and integration-aware
7. ✅ Development workflow clearly defined (considering existing processes)
8. ✅ Research meets quality standards (30+ sources + existing research)

## Example Usage

```bash
/create-init I want a bitcoin trading platform with real-time charts, portfolio tracking, and automated trading strategies
```

This will generate a complete initial project definition with researched technology recommendations, architecture design, and implementation roadmap.