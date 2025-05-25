# 🎯 Context Management dan Prompt Engineering

Panduan lengkap untuk mengelola context dan membuat prompt yang efektif untuk Cursor AI.

## 🎯 Context Management

Context adalah kunci sukses dalam berinteraksi dengan AI. Semakin jelas dan relevan context yang diberikan, semakin akurat dan berguna response yang akan diterima.

### 1. Berikan Context yang Jelas

**❌ Tidak efektif:**
```
"Perbaiki bug ini"
```

**✅ Efektif:**
```
"Ada bug di fungsi calculateTotal() di file utils/pricing.ts. 
Ketika discount lebih dari 50%, hasil kalkulasi menjadi negatif. 
Expected behavior: minimum total adalah 0."
```

### 2. Include Relevant Files
- Buka file yang relevan sebelum bertanya
- Gunakan `@filename` untuk reference spesifik file
- Share error messages lengkap dengan stack trace

### 3. Provide Business Context
```
"Ini adalah e-commerce app untuk UMKM. 
Fitur yang sedang dikembangkan: sistem inventory management.
Target user: pemilik toko kecil yang tidak tech-savvy."
```

### 4. Progressive Context Building

Context building yang efektif dilakukan secara bertahap:

```
Step 1: "Saya sedang membuat authentication system untuk e-commerce app"
Step 2: "Tech stack: Next.js, TypeScript, Prisma, PostgreSQL"
Step 3: "Need to implement JWT-based auth dengan refresh token"
Step 4: "Security requirements: rate limiting, password hashing"
```

## 💬 Prompt Engineering

Prompt yang well-structured menghasilkan output yang lebih akurat dan actionable.

### 1. Template-Based Prompts

#### Template untuk Feature Development
```
Context: [Jelaskan fitur yang ingin dibuat]
Requirements: 
- [Requirement 1]
- [Requirement 2]
- [Requirement 3]

Tech Stack: [List teknologi yang digunakan]
Constraints: [Batasan atau limitasi]
Expected Output: [Format output yang diinginkan]
```

**Contoh Penggunaan:**
```
Context: Membuat sistem notifikasi real-time untuk aplikasi chat
Requirements:
- Support multiple notification types (message, call, system)
- Real-time delivery menggunakan WebSocket
- Offline storage untuk missed notifications
- Push notifications untuk mobile users

Tech Stack: React, TypeScript, Socket.io, Node.js, MongoDB
Constraints: Harus handle 1000+ concurrent users, mobile-first design
Expected Output: Component implementation, backend service, dan setup guide
```

#### Template untuk Bug Fixing
```
Bug Description: [Jelaskan bug yang terjadi]
Steps to Reproduce:
1. [Step 1]
2. [Step 2]
3. [Step 3]

Expected Behavior: [Apa yang seharusnya terjadi]
Actual Behavior: [Apa yang sebenarnya terjadi]
Error Messages: [Copy-paste error message lengkap]
Environment: [Browser, OS, Node version, etc.]
Additional Context: [File yang terkait, recent changes, etc.]
```

#### Template untuk Code Review
```
Changes Made:
- [Change 1]
- [Change 2]

Review Focus:
- [Security implications]
- [Performance impact]
- [Breaking changes]

Testing Done:
- [Test scenarios covered]
```

#### Template untuk Performance Optimization
```
Performance Issue: [Describe the performance problem]
Current Metrics:
- [Load time: X seconds]
- [Bundle size: X MB]
- [Memory usage: X MB]

Target Metrics:
- [Target load time]
- [Target bundle size]
- [Target memory usage]

Constraints: [Browser support, backwards compatibility, etc.]
```

### 2. Advanced Prompt Patterns

#### The Iterative Refinement Pattern
```
"Let's start with a basic implementation of [feature], 
then iteratively improve it by adding:
1. Error handling
2. TypeScript types
3. Tests
4. Performance optimizations"
```

#### The Comparison Pattern
```
"I have two approaches for [problem]:
Approach A: [describe approach]
Approach B: [describe approach]

Based on our project constraints [list constraints], 
which approach would be better and why?"
```

#### The Role-Playing Pattern
```
"Act as a senior React developer reviewing this component.
Focus on:
- Component design patterns
- Performance implications
- Accessibility considerations
- Maintainability concerns"
```

#### The Constraint-First Pattern
```
"Given these strict constraints:
- Must work on IE11
- Bundle size < 50KB
- No external dependencies
- Load time < 2 seconds

How would you implement [feature]?"
```

### 3. Context-Rich Communication

#### Multi-File Context Management
```
"Looking at the interaction between:
- @components/ProductCard.tsx (UI component)
- @services/productService.ts (data layer)
- @hooks/useProducts.ts (state management)

I need to add filtering functionality yang consistent dengan existing patterns."
```

#### Business Context Integration
```
"This is for an Indonesian e-commerce platform where:
- 80% users are on mobile
- Payment methods: credit card, bank transfer, e-wallet
- Average transaction: 100K-500K IDR
- Peak traffic: 6-9 PM weekdays

The checkout flow needs to be optimized for conversion."
```

#### Technical Context Layering
```
"Current architecture:
- Frontend: Next.js 13 with App Router
- Backend: Node.js + Express + Prisma
- Database: PostgreSQL
- Deployment: Vercel + Railway
- State Management: Zustand + React Query

Adding real-time features, what's the best approach?"
```

## 🔄 Conversation Continuity

### 1. Building on Previous Context
```
"Following up on the authentication implementation we discussed earlier,
now I need to add authorization middleware untuk protected routes.
The middleware should integrate dengan JWT validation yang sudah kita buat."
```

### 2. Reference Previous Solutions
```
"Using the same pattern dari product pagination yang kita implement tadi,
how would you implement infinite scroll untuk comments section?"
```

### 3. Maintain Session Memory
```
"Based on our previous discussion tentang error handling patterns,
I'm now facing similar issue dengan file upload feature.
Should I apply the same Result<T, E> pattern here?"
```

## 🎨 Advanced Context Techniques

### 1. Domain-Specific Vocabulary
Establish dan gunakan vocabulary yang consistent:

```
"In our e-commerce domain:
- 'Product' = item yang dijual
- 'Variant' = different versions (size, color) of same product  
- 'SKU' = unique identifier per variant
- 'Inventory' = stock level per SKU
- 'Order' = customer purchase transaction
- 'Cart' = temporary collection before purchase"
```

### 2. Code Pattern References
```
"Following the repository pattern kita establish di @services/userRepository.ts,
create similar pattern untuk ProductRepository dengan:
- Same error handling approach
- Same caching strategy  
- Same TypeScript interface patterns"
```

### 3. Architectural Context
```
"Our clean architecture layers:
- Domain: business entities dan rules
- Application: use cases dan orchestration
- Infrastructure: external integrations
- Presentation: UI components dan API routes

This new feature should follow same layering."
```

## 🚀 Productivity Optimization

### 1. Quick Context Shortcuts
```
// File reference shortcuts
"Based on @utils/validation.ts patterns..."
"Following @components/Form.tsx structure..."
"Using @hooks/useApi.ts approach..."

// Business context shortcuts  
"For our UMKM e-commerce users..."
"Given mobile-first requirements..."
"Following accessibility standards..."
```

### 2. Template Combination
```
"Using bug fixing template:
Bug: Payment form validation not working
Reproduce: [steps]
Expected: Show validation errors
Actual: Form submits with invalid data

Plus performance context:
Form has 20+ fields, validation runs on every keystroke
Need debounced validation yang tidak block UI"
```

### 3. Iterative Development Prompts
```
Phase 1: "Create basic [feature] with core functionality"
Phase 2: "Add error handling dan loading states" 
Phase 3: "Optimize performance dan add animations"
Phase 4: "Add comprehensive tests dan documentation"
```

## 📊 Measuring Prompt Effectiveness

### Key Indicators
- **First Response Quality**: Apakah response pertama sudah actionable?
- **Iteration Count**: Berapa kali perlu clarification?
- **Code Accuracy**: Apakah code bisa langsung digunakan?
- **Context Retention**: Apakah AI memahami previous context?

### Success Metrics
```
✅ 80%+ prompts menghasilkan usable code pada attempt pertama
✅ Rata-rata <3 iterations untuk complex features
✅ AI consistently mengingat project context
✅ Generated code follows established patterns
✅ Minimal manual editing required
```

## 🎯 Best Practices Summary

### ✅ DO
- **Specific Context**: Always provide relevant business dan technical context
- **File References**: Open dan reference relevant files dengan @filename
- **Progressive Building**: Build context gradually across conversation
- **Template Usage**: Use structured templates untuk consistency
- **Clear Constraints**: Explicitly state limitations dan requirements
- **Error Details**: Include complete error messages dan stack traces

### ❌ DON'T
- **Vague Requests**: Avoid "fix this" atau "make it better" 
- **Context Switching**: Don't jump between unrelated topics in same session
- **Assumption Making**: Don't assume AI knows your specific setup
- **Copy-Paste Dumps**: Don't paste huge blocks tanpa explanation
- **Missing Constraints**: Don't forget to mention important limitations

---

**💡 Pro Tip**: Great prompts are like good user stories - they provide clear context, specific acceptance criteria, dan actionable requirements. Invest time dalam crafting prompts untuk exponential returns dalam development speed! 🚀 