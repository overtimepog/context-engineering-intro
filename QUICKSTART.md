# Context Engineering Quick Start Guide with MCP Tools

## What You Have

This template gives you a complete Context Engineering system powered by MCP tools:

1. **CLAUDE.md** - Global rules with MCP tool integration
2. **PLANNING.md** - Architecture and governance principles
3. **TASK.md** - Task tracking with MCP usage documentation
4. **research/** - MCP tool research outputs
5. **examples/** - Code examples for AI to follow
6. **PRPs/** - Generated implementation blueprints
7. **.claude/** - Enhanced commands using MCP tools

## MCP Tools Available

| Tool | Purpose | When to Use |
|------|---------|-------------|
| **Context7** | Library docs | Need accurate API documentation |
| **Perplexity** | AI research | Understanding concepts, best practices |
| **Brave Search** | Web search | Finding examples, current info |
| **Sequential Thinking** | Reasoning | Breaking down complex problems |
| **Playwright MCP** | Web testing | Automated browser testing |

## Quick Start Workflow

### Step 1: Understand Your Tools
The AI assistant now has access to powerful MCP tools that provide:
- **Real-time documentation** (not outdated training data)
- **Current examples** from across the web
- **Verified information** with citations
- **Complex reasoning** for difficult problems
- **Automated testing** for web features

### Step 2: Customize Project Rules
Edit `CLAUDE.md` to see MCP integration:
```markdown
## MCP Tool Integration
- Context7 for library docs
- Perplexity for research
- Brave Search for examples
- Sequential Thinking for planning
- Playwright for testing
```

### Step 3: Create Feature Request
Edit `INITIAL.md` with your feature:
```markdown
## FEATURE:
Build a FastAPI authentication system with JWT tokens

## EXAMPLES:
See examples/auth_api.py for our API patterns

## DOCUMENTATION:
FastAPI docs: https://fastapi.tiangolo.com/
PyJWT docs: https://pyjwt.readthedocs.io/

## OTHER CONSIDERATIONS:
- Research current JWT best practices
- Find examples of refresh token implementation
- Check security vulnerabilities
```

### Step 4: Generate PRP with MCP Research
```
/generate-prp INITIAL.md
```

**What happens behind the scenes:**
1. AI uses **Perplexity** to understand JWT best practices
2. AI uses **Brave Search** to find current implementation examples
3. AI uses **Context7** to get accurate FastAPI/PyJWT documentation
4. AI uses **Sequential Thinking** to plan the implementation
5. All research is saved to `/research/[feature]/`

### Step 5: Execute with Validation
```
/execute-prp PRPs/your-feature.md
```

**Execution includes:**
1. Sequential thinking for planning
2. Test-driven development
3. Git checkpoints after each validated section
4. Playwright testing for any web UI
5. Comprehensive documentation

## MCP Tool Usage Examples

### Example 1: Research-Heavy Feature
```markdown
## FEATURE:
Integrate with Stripe payment processing

## DOCUMENTATION:
Stripe API: https://stripe.com/docs/api

## OTHER CONSIDERATIONS:
- Need latest Stripe API version
- Research webhook best practices
- Find production-ready examples
```

The AI will:
- Use **Context7** to get Stripe library docs
- Use **Perplexity** to research payment processing best practices
- Use **Brave Search** to find recent Stripe integration examples

### Example 2: Complex Architecture
```markdown
## FEATURE:
Design microservices architecture for e-commerce

## OTHER CONSIDERATIONS:
- Need service boundaries
- Communication patterns
- Scaling considerations
```

The AI will:
- Use **Sequential Thinking** to break down the architecture
- Use **Perplexity** for microservices best practices
- Document decisions in `/research/architecture/`

### Example 3: Web UI Feature
```markdown
## FEATURE:
Create responsive dashboard with charts

## OTHER CONSIDERATIONS:
- Must work on mobile
- Need accessibility compliance
- Real-time data updates
```

The AI will:
- Generate implementation with web best practices
- Use **Playwright MCP** to generate comprehensive tests
- Validate responsiveness across devices
- Check accessibility automatically

## Tips for MCP Tool Success

### 1. Let Tools Do Research
Don't provide outdated docs - let the AI research:
```markdown
## BAD:
Here's what I found on Google about JWT...

## GOOD:
Research current JWT best practices and security considerations
```

### 2. Request Comprehensive Research
```markdown
## OTHER CONSIDERATIONS:
- Research at least 30 sources
- Find production examples
- Check for security issues
- Get latest library versions
```

### 3. Review Research Outputs
Check `/research/[feature]/` to see:
- What the AI discovered
- Sources and citations
- Implementation decisions
- Alternative approaches

### 4. Use Sequential Thinking
For complex features, mention in INITIAL.md:
```markdown
## OTHER CONSIDERATIONS:
- This is a complex multi-step feature
- Break down into manageable phases
- Consider edge cases and error handling
```

## Common MCP Patterns

### Pattern 1: Library Integration
1. Context7 → Get official docs
2. Perplexity → Understand best practices
3. Brave → Find real examples
4. Implement with confidence

### Pattern 2: Debugging/Problem Solving
1. Sequential Thinking → Analyze the problem
2. Brave Search → Find similar issues
3. Perplexity → Understand root causes
4. Implement fix with tests

### Pattern 3: Performance Optimization
1. Sequential Thinking → Identify bottlenecks
2. Perplexity → Research optimization techniques
3. Brave → Find benchmarks and comparisons
4. Implement with measurements

## Verifying MCP Tool Usage

### Check Research Quality
```bash
# See what research was done
ls -la research/[feature]/

# Check citations
grep "Source:" research/[feature]/*.md

# Verify tool usage
grep "mcp_tools_used:" PRPs/[feature].md
```

### Monitor Tool Usage in TASK.md
Each task documents:
- Which MCP tools were used
- What research was performed
- Links to research outputs

## Troubleshooting

### If PRP seems generic:
- Request more research in INITIAL.md
- Specify minimum 30 sources
- Ask for specific tool usage

### If implementation fails:
- Check research outputs
- Verify library versions
- Use sequential thinking for debugging

### If tests don't pass:
- Playwright MCP for web testing
- Sequential thinking for diagnosis
- Research specific error messages

## Next Steps

1. **Try a Simple Feature** with MCP research
2. **Review Research Outputs** in `/research/`
3. **Compare Results** with traditional approaches
4. **Build Confidence** in MCP tool capabilities
5. **Share Feedback** on tool effectiveness

Remember: MCP tools make your context engineering 10x more powerful by providing real-time, verified information instead of relying on potentially outdated training data!