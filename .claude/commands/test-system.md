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
  - **React components and pages**: UI component hierarchy for user and admin interfaces
  - **Service classes and utilities**: Business logic and helpers
  - **Configuration and environment variables**: System configuration
  - **Authentication systems**: User roles, admin roles, permission levels
  - **Payment integrations**: Stripe, PayPal, other payment processors
  - **Sandbox/Test credentials**: Look for test API keys, sandbox environments
  - **Admin interfaces**: Admin panels, dashboards, management tools
  - **User workflows**: Registration, login, core user journeys
  - **E-commerce features**: Shopping cart, checkout, product management
  - **Existing tests and test patterns**: Current testing coverage and approaches
  - **TODO comments and incomplete features**: Work in progress
  - **Error handling patterns**: How errors are currently managed
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

**Web UI Testing Agents** (if web application detected):

**User Agent** - Simulates Regular User:
- Responsibilities: **YOU must directly test** all user-facing interfaces and workflows
- Tools: **Playwright MCP** (`browser_navigate`, `browser_click`, `browser_type`, `browser_take_screenshot`, `browser_snapshot`)
- Focus: User registration, login, core functionality, user journeys - never assume functionality works
- **Authentication**: Look for sandbox/test user credentials in `.env.example`, docs, or config files
- **Direct Testing Required**: YOU must interact with every user-accessible page and feature
- **UI/Design Testing**: Check for visual problems:
  - Elements overflowing containers (search boxes sticking out)
  - Spacing and alignment issues
  - Text visibility problems (contrast, overlapping)
  - Responsive design breakpoints
  - Consistent styling across pages
  - Accessibility issues (button sizes, readability)

**Admin Agent** - Simulates Administrator User:
- Responsibilities: **YOU must directly test** all admin interfaces and administrative functions
- Tools: **Playwright MCP** (`browser_navigate`, `browser_click`, `browser_type`, `browser_take_screenshot`, `browser_snapshot`)
- Focus: Admin panels, user management, system configuration, data management
- **Authentication**: Look for sandbox/test admin credentials in config files
- **Direct Testing Required**: YOU must test every admin feature and management interface
- **Admin UI Testing**: Check for design consistency and usability in admin panels

**Payment/Transaction Agent** (if e-commerce/payment features detected):
- Responsibilities: **YOU must directly test** payment flows and transaction processes
- Tools: **Playwright MCP** for complete checkout and payment testing
- Focus: Shopping cart, checkout process, payment integration testing
- **Sandbox Keys**: Look for and use test/sandbox payment keys (Stripe test keys, PayPal sandbox, etc.)
- **Test Data**: Use sandbox credit card numbers and test payment methods

**UI/Design Agent** - AI-Powered Visual and Design Quality Testing:
- Responsibilities: **YOU must directly test** all visual and design aspects using AI principles
- Tools: **Playwright MCP** with focus on `browser_take_screenshot` and visual inspection
- **AI-Powered Testing Approach**:
  - **Visual-First Testing**: Identify UI elements as users see them, not just code structure
  - **Self-Healing Detection**: Note when UI changes might break existing functionality
  - **Dynamic Risk Profiling**: Prioritize testing critical UI areas (checkout, login, key CTAs)
  - **User-Centric Validation**: Test from real user perspective, not technical correctness
- **Design Issues to Check**:
  - **Layout Problems**: Elements overflowing containers, search boxes sticking out
  - **Spacing Issues**: Inconsistent margins, padding, alignment problems
  - **Text Visibility**: Low contrast, overlapping text, unreadable fonts
  - **Responsive Design**: Test at multiple viewport sizes (mobile, tablet, desktop)
  - **Visual Hierarchy**: Proper heading sizes, button prominence, call-to-action visibility
  - **Color Consistency**: Brand colors, hover states, active states
  - **Form Design**: Input field alignment, label positioning, error message display
  - **Loading States**: Proper skeleton screens, spinners, progress indicators
  - **Empty States**: How the UI looks with no data
  - **Error States**: 404 pages, error messages, validation feedback
  - **Consistency Validation**: Compare similar components across pages
  - **Usability Principles**: Clarity, efficiency, trust indicators
- **AI-Enhanced Research**: When issues found, use MCP tools with specific queries:
  - "Best practices for {UI pattern} according to user research"
  - "How to fix {specific issue} for better usability"
  - "Accessibility guidelines for {component type}"

**Security Agent**:
- Responsibilities: Test authentication, authorization, and security
- Tools: Security testing tools, penetration testing
- Focus: Access control, input validation, security vulnerabilities

**Performance Agent**:
- Responsibilities: Test system performance and scalability
- Tools: Load testing tools, performance monitoring
- Focus: Response times, throughput, resource usage

**Fixer Agent** - The Problem Solver:
- Responsibilities: **Fix ALL issues discovered by testing agents (including UI/design issues)**
- Tools: **MCP Research Tools** (Perplexity, Brave Search, Context7)
- **Code Fix Research Process**:
  1. Receive broken code and error details from testing agents
  2. Send to Perplexity for debugging guidance
  3. Search Brave for similar issues and solutions
  4. Get Context7 documentation for involved libraries
  5. Synthesize research into fix strategy
  6. Apply fix based on research findings
- **Design Fix Research Process (AI-Enhanced)**:
  1. Receive UI/design issue with screenshots from UI/Design Agent
  2. Research design best practices with Perplexity:
     - "How to fix {overflow issue} in {CSS framework} for better user experience"
     - "Best practices for {spacing/alignment} based on UI/UX research"
     - "Accessibility guidelines for {text contrast/readability} WCAG compliance"
     - "User-tested solutions for {specific UI pattern}"
  3. Search Brave for CSS solutions and design patterns with user feedback
  4. Get Context7 docs for UI frameworks (Bootstrap, Tailwind, Material-UI)
  5. Apply CSS/styling fixes based on research AND usability principles
  6. **Continuous Learning**: Document which fixes work best for future reference
- Focus: Research-driven fixes for both functionality AND design
- **Loop Strategy**: Test → Fix → Check → Fix until RESOLVED

#### 4.2 Agent Coordination Protocol with Fixer Agent

**Shared Communication**: `/tmp/system-test-log.md`
```markdown
[TIMESTAMP] [AGENT_ROLE] [STATUS] [MESSAGE]
2025-07-15 14:30:00 SERVICE_AGENT STARTED All services running - Web:3000, API:8000, DB:5432
2025-07-15 14:30:05 USER_AGENT TESTING Testing login workflow with Playwright MCP
2025-07-15 14:30:10 USER_AGENT ISSUE_FOUND Login button not responding - Issue #001
2025-07-15 14:30:15 FIXER_AGENT RESEARCHING Using Perplexity to research login button fix
2025-07-15 14:30:20 FIXER_AGENT RESEARCHING Brave Search: React onClick handler examples
2025-07-15 14:30:25 FIXER_AGENT RESEARCHING Context7: React event handling documentation
2025-07-15 14:30:30 FIXER_AGENT FIX_APPLIED Added missing onClick handler to login button
2025-07-15 14:30:35 USER_AGENT RETESTING Re-testing login button with Playwright MCP
2025-07-15 14:30:40 USER_AGENT STILL_BROKEN Function undefined error - sending back to Fixer
2025-07-15 14:30:45 FIXER_AGENT RESEARCHING Deeper research on React function imports
2025-07-15 14:30:50 FIXER_AGENT FIX_APPLIED Imported missing handleLogin function
2025-07-15 14:30:55 USER_AGENT RETESTING Re-testing login button functionality
2025-07-15 14:31:00 USER_AGENT RESOLVED Login button now working correctly
```

**Fixer Agent Integration**:
- Fixer Agent monitors all ISSUE_FOUND messages
- Automatically starts MCP research (Perplexity, Brave, Context7) when issues are reported
- Communicates fix status to testing agents
- Enters deeper research loops when fixes fail
- Only marks complete when testing agent confirms RESOLVED

### 5. Comprehensive Testing Execution

#### 5.1 System Startup and Health Check
1. **Service Agent** starts all discovered services
2. **All agents** wait for "SYSTEM_READY" status
3. **Health checks** on all services and dependencies

#### 5.2 Parallel Web Testing Execution with Multiple Playwright MCP Agents

**YOU must deploy multiple specialized web testing agents using Playwright MCP:**

**User Agent Testing Workflow:**
1. **YOU use `browser_navigate`** to access the main website
2. **Test User Registration**: Use `browser_type` to fill registration forms
3. **Test User Login**: Use discovered test/sandbox user credentials
4. **Navigate User Interface**: Use `browser_click` to test all user-accessible features
5. **Test Core User Workflows**: Complete typical user journeys end-to-end
6. **Capture Evidence**: Use `browser_take_screenshot` at each major step
7. **Document Issues**: Note any broken functionality or UI problems

**Admin Agent Testing Workflow:**
1. **YOU use `browser_navigate`** to access admin login/dashboard
2. **Test Admin Authentication**: Use discovered admin test credentials
3. **Test Admin Functions**: Use `browser_click` and `browser_type` to test:
   - User management interfaces
   - System configuration panels
   - Data management tools
   - Content management systems
   - Analytics and reporting dashboards
4. **Test Admin Workflows**: Complete administrative tasks end-to-end
5. **Verify Permissions**: Ensure admin-only features are properly protected
6. **Capture Evidence**: Use `browser_take_screenshot` for all admin interfaces

**Payment Agent Testing Workflow** (if applicable):
1. **Setup Sandbox Environment**: Use discovered test/sandbox payment keys
2. **Test Shopping Cart**: Add items, modify quantities, remove items
3. **Test Checkout Process**: Fill shipping, billing information
4. **Test Payment Integration**: Use sandbox credit card numbers:
   - Visa: 4242424242424242
   - Mastercard: 5555555555554444
   - American Express: 378282246310005
5. **Test Payment Scenarios**: Successful payments, declined cards, errors
6. **Verify Transaction Flow**: Complete purchase process end-to-end
7. **Test Admin Payment Views**: Check transaction logs, refund processes

**UI/Design Agent Testing Workflow (AI-Enhanced):**
1. **Risk-Based Priority Testing**:
   - Start with critical user paths (checkout, login, main CTAs)
   - Use AI principles to identify high-impact UI areas
   - Test business-critical interfaces first
2. **Visual Inspection at Multiple Viewports**:
   - Test at 320px (mobile), 768px (tablet), 1024px (laptop), 1920px (desktop)
   - Use `browser_take_screenshot` at each viewport for every page
   - Compare against expected design patterns automatically
3. **Layout and Spacing Analysis**:
   - Check for overflowing elements (search boxes, buttons, text)
   - Verify consistent spacing between elements
   - Ensure proper grid/flexbox alignment
   - Detect visual regression from previous versions
4. **Typography and Readability**:
   - Check text contrast ratios against WCAG standards
   - Verify font sizes meet accessibility minimums
   - Ensure no text overlaps or clips
   - Test readability across different backgrounds
5. **Interactive Element Testing**:
   - Test all hover states and transitions
   - Verify focus states for keyboard navigation
   - Check loading and error states
   - Validate touch targets for mobile (minimum 44x44px)
6. **User-Centric Design Validation**:
   - Test clarity of labels and instructions
   - Verify efficiency of user workflows
   - Check for trust indicators (security badges, testimonials)
   - Validate consistency with user expectations
7. **AI-Powered Pattern Recognition**:
   - Identify common UI anti-patterns automatically
   - Compare against successful design patterns
   - Suggest improvements based on best practices
8. **Document Issues with Enhanced Evidence**:
   - Screenshot every design problem found
   - Mark up screenshots to highlight issues
   - Include viewport size, browser info, and user impact
   - Rate issues by user experience severity

**Parallel Coordination**:
- All agents run simultaneously using Playwright MCP
- UI/Design Agent focuses on visual issues while others test functionality
- Each agent documents findings in real-time
- Coordinate to avoid conflicts (e.g., admin agent doesn't delete users being tested by user agent)
- Cross-validate functionality between user and admin perspectives

#### 5.3 Comprehensive Web Issue Discovery and Documentation
Each Playwright MCP agent documents detailed findings in `/tmp/system-test-issues.md`:

```markdown
## Issue #001
**Agent**: USER_AGENT (Playwright MCP)
**Type**: UI Bug
**Component**: Login Form
**Description**: Password reset link not working
**Location**: /login page, password reset modal
**User Perspective**: Regular user cannot reset password
**Expected**: Should send reset email and show confirmation
**Actual**: Button click shows 404 error
**Screenshot**: /tmp/user-login-issue-001.png
**Browser State**: /tmp/user-login-state-001.json
**Priority**: High
**Status**: NEEDS_FIX

## Issue #002
**Agent**: ADMIN_AGENT (Playwright MCP)
**Type**: Permission Error
**Component**: User Management Panel
**Description**: Admin cannot delete inactive users
**Location**: /admin/users page, delete button
**Admin Perspective**: Admin functionality incomplete
**Expected**: Should delete user and update user list
**Actual**: Shows "Access Denied" error despite admin permissions
**Screenshot**: /tmp/admin-users-issue-002.png
**Console Logs**: 403 Forbidden error on DELETE /api/users/123
**Priority**: Medium
**Status**: NEEDS_FIX

## Issue #003
**Agent**: PAYMENT_AGENT (Playwright MCP)
**Type**: Payment Integration Bug
**Component**: Checkout Process
**Description**: Sandbox payment processing fails at final step
**Location**: /checkout/payment page, confirm payment button
**Payment Perspective**: Cannot complete test transactions
**Expected**: Should process sandbox payment and show success
**Actual**: Spinner shows indefinitely, no success/error message
**Screenshot**: /tmp/payment-checkout-issue-003.png
**Test Data Used**: Visa 4242424242424242, exp 12/25, cvv 123
**Priority**: Critical
**Status**: NEEDS_FIX

## Issue #004
**Agent**: UI_DESIGN_AGENT (Playwright MCP)
**Type**: Visual Design Bug
**Component**: Search Box
**Description**: Search box overflows its container on mobile viewport
**Location**: Header navigation, all pages
**Design Perspective**: Layout breaking on small screens
**Expected**: Search box should stay within header boundaries
**Actual**: Search box extends 20px beyond header right edge
**Screenshots**: 
  - /tmp/search-overflow-mobile-320px.png
  - /tmp/search-overflow-tablet-768px.png
**Viewport**: 320px width (mobile)
**Priority**: High
**Status**: NEEDS_FIX

## Issue #005
**Agent**: UI_DESIGN_AGENT (Playwright MCP)
**Type**: Accessibility Issue
**Component**: Form Labels
**Description**: Text contrast too low on form field labels
**Location**: /register page, all form inputs
**Design Perspective**: Poor readability, fails WCAG AA standards
**Expected**: Contrast ratio of at least 4.5:1
**Actual**: Contrast ratio of 2.8:1 (#999999 on #FFFFFF)
**Screenshot**: /tmp/low-contrast-labels.png
**Accessibility Impact**: Users with visual impairments cannot read labels
**Priority**: High
**Status**: NEEDS_FIX
```

### 6. Fixer Agent Deployment

#### 6.1 Specialized Fixer Agent
**The Fixer Agent is responsible for fixing ALL issues discovered by testing agents:**

**Fixer Agent Workflow:**
1. **Receive Non-Working Code**: Testing agents send broken code/functionality details
2. **MCP Research Phase**:
   - **Perplexity Research**: Send the broken code and error details to `mcp__perplexity-ask__perplexity_ask`
     ```python
     mcp__perplexity-ask__perplexity_ask(
         messages=[{
             "role": "user",
             "content": "This code is not working: {broken_code}. Error: {error_message}. How can I fix this?"
         }]
     )
     ```
   - **Brave Search**: Search for similar issues and solutions
     ```python
     mcp__brave-search__brave_web_search(
         query="{error_message} {framework} fix solution",
         count=20
     )
     ```
   - **Context7 Documentation**: Get official documentation for the problematic libraries
     ```python
     mcp__Context7__resolve-library-id(libraryName="{library}")
     mcp__Context7__get-library-docs(
         context7CompatibleLibraryID="/org/library",
         tokens=10000,
         topic="{specific_feature}"
     )
     ```
3. **Analyze Research Results**: Synthesize findings from all MCP tools
4. **Apply Fix**: Implement the researched solution
5. **Document Fix**: Record what was changed and why

#### 6.2 Continuous Test → Fix → Check Loop

**The system operates in a continuous loop until ALL issues are fixed:**

```markdown
[LOOP START]
1. Testing Agent finds issue → Documents in /tmp/system-test-issues.md
2. Fixer Agent receives issue:
   - Extracts broken code and error details
   - Sends to Perplexity for debugging guidance
   - Searches Brave for similar issues and solutions
   - Gets Context7 documentation for involved libraries
   - Synthesizes research into a fix strategy
3. Fixer applies fix based on research
4. Testing Agent re-tests the specific issue:
   - User Agent uses Playwright MCP to verify user fixes
   - Admin Agent uses Playwright MCP to verify admin fixes
   - Payment Agent uses Playwright MCP to verify payment fixes
5. IF STILL BROKEN:
   - Testing Agent reports "STILL_BROKEN" with new error details
   - Fixer Agent conducts deeper research:
     * More specific Perplexity queries
     * Alternative solutions from Brave Search
     * Different approaches from Context7 docs
   - Fixer tries alternative fix
   - GOTO step 4
6. IF FIXED:
   - Testing Agent marks issue as "RESOLVED"
   - Move to next issue
[LOOP END when all issues RESOLVED]
```

**Example Fix-Test-Check Cycles:**

**Functional Fix Example:**
```markdown
[10:30:00] USER_AGENT: Login button not working - Issue #001
[10:30:05] FIXER_AGENT: Researching login button issue with MCP tools
[10:30:10] FIXER_AGENT: Perplexity suggests onClick handler missing
[10:30:15] FIXER_AGENT: Brave Search found similar React onClick issues
[10:30:20] FIXER_AGENT: Context7 React docs confirm event handler syntax
[10:30:25] FIXER_AGENT: Applied fix - added onClick handler to button
[10:30:30] USER_AGENT: Re-testing login button functionality
[10:30:35] USER_AGENT: STILL_BROKEN - Now getting "undefined function" error
[10:30:40] FIXER_AGENT: Deeper research - function not imported properly
[10:30:45] FIXER_AGENT: Applied fix - imported handleLogin function
[10:30:50] USER_AGENT: Re-testing login button functionality
[10:30:55] USER_AGENT: RESOLVED - Login button now working correctly
```

**Design Fix Example:**
```markdown
[10:35:00] UI_DESIGN_AGENT: Search box overflowing container on mobile - Issue #004
[10:35:05] FIXER_AGENT: Researching CSS overflow issues with MCP tools
[10:35:10] FIXER_AGENT: Perplexity: "CSS flexbox overflow solutions for responsive design"
[10:35:15] FIXER_AGENT: Brave Search: "search box responsive design patterns"
[10:35:20] FIXER_AGENT: Context7: Tailwind CSS docs on responsive utilities
[10:35:25] FIXER_AGENT: Applied fix - added max-width and overflow-hidden classes
[10:35:30] UI_DESIGN_AGENT: Re-testing at 320px viewport
[10:35:35] UI_DESIGN_AGENT: STILL_BROKEN - Now text is cut off
[10:35:40] FIXER_AGENT: Researching alternative - flexible width with proper constraints
[10:35:45] FIXER_AGENT: Applied fix - used flex-1 with min-width constraint
[10:35:50] UI_DESIGN_AGENT: Re-testing across all viewports
[10:35:55] UI_DESIGN_AGENT: RESOLVED - Search box now responsive at all sizes
```

### 7. System Validation and Reporting

#### 7.1 Complete Web System Validation

**Final Comprehensive Testing Phase:**

**User Agent Final Validation:**
- **YOU must use Playwright MCP** to complete full user registration → login → core functionality → logout workflow
- Test all major user features end-to-end using `browser_navigate`, `browser_click`, `browser_type`
- Verify all user interfaces are responsive and functional
- Test user account management, profile updates, password changes

**Admin Agent Final Validation:**
- **YOU must use Playwright MCP** to complete full admin workflow testing
- Test all administrative functions: user management, system configuration, content management
- Verify admin-only features are properly protected from regular users
- Test data export/import functions, system monitoring dashboards

**Payment Agent Final Validation** (if applicable):
- **YOU must complete** full purchase workflows using sandbox payment credentials
- Test various payment scenarios: successful payments, failed payments, refunds
- Verify payment data appears correctly in both user and admin views
- Test subscription management, recurring payments if applicable

**UI/Design Agent Final Validation:**
- **YOU must use Playwright MCP** to perform comprehensive visual testing
- Test all pages at multiple viewports (mobile, tablet, desktop, wide)
- Verify all design issues have been fixed
- Check accessibility compliance (contrast, keyboard navigation, screen reader compatibility)
- Validate consistent design system usage across all interfaces
- Test print styles and responsive images
- Capture final screenshots for visual regression baseline

**Cross-Agent Integration Testing:**
- All Playwright MCP agents coordinate to test scenarios involving multiple user types
- Test admin actions affecting user experience (e.g., admin creates content, user views it)
- Verify real-time updates and notifications between different user interfaces
- Test permission boundaries and access control from both perspectives
- Ensure design consistency between user and admin interfaces

**Performance and Security Validation:**
- **Performance benchmarks** established through repeated Playwright MCP testing
- **Security validation** completed by testing unauthorized access attempts
- **Direct Web Testing**: YOU must verify every web feature works through direct browser interaction

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
- **User Interfaces**: {user_page_count}
- **Admin Interfaces**: {admin_page_count}
- **Payment Integration**: {payment_system_detected}
- **Authentication Systems**: {auth_systems_found}
- **Sandbox/Test Credentials**: {test_credentials_found}

## Test Execution Summary
- **Total Tests**: {test_count}
- **Playwright MCP Tests**: {web_test_count}
- **User Workflow Tests**: {user_test_count}
- **Admin Workflow Tests**: {admin_test_count}
- **Payment Integration Tests**: {payment_test_count}
- **Passed**: {passed_count}
- **Failed**: {failed_count}
- **Issues Found**: {issue_count}
- **Issues Fixed**: {fixed_count}

## Playwright MCP Agent Performance
- **User Agent**: {user_agent_performance}
  - Pages Tested: {user_pages_tested}
  - Workflows Completed: {user_workflows_completed}
  - Screenshots Captured: {user_screenshots_count}
- **Admin Agent**: {admin_agent_performance}
  - Admin Functions Tested: {admin_functions_tested}
  - Management Workflows: {admin_workflows_completed}
  - Permission Tests: {admin_permission_tests}
- **Payment Agent**: {payment_agent_performance}
  - Payment Scenarios Tested: {payment_scenarios_tested}
  - Sandbox Transactions: {sandbox_transactions_completed}
  - Integration Points Verified: {payment_integrations_tested}

## Issues Summary
{Summary of all issues found and resolved}

## Performance Metrics
{Response times, throughput, resource usage}

## Security Assessment
{Security test results and recommendations}

## Web Testing Insights (AI-Enhanced)
- **User Experience Issues**: {UX_issues_found}
  - Critical Path Problems: {issues_on_checkout_login_etc}
  - Usability Violations: {clarity_efficiency_trust_issues}
  - User Impact Severity: {high_medium_low_breakdown}
- **Design Pattern Analysis**: {AI_pattern_recognition_findings}
  - Anti-patterns Detected: {common_UI_mistakes_found}
  - Best Practice Violations: {design_principle_violations}
  - Improvement Opportunities: {AI_suggested_enhancements}
- **Accessibility Compliance**: {WCAG_compliance_results}
  - Contrast Issues: {low_contrast_elements}
  - Keyboard Navigation: {keyboard_accessibility_problems}
  - Screen Reader Compatibility: {aria_label_issues}
- **Cross-Platform Compatibility**: {browser_compatibility_results}
- **Mobile Responsiveness**: {mobile_testing_results}
  - Touch Target Issues: {small_button_problems}
  - Viewport Problems: {overflow_scrolling_issues}

## Recommendations
- **User Interface Improvements**: {UI_improvement_suggestions}
- **Admin Panel Enhancements**: {admin_improvement_suggestions}
- **Payment Flow Optimizations**: {payment_improvement_suggestions}
- **Security Enhancements**: {security_recommendations}
- **Performance Optimizations**: {performance_recommendations}
```

### 8. Success Criteria

The `/test-system` command succeeds when:
1. ✅ Complete system analysis and architecture mapping
2. ✅ All components, user interfaces, and admin interfaces identified
3. ✅ Sandbox/test credentials discovered and utilized
4. ✅ Multiple specialized Playwright MCP agents deployed (User, Admin, Payment)
5. ✅ **YOU used Playwright MCP** for comprehensive web testing from multiple perspectives
6. ✅ All user workflows tested end-to-end through direct browser interaction
7. ✅ All admin functions tested through direct admin interface interaction
8. ✅ Payment flows tested with sandbox credentials and test payment methods
9. ✅ All issues discovered and documented with screenshots and browser evidence
10. ✅ **Fixer Agent uses MCP research** (Perplexity, Brave, Context7) to fix all issues
11. ✅ **Test → Fix → Check loop** continues until all issues RESOLVED
12. ✅ Cross-perspective validation completed (user/admin/payment coordination)
13. ✅ Complete system validation passes with all features working
14. ✅ Comprehensive test report generated with web testing insights and fix documentation

### 9. Research Documentation

Save all findings to `/research/system-testing/` and if this folder doesnt exist, make it:
- `complete-system-analysis.md` - Comprehensive system inventory and architecture
- `existing-research-utilized.md` - Summary of existing research that was leveraged
- `web-interface-analysis.md` - Complete catalog of user and admin interfaces
- `sandbox-credentials-found.md` - Documentation of test/sandbox credentials discovered
- `playwright-testing-strategy.md` - Multi-agent web testing approach and coordination
- `user-agent-report.md` - Detailed user workflow testing results
- `admin-agent-report.md` - Detailed admin interface testing results
- `payment-agent-report.md` - Detailed payment integration testing results
- `fixer-agent-report.md` - All fixes applied with MCP research documentation
- `fix-research-log.md` - Perplexity queries, Brave searches, Context7 lookups for each fix
- `test-fix-check-cycles.md` - Documentation of all test→fix→check iterations
- `cross-perspective-validation.md` - Results of coordinated multi-agent testing
- `web-performance-data/` - Performance test results from browser testing
- `security-assessment.md` - Security test findings including permission testing
- `screenshot-evidence/` - All screenshots captured during testing
- `integration-points.md` - Analysis of all system integration points

## Example Usage

```bash
/test-system
```

This will:
1. Analyze the entire codebase to understand the system architecture
2. Discover all user and admin interfaces, payment integrations, and sandbox credentials
3. Research appropriate testing strategies for the discovered technology stack
4. Deploy multiple specialized Playwright MCP agents (User, Admin, Payment) + Fixer Agent
5. **YOU will use Playwright MCP** to directly test all web functionality from multiple perspectives
6. Test complete user journeys, admin workflows, and payment processes
7. **Fixer Agent uses MCP research** (Perplexity, Brave, Context7) to fix ALL discovered issues
8. **Test → Fix → Check loop** continues until every feature works correctly
9. Generate comprehensive test report with web testing insights, fix documentation, and recommendations

## Key Features

- **Automatic System Discovery**: No manual configuration needed
- **Technology-Aware Testing**: Adapts to discovered tech stack
- **Playwright MCP Integration**: YOU must directly test all web functionality - never assume it works
- **Multi-Agent Coordination**: Parallel testing with communication between User, Admin, Payment, and Fixer agents
- **MCP-Powered Issue Resolution**: Fixer Agent uses Perplexity, Brave Search, and Context7 to research and fix all issues
- **Test → Fix → Check Loop**: Continuous cycle until all features work correctly
- **Comprehensive Reporting**: Detailed analysis with fix documentation and recommendations
- **Direct Web Testing**: YOU must interact with and test websites yourself using Playwright MCP
- **Research-Driven Fixes**: Every fix is based on MCP tool research, not guesswork