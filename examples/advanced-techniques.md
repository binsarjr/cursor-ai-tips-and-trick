# 🎯 Advanced Techniques untuk Cursor AI

Teknik-teknik lanjutan untuk memaksimalkan produktivitas dengan Cursor AI Agent.

## 🔗 Multi-File Context Management

### 1. File Referencing Strategy
```
Saya sedang refactor authentication system yang melibatkan:
- @components/auth/LoginForm.tsx - Form login utama
- @hooks/useAuth.ts - Custom hook untuk auth state
- @utils/authHelpers.ts - Helper functions
- @types/auth.ts - Type definitions

Please analyze the current implementation dan suggest improvements untuk:
1. Better error handling
2. Improved TypeScript types
3. More efficient state management
```

### 2. Cross-File Dependencies
```
Update the user management system:

1. Modify @types/user.ts to add 'lastLoginDate' field
2. Update @api/users.ts to handle the new field in API calls
3. Modify @components/UserProfile.tsx to display last login
4. Update @hooks/useUser.ts to track login timestamps
5. Add migration in @db/migrations/ for database schema

Please ensure all changes are consistent across files.
```

## 🧠 Context Accumulation Techniques

### 1. Progressive Context Building
```
Phase 1: "Let me show you the current user authentication flow"
[Show relevant files]

Phase 2: "Now I want to add two-factor authentication. Based on the existing flow, how should we implement this?"

Phase 3: "Great! Now let's also add social login options. How can we integrate this with the 2FA system we just designed?"
```

### 2. Context Anchoring
```
CONTEXT ANCHOR:
This is an e-commerce platform for Indonesian SMEs.
- Target users: Small business owners (non-technical)
- Main features: Inventory, orders, customer management
- Tech stack: Next.js, TypeScript, Prisma, PostgreSQL
- UI: Simple, mobile-first, Indonesian language

Now, with this context in mind: [your specific request]
```

## 🎨 Advanced Prompt Patterns

### 1. The "Rubber Duck" Pattern
```
I'm going to explain my current problem as if you're a rubber duck, then ask for your expert input:

"I have this weird bug where user sessions expire randomly. I think it might be related to how I'm handling JWT tokens, but I'm not sure. The weird thing is it only happens in production, not in development..."

Now, as a senior developer, what questions would you ask me to debug this? And what are the most likely causes?
```

### 2. The "Architect Review" Pattern
```
Please put on your architect hat dan review this system design:

Current Architecture:
[Describe current state]

Proposed Changes:
[Describe what you want to change]

Please evaluate from these perspectives:
1. Scalability: Will this handle 10x traffic?
2. Maintainability: How will this affect code complexity?
3. Performance: Any potential bottlenecks?
4. Security: Are there any vulnerabilities?
5. Cost: Resource implications?

Provide a recommendation with pros/cons dan alternative approaches.
```

### 3. The "Pair Programming" Pattern
```
Let's pair program on this feature. I'll implement the basic structure, you help me refine it:

My initial approach:
[Paste your initial code]

Your turn: What improvements do you see? Let's iterate on this together, focusing on:
- Code quality dan readability
- Performance optimizations
- Error handling
- Testing strategy
```

## 🔄 Iterative Development Workflow

### 1. Red-Green-Refactor with AI
```
RED PHASE:
Write a failing test for [feature description]:
- Test should cover [specific scenario]
- Include edge cases for [edge case]
- Mock dependencies like [dependency list]

GREEN PHASE:
Implement minimal code to make the test pass

REFACTOR PHASE:
Now improve the implementation:
- Better error handling
- Performance optimization
- Code organization
- Documentation
```

### 2. Feature Flag Development
```
Implement [feature] using feature flags:

1. Create feature flag configuration
2. Implement feature behind flag
3. Add A/B testing capability
4. Include rollback strategy
5. Add monitoring dan metrics

Environment strategy:
- Development: Always enabled
- Staging: Configurable
- Production: Gradual rollout

Please include TypeScript types dan proper testing.
```

## 🎭 Role-Based AI Interactions

### 1. The Security Expert
```
🛡️ SECURITY REVIEW MODE ACTIVATED

Please review this authentication implementation as a security expert:

[Code or description]

Check for:
- OWASP Top 10 vulnerabilities
- JWT implementation best practices
- Password handling security
- Session management issues
- Input validation gaps
- Authorization flaws

Provide:
- Risk assessment (High/Medium/Low)
- Specific vulnerabilities found
- Mitigation strategies
- Secure implementation examples
```

### 2. The Performance Engineer
```
⚡ PERFORMANCE OPTIMIZATION MODE

Analyze this code for performance issues:

[Code or description]

Focus areas:
- Algorithm complexity
- Memory usage patterns
- Database query optimization
- Bundle size impact
- Runtime performance
- Caching opportunities

Provide:
- Performance metrics predictions
- Optimization recommendations
- Alternative implementations
- Monitoring suggestions
```

### 3. The UX Designer
```
🎨 UX DESIGN MODE

Review this user interface from a UX perspective:

[Component or flow description]

Evaluate:
- User journey flow
- Accessibility compliance
- Mobile responsiveness
- Loading states
- Error states
- User feedback mechanisms

Consider our users: [user persona description]

Suggest improvements for:
- Usability
- Accessibility
- Performance perception
- Error prevention
- User delight factors
```

## 🔬 Advanced Debugging Techniques

### 1. Systematic Bug Analysis
```
🐛 SYSTEMATIC DEBUG ANALYSIS

Bug: [Description]

Let's debug this systematically:

STEP 1: Reproduce the issue
- Minimal reproduction steps
- Environment details
- Input data that triggers bug

STEP 2: Isolate the problem
- Which component/function is involved?
- What's the data flow?
- Where does it break?

STEP 3: Hypothesis formation
- What could cause this behavior?
- List 3-5 potential causes
- Order by probability

STEP 4: Testing hypotheses
- How to test each hypothesis?
- What evidence would confirm/deny each?

STEP 5: Solution implementation
- Fix the root cause
- Add preventive measures
- Update tests

Guide me through this process.
```

### 2. Performance Profiling
```
🔍 PERFORMANCE PROFILING SESSION

Target: [Component/function/page]

Current metrics:
- [Baseline measurements]

Let's profile step by step:

1. Identify bottlenecks
2. Measure before optimization
3. Apply optimizations
4. Measure after optimization
5. Validate improvements

Tools to use:
- Browser DevTools
- React DevTools Profiler
- Lighthouse
- Bundle analyzer

Please guide me through this process with specific commands dan checkpoints.
```

## 🏗️ Architecture Design Patterns

### 1. Event-Driven Architecture
```
🏗️ DESIGN EVENT-DRIVEN SYSTEM

Requirements: [System requirements]

Design an event-driven architecture including:

1. Event Definition
   - Event types dan schemas
   - Event naming conventions
   - Payload structures

2. Event Bus Implementation
   - Message broker choice
   - Topic organization
   - Partitioning strategy

3. Event Handlers
   - Handler registration
   - Error handling
   - Retry mechanisms

4. Monitoring & Observability
   - Event tracking
   - Performance metrics
   - Error monitoring

Include TypeScript types, implementation examples, dan testing strategies.
```

### 2. Microservices Communication
```
🔗 MICROSERVICES COMMUNICATION DESIGN

Services involved:
- [Service 1]: [Description]
- [Service 2]: [Description]
- [Service 3]: [Description]

Design communication patterns:

1. Synchronous Communication
   - REST APIs
   - GraphQL
   - gRPC

2. Asynchronous Communication
   - Message queues
   - Event streaming
   - Webhooks

3. Data Consistency
   - SAGA patterns
   - Event sourcing
   - CQRS implementation

4. Error Handling
   - Circuit breakers
   - Retry policies
   - Fallback strategies

Provide implementation examples dan trade-off analysis.
```

## 🎯 Domain-Specific Techniques

### 1. E-commerce Specific
```
🛒 E-COMMERCE CONTEXT MODE

Working on e-commerce platform for [target market].

Key considerations:
- Payment processing (Indonesian payment gateways)
- Inventory management
- Order fulfillment
- Customer experience
- Mobile-first approach

Apply e-commerce best practices to: [your request]

Include:
- Payment security
- Inventory accuracy
- Performance optimization
- SEO considerations
- Conversion optimization
```

### 2. Fintech Specific
```
💰 FINTECH CONTEXT MODE

Building financial application with:
- Regulatory compliance requirements
- High security standards
- Audit trail needs
- Real-time processing
- Data accuracy critical

Apply fintech best practices to: [your request]

Include:
- Security measures
- Compliance checks
- Audit logging
- Error handling
- Transaction integrity
```

## 🧪 Testing Strategies

### 1. Test-Driven Development with AI
```
🧪 TDD WITH AI ASSISTANCE

Feature: [Feature description]

TDD Cycle:
1. Write failing test (RED)
2. Implement minimal code (GREEN)  
3. Refactor dan improve (REFACTOR)

Let's start:

RED: Write comprehensive tests for:
- Happy path scenarios
- Edge cases
- Error conditions
- Integration points

Please generate test cases first, then we'll implement.
```

### 2. Property-Based Testing
```
🎲 PROPERTY-BASED TESTING

Function to test: [Function description]

Generate property-based tests that verify:
- Function properties that should always hold
- Invariants that must be maintained
- Relationship between inputs dan outputs
- Edge case generation strategies

Use property-based testing library dan provide:
- Property definitions
- Generator functions
- Test execution strategies
- Shrinking examples for failures
```

## 💡 Pro Tips

### 1. Context Preservation
- Save successful prompts dalam file
- Create prompt libraries untuk different scenarios
- Use consistent terminology across conversations
- Build conversation templates untuk complex tasks

### 2. Efficiency Maximization
- Batch related requests together
- Use file references instead of copy-pasting
- Leverage AI memory for ongoing conversations
- Create shortcuts untuk frequently used patterns

### 3. Quality Assurance
- Always review generated code before applying
- Test AI suggestions in isolated environments
- Cross-reference with official documentation
- Validate security implications

---

**Master Tip**: Treat AI as your senior pair programming partner. Be explicit about your thought process, ask for explanations when needed, dan don't hesitate to challenge suggestions! 🚀 