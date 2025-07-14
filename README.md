# Context Engineering Template with MCP Integration

A comprehensive template for getting started with Context Engineering - the discipline of engineering context for AI coding assistants using Model Context Protocol (MCP) tools for enhanced research, reasoning, and validation.

> **Context Engineering is 10x better than prompt engineering and 100x better than vibe coding.**
> **MCP tools make Context Engineering 10x more powerful with real-time research and validation.**

## 🔗 Links & Resources

- **📺 YouTube Channel**: [Income Stream Surfers](https://www.youtube.com/c/incomestreamsurfers) - Learn advanced AI automation techniques
- **🏫 AI Automation School**: [Skool Community](https://www.skool.com/iss-ai-automation-school-6342/about) - Join our AI automation community
- **🌐 SEO Grove**: [Live Website](https://seogrove.ai/) - See advanced AI automation in action (built with different methods)

## 🚀 Quick Start

**For full setup with automatic documentation hooks:** See [SETUP.md](SETUP.md)

**For basic template usage:**

```bash
# 1. Clone this template
git clone https://github.com/IncomeStreamSurfer/context-engineering-intro.git
cd context-engineering-intro

# 2. Set up your project rules (optional - template provided)
# Edit CLAUDE.md to add your project-specific guidelines

# 3. Add examples (highly recommended)
# Place relevant code examples in the examples/ folder

# 4. Create your initial feature request
# Edit INITIAL.md with your feature requirements

# 5. Generate a comprehensive PRP (Product Requirements Prompt)
# In Claude Code, run:
/generate-prp INITIAL.md

# 6. Execute the PRP to implement your feature
# In Claude Code, run:
/execute-prp PRPs/your-feature-name.md
```

## 📚 Table of Contents

- [What is Context Engineering?](#what-is-context-engineering)
- [MCP Tool Integration](#mcp-tool-integration)
- [Template Structure](#template-structure)
- [Step-by-Step Guide](#step-by-step-guide)
- [Writing Effective INITIAL.md Files](#writing-effective-initialmd-files)
- [The PRP Workflow](#the-prp-workflow)
- [Using Examples Effectively](#using-examples-effectively)
- [Best Practices](#best-practices)
- [Governance & Quality Standards](#governance--quality-standards)

## What is Context Engineering?

Context Engineering represents a paradigm shift from traditional prompt engineering:

### Prompt Engineering vs Context Engineering

**Prompt Engineering:**
- Focuses on clever wording and specific phrasing
- Limited to how you phrase a task
- Like giving someone a sticky note

**Context Engineering:**
- A complete system for providing comprehensive context
- Includes documentation, examples, rules, patterns, and validation
- Like writing a full screenplay with all the details

### Why Context Engineering Matters

1. **Reduces AI Failures**: Most agent failures aren't model failures - they're context failures
2. **Ensures Consistency**: AI follows your project patterns and conventions
3. **Enables Complex Features**: AI can handle multi-step implementations with proper context
4. **Self-Correcting**: Validation loops allow AI to fix its own mistakes
5. **Real-Time Accuracy**: MCP tools provide up-to-date information, not outdated training data
6. **Verifiable Sources**: Every decision backed by citations and current documentation

## MCP Tool Integration

This template now includes full Model Context Protocol (MCP) tool integration for enhanced capabilities:

### Available MCP Tools

| Tool | Purpose | When to Use |
|------|---------|-------------|
| **Context7** | Library documentation | Getting accurate, versioned API docs |
| **Perplexity** | AI-powered research | Understanding concepts, best practices |
| **Brave Search** | Web search | Finding examples, current information |
| **Sequential Thinking** | Complex reasoning | Breaking down multi-step problems |
| **Playwright MCP** | Web testing | Automated browser testing & validation |

### MCP Research Workflow

1. **Identify Information Needs** → What do you need to know?
2. **Select Appropriate Tools** → Which MCP tool fits best?
3. **Parallel Research** → Use multiple tools simultaneously
4. **Document Findings** → Store in `/research/[topic]/`
5. **Cite Sources** → Include URLs and dates
6. **Apply Knowledge** → Use in implementation

## Template Structure

```
context-engineering-intro/
├── .claude/
│   ├── project/              # Project-specific context
│   ├── commands/
│   │   ├── generate-prp.md   # Generates PRPs with MCP research
│   │   └── execute-prp.md    # Executes PRPs with validation
│   └── settings.local.json   # Claude Code permissions
├── docs/                     # Documentation
│   ├── decisions/           # Architecture decision records
│   ├── specs/              # Feature specifications
│   └── capability-matrix.md # Feature inventory
├── research/                # MCP tool research outputs
│   └── [topic]/            # Organized by research topic
├── PRPs/
│   ├── templates/
│   │   └── prp_base.md     # Base template for PRPs
│   └── EXAMPLE_multi_agent_prp.md  # Example PRP
├── examples/                # Your code examples (critical!)
├── tests/                   # Test organization
│   └── e2e/                # Playwright e2e tests
├── CLAUDE.md               # Global rules with MCP integration
├── PLANNING.md             # Architecture & governance
├── TASK.md                 # Task tracking
├── research-log.md         # Research history
└── README.md               # This file
```

## Step-by-Step Guide

### 1. Set Up Global Rules (CLAUDE.md)

The `CLAUDE.md` file contains project-wide rules that the AI assistant will follow in every conversation. The template includes:

- **Project awareness**: Reading planning docs, checking tasks
- **Code structure**: File size limits, module organization
- **Testing requirements**: Unit test patterns, coverage expectations
- **Style conventions**: Language preferences, formatting rules
- **Documentation standards**: Docstring formats, commenting practices

**You can use the provided template as-is or customize it for your project.**

### 2. Create Your Initial Feature Request

Edit `INITIAL.md` to describe what you want to build:

```markdown
## FEATURE:
[Describe what you want to build - be specific about functionality and requirements]

## EXAMPLES:
[List any example files in the examples/ folder and explain how they should be used]

## DOCUMENTATION:
[Include links to relevant documentation, APIs, or MCP server resources]

## OTHER CONSIDERATIONS:
[Mention any gotchas, specific requirements, or things AI assistants commonly miss]
```

**See `INITIAL_EXAMPLE.md` for a complete example.**

### 3. Generate the PRP

PRPs (Product Requirements Prompts) are comprehensive implementation blueprints that include:

- Complete context and documentation
- Implementation steps with validation
- Error handling patterns
- Test requirements

They are similar to PRDs (Product Requirements Documents) but are crafted more specifically to instruct an AI coding assistant.

Run in Claude Code:
```bash
/generate-prp INITIAL.md
```

**Note:** The slash commands are custom commands defined in `.claude/commands/`. You can view their implementation:
- `.claude/commands/generate-prp.md` - See how it researches and creates PRPs
- `.claude/commands/execute-prp.md` - See how it implements features from PRPs

The `$ARGUMENTS` variable in these commands receives whatever you pass after the command name (e.g., `INITIAL.md` or `PRPs/your-feature.md`).

This command will:
1. Read your feature request
2. Research the codebase for patterns
3. Search for relevant documentation
4. Create a comprehensive PRP in `PRPs/your-feature-name.md`

### 4. Execute the PRP

Once generated, execute the PRP to implement your feature:

```bash
/execute-prp PRPs/your-feature-name.md
```

The AI coding assistant will:
1. Read all context from the PRP
2. Create a detailed implementation plan
3. Execute each step with validation
4. Run tests and fix any issues
5. Ensure all success criteria are met

## Writing Effective INITIAL.md Files

### Key Sections Explained

**FEATURE**: Be specific and comprehensive
- ❌ "Build a web scraper"
- ✅ "Build an async web scraper using BeautifulSoup that extracts product data from e-commerce sites, handles rate limiting, and stores results in PostgreSQL"

**EXAMPLES**: Leverage the examples/ folder
- Place relevant code patterns in `examples/`
- Reference specific files and patterns to follow
- Explain what aspects should be mimicked

**DOCUMENTATION**: Include all relevant resources
- API documentation URLs
- Library guides
- MCP server documentation
- Database schemas

**OTHER CONSIDERATIONS**: Capture important details
- Authentication requirements
- Rate limits or quotas
- Common pitfalls
- Performance requirements

## The PRP Workflow

### How /generate-prp Works

The command follows this process:

1. **Research Phase**
   - Analyzes your codebase for patterns
   - Searches for similar implementations
   - Identifies conventions to follow

2. **Documentation Gathering**
   - Fetches relevant API docs
   - Includes library documentation
   - Adds gotchas and quirks

3. **Blueprint Creation**
   - Creates step-by-step implementation plan
   - Includes validation gates
   - Adds test requirements

4. **Quality Check**
   - Scores confidence level (1-10)
   - Ensures all context is included

### How /execute-prp Works

1. **Load Context**: Reads the entire PRP
2. **Plan**: Creates detailed task list using TodoWrite
3. **Execute**: Implements each component
4. **Validate**: Runs tests and linting
5. **Iterate**: Fixes any issues found
6. **Complete**: Ensures all requirements met

See `PRPs/EXAMPLE_multi_agent_prp.md` for a complete example of what gets generated.

## Using Examples Effectively

The `examples/` folder is **critical** for success. AI coding assistants perform much better when they can see patterns to follow.

### What to Include in Examples

1. **Code Structure Patterns**
   - How you organize modules
   - Import conventions
   - Class/function patterns

2. **Testing Patterns**
   - Test file structure
   - Mocking approaches
   - Assertion styles

3. **Integration Patterns**
   - API client implementations
   - Database connections
   - Authentication flows

4. **CLI Patterns**
   - Argument parsing
   - Output formatting
   - Error handling

### Example Structure

```
examples/
├── README.md           # Explains what each example demonstrates
├── cli.py             # CLI implementation pattern
├── agent/             # Agent architecture patterns
│   ├── agent.py      # Agent creation pattern
│   ├── tools.py      # Tool implementation pattern
│   └── providers.py  # Multi-provider pattern
└── tests/            # Testing patterns
    ├── test_agent.py # Unit test patterns
    └── conftest.py   # Pytest configuration
```

## Best Practices

### 1. Be Explicit in INITIAL.md
- Don't assume the AI knows your preferences
- Include specific requirements and constraints
- Reference examples liberally

### 2. Provide Comprehensive Examples
- More examples = better implementations
- Show both what to do AND what not to do
- Include error handling patterns

### 3. Use Validation Gates
- PRPs include test commands that must pass
- AI will iterate until all validations succeed
- This ensures working code on first try

### 4. Leverage Documentation
- Include official API docs
- Add MCP server resources
- Reference specific documentation sections

### 5. Customize CLAUDE.md
- Add your conventions
- Include project-specific rules
- Define coding standards

## 🎯 Advanced PRP Method - Multi-Agent Research Approach

This template demonstrates an advanced PRP creation method using multiple parallel research agents for comprehensive documentation gathering.

### See Advanced AI Automation Examples
- **SEO Grove**: https://seogrove.ai/ - Example of advanced AI automation (built with different methods)
- **YouTube Channel**: https://www.youtube.com/c/incomestreamsurfers - Learn more about AI automation methodologies
- **AI Automation School**: https://www.skool.com/iss-ai-automation-school-6342/about - Join our community

### Advanced PRP Creation Process

#### Prompt 1: Initialize Research Framework
```
read my incredibly specific instructions about how to create a prp document then summarise them, also store how to do a jina scrapein order to create a llm.txt in your memory

If a page 404s or does not scrape properly, scrape it again

Do not use Jina to scrape CSS of the design site.

All SEPARATE pages must be stored in /research/[technology]/ directories with individual .md files.

curl
  "https://r.jina.ai/https://platform.openai.com/docs/" \
    -H "Authorization: Bearer jina_033257e7cdf14fd3b948578e2d34986bNtfCCkjHt7_j1Bkp5Kx521rDs2Eb"
```

#### Prompt 2: Generate PRP with Parallel Research
```
/generate-prp initial.md
```

**Wait until it gets to the research phase, then press escape and say:**

```
can you spin up multiple research agents and do this all at the same time
```

This approach enables:
- **Parallel Documentation Scraping**: 6+ agents simultaneously research different technologies
- **Comprehensive Coverage**: 30-100+ pages of official documentation scraped and organized
- **Technology-Specific Organization**: Each technology gets its own `/research/[tech]/` directory
- **Production-Ready PRPs**: Complete implementation blueprints with real-world examples

### Research Directory Structure
```
research/
├── pydantic-ai/      # 22+ documentation pages
├── openai/           # 20+ API documentation pages  
├── anthropic/        # 18+ Claude documentation pages
├── jina/             # 12+ scraping API pages
├── shopify/          # 18+ GraphQL/REST API pages
└── seo-apis/         # 24+ Search Console/Ahrefs pages
```

This multi-agent research approach results in PRPs with 9/10 confidence scores for one-pass implementation success.

## Governance & Quality Standards

### Core Principles
- **KISS** – Keep it simple, avoid over-engineering
- **YAGNI** – Build only what's needed today
- **Plan > Prompt** – Articulate specs before writing code
- **Fail Fast** – Surface errors immediately
- **Real Data Only** – Use MCP tools for verified information

### Quality Requirements
| Metric | Standard | Validation |
|--------|----------|------------|
| Test Coverage | ≥ 85% | pytest-cov |
| Type Coverage | 100% | mypy |
| Code Quality | Zero errors | ruff |
| Documentation | All public APIs | Auto-generated |
| Research | Cited sources | MCP tools |

### Development Workflow
1. **Research Phase** → Use MCP tools comprehensively
2. **Planning Phase** → Create detailed task lists
3. **Implementation** → TDD with continuous validation
4. **Testing Phase** → Unit → Integration → E2E (Playwright)
5. **Documentation** → Update as you go
6. **Git Checkpoint** → After each validated section

### Key Files
- **CLAUDE.md** - Global AI rules and MCP tool instructions
- **PLANNING.md** - Architecture and detailed governance
- **TASK.md** - Track all work with MCP tool usage
- **research-log.md** - Document all research queries

## Resources

- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code)
- [Context Engineering Best Practices](https://www.philschmid.de/context-engineering)
- [SEO Grove - Live Implementation](https://seogrove.ai/)
- [Income Stream Surfers - YouTube Channel](https://www.youtube.com/c/incomestreamsurfers)