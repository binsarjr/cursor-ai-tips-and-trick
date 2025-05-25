# ✅ Best Practices & ⚠️ Common Pitfalls

Panduan untuk menghindari kesalahan umum dan mengoptimalkan penggunaan Cursor AI.

## ✅ Best Practices

### 1. Context Management

#### ✅ Do: Gradual Context Building
```
Step 1: "I'm building a user management system for a SaaS app"
Step 2: "Here's the current User model: @types/user.ts"
Step 3: "Now I want to add role-based permissions..."
```

#### ❌ Don't: Context Overload
```
❌ "Here are 15 files, please understand everything and build a complete authentication system with OAuth, 2FA, role management, audit logs, and password policies"
```

### 2. Request Specificity

#### ✅ Do: Specific, Actionable Requests
```
✅ "Refactor the calculatePrice function in @utils/pricing.ts to handle discount codes. It should:
- Accept a discountCode parameter
- Validate the code against our discount rules
- Apply percentage or fixed amount discounts
- Return both original and discounted prices"
```

#### ❌ Don't: Vague Requests
```
❌ "Make the pricing better"
❌ "Fix this bug"
❌ "Improve performance"
```

### 3. Error Communication

#### ✅ Do: Complete Error Information
```
✅ Error in checkout process:

Steps to reproduce:
1. Add item to cart
2. Proceed to checkout
3. Enter payment details
4. Click "Pay Now"

Error message:
```
TypeError: Cannot read property 'total' of undefined
    at processPayment (checkout.ts:45)
    at handleSubmit (CheckoutForm.tsx:123)
```

Expected: Order should be processed successfully
Environment: Chrome 119, macOS, Production
```

#### ❌ Don't: Incomplete Error Reporting
```
❌ "Payment not working, help fix"
```

### 4. Code Quality Requests

#### ✅ Do: Specify Quality Criteria
```
✅ "Review this React component for:
- Performance optimization (memo, useMemo, useCallback)
- Accessibility (ARIA labels, keyboard navigation)
- TypeScript strictness
- Error boundary integration
- Mobile responsiveness"
```

#### ❌ Don't: Generic Quality Requests
```
❌ "Make this code better"
```

### 5. Testing Integration

#### ✅ Do: Test-First Approach
```
✅ "Write unit tests for the shopping cart functionality first, then implement:
- Add item to cart
- Remove item from cart
- Update quantity
- Calculate total with taxes
- Apply discount codes

Test framework: Jest + React Testing Library"
```

#### ❌ Don't: Afterthought Testing
```
❌ "Here's my finished code, now add some tests"
```

## ⚠️ Common Pitfalls

### 1. The "One-Shot" Trap

#### ❌ Pitfall:
```
"Please build a complete e-commerce application with user authentication, product catalog, shopping cart, payment processing, admin panel, and inventory management."
```

#### ✅ Solution:
```
Break into smaller iterations:
1. "Set up basic project structure with authentication"
2. "Add product catalog with search functionality"
3. "Implement shopping cart with state management"
4. "Integrate payment processing"
etc.
```

### 2. The "Magic Code" Trap

#### ❌ Pitfall:
Accepting generated code without understanding it.

#### ✅ Solution:
```
"Please explain how this authentication middleware works:
1. What security measures does it implement?
2. How does the token validation work?
3. What are the potential security vulnerabilities?
4. How should I test this in different scenarios?"
```

### 3. The "Context Loss" Trap

#### ❌ Pitfall:
Starting new conversations for related tasks without providing context.

#### ✅ Solution:
```
Maintain context with:
- Reference previous work: "Building on the auth system we created earlier..."
- Use file references: "@components/auth/LoginForm.tsx that we just built"
- Provide project context: "This is for the SaaS dashboard we're building"
```

### 4. The "Copy-Paste" Trap

#### ❌ Pitfall:
Directly copying generated code without adaptation to your project.

#### ✅ Solution:
```
"Adapt this authentication solution for our project:
- We use Supabase instead of Firebase
- Our user model has additional fields: company, role
- We need to integrate with our existing Redux store
- Follow our TypeScript strict configuration"
```

### 5. The "Over-Engineering" Trap

#### ❌ Pitfall:
```
AI: "I'll implement this with microservices architecture, event sourcing, CQRS, distributed caching, and auto-scaling containers..."
You: "Um, it's just a todo app..."
```

#### ✅ Solution:
```
"Implement a simple todo app with:
- Basic CRUD operations
- Local storage persistence
- Simple, clean UI
- No complex architecture needed
- Focus on code clarity over fancy patterns"
```

## 🛡️ Quality Assurance Practices

### 1. Code Review Checklist

Always ask AI to review for:
```
- Security vulnerabilities
- Performance implications
- Error handling completeness
- TypeScript type safety
- Testing coverage
- Documentation quality
- Accessibility compliance
- Mobile responsiveness
```

### 2. Testing Strategy
```
For each feature, request:
1. Unit tests for individual functions
2. Integration tests for API endpoints
3. Component tests for React components
4. E2E tests for critical user flows
5. Error scenario testing
```

### 3. Documentation Standards
```
Ensure AI provides:
- Clear function/component descriptions
- Usage examples
- Parameter documentation
- Error handling instructions
- Performance considerations
```

## 🎯 Productivity Optimization

### 1. Template Usage
```
✅ Create reusable templates for:
- Feature requests
- Bug reports
- Code reviews
- Testing scenarios
- Documentation requests
```

### 2. Batching Related Tasks
```
✅ Instead of separate requests:
"Create login component"
"Add form validation"
"Add error handling"
"Add loading states"

✅ Batch together:
"Create login component with form validation, error handling, loading states, and TypeScript types"
```

### 3. Incremental Improvement
```
✅ Build iteratively:
Phase 1: Basic functionality
Phase 2: Error handling
Phase 3: Performance optimization
Phase 4: Advanced features
Phase 5: Testing & documentation
```

## 🔍 Debugging Best Practices

### 1. Systematic Approach
```
When reporting bugs:
1. Minimal reproduction case
2. Expected vs actual behavior
3. Environment details
4. Error messages with stack traces
5. Recent changes that might be related
```

### 2. Performance Issues
```
For performance problems:
1. Specific metrics (load time, bundle size, etc.)
2. Profiling data
3. User scenarios affected
4. Baseline measurements
5. Target performance goals
```

### 3. Integration Issues
```
For integration problems:
1. API endpoints involved
2. Data flow description
3. Authentication/authorization details
4. Error responses
5. Network timing issues
```

## 🎨 UI/UX Considerations

### 1. Design System Integration
```
✅ "Create this component following our design system:
- Use our color tokens: primary-500, gray-100
- Follow spacing scale: 8px grid system
- Match our typography: font-sans, text-sm
- Include dark mode support
- Ensure mobile-first responsive design"
```

### 2. Accessibility Requirements
```
✅ Always specify:
- ARIA labels and roles
- Keyboard navigation support
- Screen reader compatibility
- Color contrast compliance
- Focus management
```

### 3. Performance Considerations
```
✅ Request optimization for:
- Bundle size impact
- Render performance
- Image optimization
- Lazy loading implementation
- Critical path prioritization
```

## 📊 Success Metrics

### Track Effectiveness:
```
✅ Measure:
- Time saved in development
- Code quality improvements
- Bug reduction rate
- Test coverage increase
- Documentation completeness
- Team productivity gains
```

### Red Flags to Watch:
```
⚠️ Warning signs:
- Constantly fixing AI-generated code
- Unable to understand generated solutions
- Skipping testing due to complexity
- Over-engineering simple problems
- Ignoring security best practices
```

## 🎓 Continuous Learning

### 1. Stay Updated
```
- Follow Cursor AI updates and new features
- Learn about AI prompting best practices
- Understand your tech stack deeply
- Practice with different prompt styles
```

### 2. Share Knowledge
```
- Document successful prompt patterns
- Share with team members
- Create internal best practices guide
- Build organization-specific templates
```

### 3. Iterate and Improve
```
- Regularly review and refine your approach
- Experiment with new techniques
- Collect feedback from team members
- Adapt to project-specific needs
```

---

## 🚀 Action Items

### Immediate Steps:
1. ✅ Create your first prompt template
2. ✅ Set up proper file organization
3. ✅ Define project-specific context rules
4. ✅ Establish code review practices

### Weekly Habits:
1. ✅ Review and refine successful prompts
2. ✅ Update project context documentation
3. ✅ Share learnings with team
4. ✅ Practice new prompting techniques

### Monthly Reviews:
1. ✅ Assess productivity improvements
2. ✅ Update templates and best practices
3. ✅ Evaluate tool effectiveness
4. ✅ Plan skill development

---

**Remember**: AI is a powerful amplifier - it amplifies both good practices and bad ones. Focus on building strong fundamentals first! 🎯 