# 🚀 Quick Reference - Cursor AI Tips & Tricks

Referensi cepat untuk tips dan trik Cursor AI yang paling sering digunakan.

## 🎯 Essential Prompt Starters

### For Feature Development
```
"Saya need to build [feature] for [project type]. 
Tech stack: [list technologies].
Requirements: [list key requirements].
Please provide implementation with TypeScript, tests, and error handling."
```

### For Bug Fixing
```
"I'm getting this error: [paste error message]
In file: [filename] at line [number]
Expected behavior: [describe expected]
Current behavior: [describe actual]
Please help debug and fix this issue."
```

### For Code Review
```
"Please review this code for:
- Security vulnerabilities
- Performance issues  
- Best practices compliance
- Potential bugs
- Improvement suggestions"
```

### For Refactoring
```
"Please refactor this code to:
- Improve readability
- Better error handling
- Add TypeScript types
- Follow [specific pattern]
- Maintain existing functionality"
```

## 🔧 Context Management Quick Tips

### ✅ DO
- Open relevant files before asking
- Use `@filename` to reference specific files
- Provide business context and constraints
- Explain the "why" behind your request
- Share complete error messages
- Mention your tech stack explicitly

### ❌ DON'T
- Ask vague questions like "fix this"
- Skip providing error details
- Forget to mention constraints
- Assume AI knows your project context
- Copy-paste huge blocks of code unnecessarily

## 📁 Cursor Rules Quick Setup

### 1. Basic Project Rules (`.cursor/rules/project-basics.mdc`)
```markdown
# Project: [Your Project Name]
# Type: [Web app/API/Mobile app]
# Tech Stack: [React, TypeScript, Node.js, etc.]

## Coding Standards
- Use TypeScript with strict mode
- Prefer functional components and hooks
- Follow conventional commit messages
- Include error handling in all functions
- Write tests for business logic

## File Organization
- Components in `/components`
- Business logic in `/hooks` or `/services`
- Types in `/types`
- Constants in `/constants`
```

### 2. Domain Knowledge (`.cursor/rules/domain.mdc`)
```markdown
# Business Domain: [E-commerce/Fintech/SaaS/etc.]

## Target Users
- [Primary user type and characteristics]
- [Secondary user type and characteristics]

## Key Business Rules
- [Important business rule 1]
- [Important business rule 2]
- [Important business rule 3]

## Technical Constraints
- [Performance requirements]
- [Security requirements]
- [Browser/device support]
```

## 🚀 Productivity Shortcuts

### File References
```
"Looking at @components/Button.tsx and @styles/theme.ts"
"Based on the pattern in @services/api.ts"
"Following the structure from @types/user.ts"
```

### Progressive Context Building
```
Step 1: "I'm building an e-commerce checkout flow"
Step 2: "Using React + TypeScript + Stripe integration"  
Step 3: "Need to handle payment validation and error states"
Step 4: "Following our existing pattern from @components/PaymentForm.tsx"
```

### Template Requests
```
"Create a [component/function/service] similar to [existing example]
but adapted for [specific use case]"
```

## 🎨 Common Request Patterns

### Component Creation
```
"Create a React component for [purpose] with:
- TypeScript props interface
- Responsive design (mobile-first)
- Loading and error states
- Accessibility features (ARIA labels)
- Jest/Testing Library tests"
```

### API Integration
```
"Create an API service for [feature] that:
- Uses our existing fetch wrapper from @services/api.ts
- Includes proper TypeScript types
- Handles errors gracefully
- Includes loading states
- Has retry logic for failures"
```

### Database Operations
```
"Create database operations for [entity] using [Prisma/TypeORM]:
- CRUD operations with proper types
- Input validation with [Zod/Joi]
- Error handling for constraints
- Optimized queries with relations
- Transaction support where needed"
```

## 🔍 Debugging Shortcuts

### Error Analysis
```
"This error suggests [your analysis]. 
The issue seems to be in [file/function].
Based on our codebase pattern, the fix should involve [approach].
Please confirm and provide the solution."
```

### Performance Issues
```
"The [component/page] is slow. I've profiled and found:
- [Specific metric: load time, bundle size, etc.]
- [Suspected cause]
Please suggest optimizations following our performance patterns."
```

### Integration Problems
```
"The integration between [service A] and [service B] is failing.
API response: [paste response]
Expected format: [describe expected]
Please help debug the data transformation."
```

## 🎯 Quality Assurance Checklist

### Before Requesting Code
- [ ] Have I provided enough context?
- [ ] Are relevant files open?
- [ ] Have I explained the business need?
- [ ] Did I mention constraints/requirements?

### After Receiving Code
- [ ] Does it follow our project patterns?
- [ ] Are TypeScript types included?
- [ ] Is error handling implemented?
- [ ] Are tests included/needed?
- [ ] Does it meet performance requirements?

### Before Committing
- [ ] Code reviewed and tested
- [ ] Follows naming conventions
- [ ] Documentation updated if needed
- [ ] No security vulnerabilities
- [ ] Matches existing code style

## 📊 Success Metrics to Track

### Weekly
- ✅ Features completed with AI assistance
- ✅ Time saved on coding tasks
- ✅ Number of iterations needed per request
- ✅ Code review feedback volume

### Monthly  
- 📈 Development velocity improvement
- 📈 Code quality metrics
- 📈 Bug rate reduction
- 📈 Team satisfaction with AI assistance

## 🚨 Common Pitfalls to Avoid

### The "One-Shot Trap"
❌ Expecting perfect code in one request
✅ Iterate and refine through conversation

### The "Magic Code Trap"  
❌ Using AI code without understanding
✅ Ask for explanations of complex parts

### The "Over-Engineering Trap"
❌ Requesting overly complex solutions
✅ Start simple, add complexity gradually

### The "Context Amnesia"
❌ Starting fresh conversation for related tasks
✅ Build on previous context in same session

## 🔗 Quick Links

- [📝 Prompt Templates](../examples/prompt-templates.md)
- [🎯 Advanced Techniques](../examples/advanced-techniques.md)
- [📋 Best Practices Guide](best-practices-and-pitfalls.md)
- [📜 Comprehensive Rules Guide](cursor-rules-comprehensive.md)
- [📖 Main README](../README.md)

---

**💡 Pro Tip**: Bookmark this page and reference it before starting complex AI conversations. The few minutes spent setting up context properly will save hours of back-and-forth! 🚀 