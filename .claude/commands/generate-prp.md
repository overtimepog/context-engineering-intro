# Create PRP with MCP Tool Integration

YOU MUST DO IN-DEPTH RESEARCH USING MCP TOOLS, FOLLOW THE <MCP RESEARCH PROCESS>

<MCP RESEARCH PROCESS>

## 1. Initial Analysis
- Use TodoWrite to create research task list
- Read the feature file ($ARGUMENTS) to understand requirements
- Use mcp__sequential-thinking__sequentialthinking for complex requirement decomposition

## 2. MCP Tool Research Phase

### 2.1 Parallel Research Execution
Execute these MCP tools SIMULTANEOUSLY for maximum efficiency:

```python
# Conceptual parallel research approach
parallel_research = [
    mcp__perplexity-ask__perplexity_ask("Best practices for {feature}"),
    mcp__brave-search__brave_web_search("{feature} implementation examples", count=20),
    mcp__Context7__resolve-library-id("{main_library}") → then get docs
]
```

### 2.2 Library Documentation
For EACH library mentioned:
1. Use `mcp__Context7__resolve-library-id(libraryName="...")` to get library ID
2. Use `mcp__Context7__get-library-docs(context7CompatibleLibraryID="...", tokens=10000)`
3. Save output to `/research/[library]/context7-docs.md`

### 2.3 Concept Research
For EACH technical concept:
1. Use `mcp__perplexity-ask__perplexity_ask` for comprehensive understanding
2. Use `mcp__brave-search__brave_web_search` for recent examples and updates
3. Cross-reference multiple sources for accuracy

### 2.4 Research Documentation
- Create `/research/[feature]/` directory
- Save each MCP tool output to separate .md files
- Include tool used, date, query, and full response
- Update `research-log.md` with all queries

## 3. Complex Problem Analysis
Use `mcp__sequential-thinking__sequentialthinking` when encountering:
- Multi-step implementation requirements
- Architecture decisions
- Complex integration patterns
- Performance optimization needs

</MCP RESEARCH PROCESS>

## Feature file: $ARGUMENTS

Generate a complete PRP for feature implementation with comprehensive MCP-powered research. Read the feature file first to understand requirements, examples, and considerations.

## Research Process

### 1. Comprehensive Codebase Analysis

**First, understand the existing codebase:**

#### 1.1 Project Structure Analysis
- Read `README.md`, `PLANNING.md`, `CLAUDE.md` for project context
- Use `LS` to examine directory structure and organization patterns
- Check `package.json`, `requirements.txt`, `Cargo.toml` for dependencies
- Review `.gitignore`, config files for project setup

#### 1.2 Implementation Status Assessment
- **Feature Inventory**: Use `Grep` to search for related functionality keywords
- **Existing Implementation Check**:
  - Does similar functionality already exist (partial or complete)?
  - Are there placeholder functions, TODO comments, or stub implementations?
  - Look for incomplete features that could be extended vs building new
  - Check for related API endpoints, database tables, or components
- **Development History**: Review recent commits to understand current development focus

#### 1.3 Code Patterns & Conventions
- Use `Grep` to find similar features/patterns in the codebase
- Use `Glob` to identify file naming conventions
- Read existing source files to understand:
  - Code style and formatting preferences
  - Error handling patterns
  - Testing approaches and frameworks
  - Import/module organization
  - Documentation standards

#### 1.4 Architecture Understanding
- Identify existing frameworks and libraries in use
- Understand data flow and component structure
- Note API patterns and interfaces
- Check for existing databases, services, or external integrations
- Review test structure and testing utilities

#### 1.5 Integration Points & Gap Analysis
- **What's Already Implemented**: Document existing functionality that relates to the new feature
- **What's Missing or Incomplete**: Identify gaps that need to be filled
- **Extension vs New Development**: Determine what can be extended vs built from scratch
- **Integration Points**: Find where the new feature should connect
- **Potential Conflicts**: Note dependencies or conflicts with existing code
- **Leverage Opportunities**: Identify existing APIs, services, or utilities that can be reused
- Document findings in `/research/[feature]/codebase-analysis.md`

**MCP Enhancement**: Use `mcp__Context7__get-library-docs` for any existing libraries to ensure compatibility

### 2. External Research with MCP Tools

#### Required Research (Do ALL of these):
1. **Concept Understanding**
   ```
   mcp__perplexity-ask__perplexity_ask(
     messages=[{
       "role": "user", 
       "content": "Explain {concept} best practices, common patterns, and pitfalls"
     }]
   )
   ```

2. **Current Examples**
   ```
   mcp__brave-search__brave_web_search(
     query="{feature} implementation example 2024 2025",
     count=20
   )
   ```

3. **Library Documentation**
   ```
   # First resolve library ID
   mcp__Context7__resolve-library-id(libraryName="{library}")
   # Then get comprehensive docs
   mcp__Context7__get-library-docs(
     context7CompatibleLibraryID="/org/library",
     tokens=10000,
     topic="{specific_feature}"
   )
   ```

4. **Complex Planning**
   ```
   mcp__sequential-thinking__sequentialthinking(
     thought="Breaking down {feature} implementation",
     thoughtNumber=1,
     totalThoughts=10,
     nextThoughtNeeded=True
   )
   ```

#### Research Requirements:
- Minimum 30 sources across all MCP tools
- Save ALL outputs to `/research/[feature]/`
- Include citations with dates and URLs
- Cross-reference information from multiple tools

### 3. Synthesis & Documentation
- Compile findings into coherent context
- Identify patterns and best practices
- Document gotchas and edge cases
- Create implementation blueprint

## PRP Generation

Using PRPs/templates/prp_base.md as template, include:

### Critical Context from MCP Research
- **Documentation**: Direct quotes from Context7 with version numbers
- **Examples**: Working code from Brave Search results
- **Best Practices**: Insights from Perplexity research
- **Architecture**: Decisions from Sequential Thinking analysis
- **Research References**: Links to all `/research/[feature]/` files

### Implementation Blueprint
1. Include sequential thinking breakdown
2. Reference specific research findings
3. Provide error handling from research
4. List tasks with MCP tool validation

### Validation Gates
```bash
# Syntax/Style
ruff check --fix && mypy .

# Unit Tests
pytest tests/ -v --cov=src

# Integration Tests (if applicable)
pytest tests/integration -v

# E2E Tests with Playwright MCP (if web UI)
# YOU must use Playwright MCP to directly test all web functionality
```

### Web Testing Integration
If feature includes web UI, YOU must directly test the website:
- **YOU must use Playwright MCP** to directly interact with and test all web functionality
- Use `browser_navigate`, `browser_click`, `browser_type`, `browser_take_screenshot`, `browser_snapshot`
- Specify all user interactions that must be directly tested
- Define screenshot capture points for visual validation
- List complete user workflows that must be tested end-to-end
- Never assume web functionality works - include direct testing requirements

## Quality Assurance

### Pre-PRP Checklist
- [ ] Used all relevant MCP tools
- [ ] Minimum 30 research sources
- [ ] All research saved to `/research/`
- [ ] Cross-referenced multiple sources
- [ ] Updated research-log.md

### PRP Quality Metrics
- [ ] All context from MCP research included
- [ ] Validation gates are executable
- [ ] References research files
- [ ] Clear implementation path
- [ ] Error handling from research
- [ ] Version numbers for all libraries
- [ ] Working code examples included

## Output

Save as: `PRPs/{feature-name}.md`

Include at top of PRP:
```yaml
mcp_tools_used:
  - Context7: [number] queries
  - Perplexity: [number] queries  
  - Brave Search: [number] queries
  - Sequential Thinking: [number] sessions
research_files: /research/[feature]/
confidence_score: [1-10]
```

## Final Steps

1. **Review Research Completeness**
   - Check `/research/[feature]/` has 30+ files
   - Verify all MCP tool outputs saved
   - Ensure citations included

2. **Score Confidence**
   - 10/10: Comprehensive research, clear path, all edge cases covered
   - 8-9/10: Good research, minor gaps
   - <8/10: Need more MCP tool research

Remember: The goal is one-pass implementation success through comprehensive MCP-powered research!