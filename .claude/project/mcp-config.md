# MCP Tool Configuration

This file contains project-specific MCP tool configurations and usage patterns.

## MCP Tool Availability

### Research Tools
```yaml
perplexity:
  enabled: true
  usage: "Concept understanding, best practices research"
  
brave_search:
  enabled: true
  usage: "Current examples, implementation patterns"
  
context7:
  enabled: true
  usage: "Library documentation, API references"
```

### Reasoning Tools
```yaml
sequential_thinking:
  enabled: true
  usage: "Complex problem decomposition, planning"
  max_thoughts: 20
```

### Testing Tools
```yaml
playwright_mcp:
  enabled: true
  config:
    headless: false  # Use headed mode for debugging
    browsers: ["chromium", "firefox", "webkit"]
    capabilities:
      - browser_snapshot
      - browser_click
      - browser_navigate
      - browser_take_screenshot
      - browser_generate_playwright_test
```

## Tool Usage Patterns

### 1. Research Pattern
Always use multiple tools in parallel:
```python
# Good - Parallel execution
results = parallel([
    perplexity_research(topic),
    brave_search(topic),
    context7_docs(library)
])

# Bad - Sequential execution
result1 = perplexity_research(topic)
result2 = brave_search(topic)
result3 = context7_docs(library)
```

### 2. Documentation Pattern
For each library/framework:
1. First: `mcp__Context7__resolve-library-id`
2. Then: `mcp__Context7__get-library-docs`
3. Save to: `/research/[library]/context7-docs.md`

### 3. Complex Problem Pattern
Use sequential thinking for:
- Architecture decisions
- Multi-step implementations
- Performance optimizations
- Error diagnosis

### 4. Testing Pattern
For web features:
1. Generate tests with Playwright MCP
2. Run in headed mode first
3. Capture screenshots
4. Validate all interactions

## Research Requirements

### Minimum Standards
- **New Features**: 30+ research sources
- **Bug Fixes**: 10+ sources
- **Documentation**: 5+ sources
- **Refactoring**: 15+ sources

### Source Distribution
- Context7: 40% (library docs)
- Perplexity: 30% (concepts)
- Brave: 30% (examples)

## Output Organization

### Research Files
```
/research/
└── [feature]/
    ├── context7/
    │   └── [library]-docs.md
    ├── perplexity/
    │   └── [concept]-research.md
    ├── brave/
    │   └── [topic]-examples.md
    └── synthesis/
        └── implementation-plan.md
```

### Citation Format
```markdown
**Source**: [Tool Name]
**Date**: YYYY-MM-DD
**Query**: "exact query used"
**URL**: https://...
**Key Findings**:
- Finding 1
- Finding 2
```

## Rate Limits & Best Practices

### API Limits
- Perplexity: Respect rate limits
- Brave: Max 20 results per query
- Context7: 10,000 tokens per request

### Efficiency Tips
1. Batch related queries
2. Cache research results
3. Reuse relevant findings
4. Update research incrementally

## Troubleshooting

### Common Issues
1. **Context7 library not found**: Try alternative names
2. **Brave no results**: Refine search terms
3. **Perplexity timeout**: Break into smaller queries
4. **Playwright fails**: Check browser installation

### Debug Commands
```bash
# Test MCP availability
claude mcp list

# Check tool permissions
cat .claude/settings.local.json

# Verify research directory
tree research/
```