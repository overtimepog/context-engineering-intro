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

3. **Multi-Agent Testing (After Each Section)**
   Deploy multiple agents for comprehensive validation:
   - **Service Agent**: Start and monitor the application/service
   - **User Agent**: Test interactions and user workflows
   - **Monitor Agent**: Watch for errors, performance issues, logs
   - **Coordination**: Agents share findings and coordinate test scenarios
   - **Regression Check**: Verify previous features still work correctly

4. **Fix Issues**
   - If validation fails, use sequential thinking to diagnose
   - Research solutions with MCP tools if needed
   - Document fixes for future reference

5. **Git Checkpoint** (if all tests pass)
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

#### 6.2 Integration Testing with Multi-Agent Feature Loss Detection
```bash
# Start service/application
python -m src.main --dev  # or appropriate command

# Run integration tests
pytest tests/integration -v

# Manual verification if needed
curl -X POST http://localhost:8000/[endpoint] -d '{...}'
```

**Enhanced Multi-Agent Testing for Feature Loss Detection:**
- **Service Agent**: Maintains application instance and monitors system health
- **Legacy Feature Agent**: Tests all previously implemented features for regression
- **New Feature Agent**: Validates current implementation section
- **Integration Agent**: Tests interactions between old and new features
- **Communication Protocol**: 
  - Share test results in real-time via shared log files
  - Coordinate test timing to avoid conflicts
  - Report any feature degradation immediately
  - Cross-validate findings between agents

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
- [ ] Multi-agent testing confirms no feature loss
- [ ] All agents report successful coordination
- [ ] Cross-agent validation completed

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

## Multi-Agent Communication Protocol

### Agent Coordination Requirements

**Shared Context Management:**
- Create shared log file: `/tmp/multi-agent-test-log.md` 
- Each agent writes status updates with timestamps
- Include agent role, current action, and findings
- Log any errors or unexpected behavior immediately

**Communication Pattern:**
```markdown
[TIMESTAMP] [AGENT_ROLE] [STATUS] [MESSAGE]
2025-07-15 10:30:00 SERVICE_AGENT STARTED Application running on port 8000
2025-07-15 10:30:05 USER_AGENT TESTING Testing login functionality
2025-07-15 10:30:10 MONITOR_AGENT ERROR Database connection timeout detected
2025-07-15 10:30:15 LEGACY_AGENT REGRESSION Previous search feature working correctly
```

**Synchronization Points:**
- Wait for SERVICE_AGENT "READY" before starting tests
- Coordinate test scenarios to avoid conflicts
- Share test results before proceeding to next section
- Aggregate findings before final validation

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