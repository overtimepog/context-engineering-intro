# Execute PRP with Sequential Thinking & MCP Validation

Implement a feature using the PRP file with enhanced MCP tool support and validation.

## PRP File: $ARGUMENTS

## Execution Process with MCP Integration

### 1. Load & Analyze PRP + Understand Codebase

#### 1.1 PRP Analysis
- Read the specified PRP file
- Check `mcp_tools_used` section for research context
- Review all `/research/` references
- Use `mcp__sequential-thinking__sequentialthinking` to understand complex requirements

#### 1.2 Current Codebase Understanding
**Essential first step - understand the existing codebase:**

- **Project Context**: Read `README.md`, `PLANNING.md`, `CLAUDE.md` for current project state
- **Directory Structure**: Use `LS` to understand organization and file layout
- **Dependencies**: Check `package.json`, `requirements.txt`, etc. for existing libraries
- **Implementation Status Assessment**: 
  - Use `Grep` to search for related functionality keywords
  - Check if similar features already exist (partial or complete)
  - Identify placeholder functions, TODO comments, or stub implementations
  - Review commit history to understand recent development focus
  - Look for incomplete features that could be extended vs starting fresh
- **Code Patterns**: Use `Grep` and `Glob` to find:
  - Similar existing features that could be extended
  - Current code style and conventions
  - Error handling patterns
  - Testing frameworks and patterns
  - Import/module organization
- **Architecture**: Read key source files to understand:
  - Current frameworks and libraries in use
  - Data flow and component structure
  - API patterns and interfaces
  - Database schema and models (if applicable)
- **Feature Gap Analysis**:
  - What's already implemented that relates to the PRP?
  - What's missing or incomplete?
  - What needs modification vs new development?
  - Are there existing APIs/services that can be leveraged?
- **Integration Points**: Identify where new feature should connect
- **Existing Tests**: Review test structure and utilities available

#### 1.3 Compatibility Check
- Use `mcp__Context7__get-library-docs` for existing libraries to ensure version compatibility
- Document any version conflicts or upgrade requirements
- Note integration challenges with current architecture

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
2. **Codebase Integration Planning** → How to integrate with existing code
3. **Identify Dependencies** → What needs to be done first? What existing code to modify?
4. **Risk Assessment** → What could go wrong? What existing features might break?
5. **Validation Strategy** → How to verify each step? What existing tests to run?
6. **Create Task List** → Use TodoWrite tool with codebase-aware tasks

### 3. Pre-Implementation Research

#### 3.1 Gap Analysis
Compare PRP with current codebase understanding:
- Are there new libraries needed not in current dependencies?
- Do existing patterns support the planned implementation?
- Are there integration challenges not covered in the PRP?

#### 3.2 Additional Research (if needed)
If PRP references are unclear or codebase integration is complex:
- Use `mcp__perplexity-ask__perplexity_ask` for clarification on integration patterns
- Use `mcp__brave-search__brave_web_search` for current examples with similar codebases
- Use `mcp__Context7__get-library-docs` for API updates and integration guides
- Research how to extend existing features vs building new ones
- Document new findings in `/research/[feature]/updates/`

#### 3.3 Codebase-Specific Considerations
- Identify which existing files need modification
- Plan for backward compatibility with existing features
- Consider impact on existing tests and user workflows

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
   - **User Agent**: Test interactions and user workflows using Playwright MCP for web testing
   - **Monitor Agent**: Watch for errors, performance issues, logs
   - **Coordination**: Agents share findings and coordinate test scenarios
   - **Regression Check**: Verify previous features still work correctly
   
   **Issue Discovery & Documentation Phase:**
   - Testing agents **DO NOT FIX** issues they find
   - **For Web Testing**: User Agent must use Playwright MCP tools:
     - `browser_navigate` to access pages
     - `browser_click`, `browser_type` for interactions
     - `browser_take_screenshot` for visual evidence
     - `browser_snapshot` for page state capture
   - Document all issues in shared `/tmp/testing-issues.md`:
     ```markdown
     ## Issue #001
     **Agent**: USER_AGENT (using Playwright MCP)
     **Type**: Missing Feature
     **Description**: Login button does not respond to clicks
     **Location**: src/components/LoginForm.js:45 (URL: /login)
     **Expected**: Button should trigger login API call
     **Actual**: No response, no console errors
     **Screenshot**: /tmp/issue-001-screenshot.png
     **Priority**: High
     **Status**: NEEDS_FIX
     ```
   
   **Fix Agent Deployment:**
   - After all testing agents complete discovery phase
   - **Fix Agent** spawns to address all documented issues
   - Fix Agent uses MCP tools to research solutions
   - Fix Agent implements fixes and reports completion:
     ```markdown
     ## Fix Report #001
     **Issue**: #001
     **Fix Applied**: Added missing onClick handler and API integration
     **Files Modified**: src/components/LoginForm.js, src/api/auth.js
     **Ready for Re-test**: YES
     ```
   
   **Fix-Test Communication Loop:**
   1. **Fix Agent** announces fix completion
   2. **Testing Agents** re-test the specific issue:
      - **For Web Issues**: User Agent uses Playwright MCP to re-test interactions
      - Takes new screenshot to compare with original issue
      - Uses `browser_navigate`, `browser_click` etc. to verify fix
   3. **Testing Agents** report results back to Fix Agent with evidence
   4. If still broken: Fix Agent researches more and applies new fix
   5. Repeat until issue resolved
   6. Continue until all issues marked "RESOLVED"

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

If feature includes web components, YOU must directly interact with the website:

1. **Direct Web Testing**
   - YOU must use `browser_navigate` to visit pages
   - YOU must use `browser_click` to test buttons and links
   - YOU must use `browser_type` to fill forms and inputs
   - YOU must use `browser_take_screenshot` to capture visual evidence
   - YOU must use `browser_snapshot` to save page states
   - Never assume web functionality works - test it yourself

2. **Comprehensive Testing**
   - Test all user interactions directly
   - Verify all forms and inputs work
   - Check all navigation and routing
   - Test responsive design at different screen sizes
   - Capture screenshots of all key states

3. **Debug Failures**
   - Use screenshots to identify visual issues
   - Check console errors through browser tools
   - Test edge cases and error conditions
   - Verify accessibility features

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
- **Service Agent**: Maintains application instance, monitors system health
- **Legacy Feature Agent**: Tests all previously implemented features for regression using Playwright MCP for web features
- **New Feature Agent**: Validates current implementation section using Playwright MCP for web features
- **Integration Agent**: Tests interactions between old and new features using Playwright MCP for web workflows

**Issue Discovery & Documentation (Integration Phase):**
- Testing agents document all findings in `/tmp/integration-issues.md`
- **For Web Testing**: Use Playwright MCP to capture screenshots and page states
- Include regression issues, integration failures, performance problems
- Rate severity: Critical (breaks existing features), High (new feature broken), Medium (minor issues)
- **Web Evidence**: Include screenshots, console logs, network requests from Playwright MCP

**Specialized Fix Agent for Integration:**
- **Integration Fix Agent** spawns after discovery phase
- Prioritizes Critical issues first (regression fixes)
- Uses MCP tools for complex integration research
- Reports fixes with impact analysis:
  ```markdown
  ## Integration Fix Report #003
  **Issue**: #003 - API endpoints conflict
  **Fix Applied**: Namespaced new endpoints under /v2/
  **Impact**: Maintains backward compatibility for existing clients
  **Files Modified**: src/routes/api.js, src/middleware/versioning.js
  **Regression Risk**: Low - old endpoints unchanged
  **Ready for Re-test**: YES
  ```

**Continuous Fix-Test Loop:**
- Integration Fix Agent and Testing Agents communicate until all issues resolved
- **For Web Fixes**: Testing agents use Playwright MCP to verify both fix AND no new regressions introduced
- Compare before/after screenshots to validate visual fixes
- Test complete user workflows end-to-end with Playwright MCP
- **Success criteria**: All agents report "INTEGRATION_VALIDATED"

#### 6.3 E2E Testing
If applicable, YOU must directly test end-to-end workflows:
- **YOU must use Playwright MCP** to test complete user journeys
- Navigate through entire workflows using `browser_navigate`, `browser_click`, `browser_type`
- Test all critical paths and user scenarios
- Capture screenshots of each step for documentation
- Verify all integrations work end-to-end
- Never assume the full workflow works - test it yourself completely

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
- [ ] Web functionality directly tested with Playwright MCP (if applicable)
- [ ] All user interactions verified through direct testing

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
2025-07-15 10:30:05 USER_AGENT TESTING Testing login functionality with Playwright MCP
2025-07-15 10:30:10 MONITOR_AGENT ISSUE_FOUND Database connection timeout - documented as Issue #001
2025-07-15 10:30:15 USER_AGENT ISSUE_FOUND Login button not responding - documented as Issue #002 with screenshot
2025-07-15 10:30:20 SERVICE_AGENT TESTING_COMPLETE All tests finished, 2 issues documented
2025-07-15 10:30:25 FIX_AGENT SPAWNED Analyzing 2 issues, starting with Critical priority
2025-07-15 10:30:30 FIX_AGENT RESEARCHING Using MCP tools to research Issue #001 solutions
2025-07-15 10:30:35 FIX_AGENT FIX_APPLIED Issue #001 fixed - database timeout resolved
2025-07-15 10:30:40 MONITOR_AGENT RETESTING Re-testing Issue #001 - database connection
2025-07-15 10:30:45 MONITOR_AGENT VERIFIED Issue #001 RESOLVED - database working
2025-07-15 10:30:50 FIX_AGENT FIX_APPLIED Issue #002 fixed - login handler added
2025-07-15 10:30:55 USER_AGENT RETESTING Re-testing Issue #002 with Playwright MCP - login functionality
2025-07-15 10:31:00 USER_AGENT VERIFIED Issue #002 RESOLVED - login working, screenshot confirms
2025-07-15 10:31:05 FIX_AGENT COMPLETE All issues resolved, testing agents can proceed
```

**Synchronization Points:**
- Wait for SERVICE_AGENT "READY" before starting tests
- **Testing Phase**: All testing agents must report "TESTING_COMPLETE" before Fix Agent spawns
- **Issue Documentation**: All issues must be documented before fixing begins
- **Fix Phase**: Fix Agent addresses issues one by one, announces each completion
- **Verification Phase**: Testing agents re-test specific issues and verify fixes
- **Fix-Test Loop**: Continue until all issues marked "RESOLVED"
- **Section Completion**: Only proceed when Fix Agent reports "COMPLETE" and no issues remain
- **Project completion requires**: All agents report "ALL_ISSUES_RESOLVED" simultaneously

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