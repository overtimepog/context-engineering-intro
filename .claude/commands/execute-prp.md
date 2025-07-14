# Execute PRP with Sequential Thinking & MCP Validation

Implement a feature using the PRP file with enhanced MCP tool support and validation.

## PRP File: $ARGUMENTS

## Execution Process with MCP Integration

### 1. Load & Analyze PRP
- Read the specified PRP file
- Check `mcp_tools_used` section for research context
- Review all `/research/` references
- Use `mcp__sequential-thinking__sequentialthinking` to understand complex requirements

### 2. Sequential Planning Phase

#### Use Sequential Thinking for Planning
```python
mcp__sequential-thinking__sequentialthinking(
    thought="Analyzing PRP requirements and creating implementation plan",
    thoughtNumber=1,
    totalThoughts=10,  # Adjust based on complexity
    nextThoughtNeeded=True
)
```

#### Planning Steps:
1. **Decompose Requirements** → Break down into atomic tasks
2. **Identify Dependencies** → What needs to be done first?
3. **Risk Assessment** → What could go wrong?
4. **Validation Strategy** → How to verify each step?
5. **Create Task List** → Use TodoWrite tool

### 3. Pre-Implementation Research

If PRP references are unclear or outdated:
- Use `mcp__perplexity-ask__perplexity_ask` for clarification
- Use `mcp__brave-search__brave_web_search` for current examples
- Use `mcp__Context7__get-library-docs` for API updates
- Document new findings in `/research/[feature]/updates/`

### 4. Implementation with Continuous Validation

#### 4.1 Setup Phase
```bash
# Create feature branch (if using git)
git checkout -b feature/[name]

# Set up environment
python -m venv venv && source venv/bin/activate  # or use Docker
pip install -r requirements.txt
```

#### 4.2 Incremental Implementation
For EACH task in the plan:

1. **Implement Code Section**
   - Follow patterns from PRP
   - Use examples from research
   - Apply error handling strategies

2. **Immediate Validation**
   ```bash
   # Syntax check
   ruff check --fix [file]
   
   # Type check
   mypy [file]
   
   # Run relevant tests
   pytest tests/[relevant] -v
   ```

3. **Fix Issues**
   - If validation fails, use sequential thinking to diagnose
   - Research solutions with MCP tools if needed
   - Document fixes for future reference

4. **Git Checkpoint** (if all tests pass)
   ```bash
   git add [files]
   git commit -m "feat: implement [section] - all tests passing"
   ```

### 5. Web UI Testing with Playwright MCP

If feature includes web components:

1. **Generate Tests**
   - Use `browser_generate_playwright_test` tool
   - Create comprehensive test scenarios
   - Include accessibility checks

2. **Run Tests**
   - Execute in headed mode first for visual verification
   - Capture screenshots at key points
   - Validate all interactions

3. **Debug Failures**
   - Use Playwright Inspector
   - Check console errors
   - Verify responsive design

### 6. Integration Validation

#### 6.1 Full Test Suite
```bash
# Run all tests with coverage
pytest tests/ -v --cov=src --cov-report=term-missing

# Check coverage meets requirement (≥85%)
# If not, add missing tests
```

#### 6.2 Integration Testing
```bash
# Start service/application
python -m src.main --dev  # or appropriate command

# Run integration tests
pytest tests/integration -v

# Manual verification if needed
curl -X POST http://localhost:8000/[endpoint] -d '{...}'
```

#### 6.3 E2E Testing
If applicable, run Playwright E2E tests:
```bash
# Run Playwright tests
npx playwright test tests/e2e/

# View report
npx playwright show-report
```

### 7. Final Validation & Documentation

#### 7.1 Complete Checklist
Review all items from PRP validation section:
- [ ] All tests pass
- [ ] No linting errors
- [ ] No type errors
- [ ] Coverage ≥ 85%
- [ ] Manual tests successful
- [ ] Error cases handled
- [ ] Performance acceptable

#### 7.2 Update Documentation
- Update README.md if needed
- Add/update API documentation
- Update capability-matrix.md
- Document any deviations from PRP

#### 7.3 Research Documentation
If you discovered new information:
- Add to `/research/[feature]/implementation-notes.md`
- Update research-log.md
- Note for future PRP improvements

### 8. Completion Report

Generate a summary including:
- Tasks completed vs planned
- Any deviations from PRP
- Issues encountered and solutions
- Test results summary
- Performance metrics
- Suggestions for improvement

## MCP Tool Usage During Execution

### When to Use Each Tool:

| Situation | Tool | Purpose |
|-----------|------|---------|
| Unclear requirement | Sequential Thinking | Break down complexity |
| API confusion | Context7 | Get current docs |
| Implementation pattern | Brave Search | Find examples |
| Best practices | Perplexity | Understand concepts |
| Web UI testing | Playwright MCP | Automated testing |

### Research During Implementation
If you need additional research:
1. Create new research task in TodoWrite
2. Use appropriate MCP tools
3. Save findings to `/research/[feature]/during-implementation/`
4. Reference in code comments

## Error Recovery

If implementation gets stuck:

1. **Use Sequential Thinking**
   ```python
   mcp__sequential-thinking__sequentialthinking(
       thought="Analyzing implementation blocker: [describe issue]",
       thoughtNumber=1,
       totalThoughts=5,
       nextThoughtNeeded=True
   )
   ```

2. **Research Solutions**
   - Search for error messages
   - Check library GitHub issues
   - Review similar implementations

3. **Document Resolution**
   - Add to troubleshooting guide
   - Update PRP if needed
   - Create ADR if architecture changes

## Success Criteria

The implementation is complete when:
1. ✅ All PRP requirements implemented
2. ✅ All validation gates pass
3. ✅ Documentation updated
4. ✅ Research findings documented
5. ✅ Git commits created at checkpoints
6. ✅ Final integration verified

Remember: The goal is high-quality, validated implementation with comprehensive documentation!