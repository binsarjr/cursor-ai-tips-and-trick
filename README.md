# 🚀 Tips & Tricks Cursor AI Agent

Panduan lengkap untuk menggunakan Cursor AI Agent dengan lebih akurat dan efektif dalam proyek development.

## 📋 Daftar Isi
- [Setup Awal](#setup-awal)
- [Cursor Rules - The Power of Context](#cursor-rules---the-power-of-context)
  - [Mengapa Rules Sangat Penting](#mengapa-rules-sangat-penting)
  - [Jenis-Jenis Rules dan Manfaatnya](#jenis-jenis-rules-dan-manfaatnya)
  - [Advanced Rules Techniques](#advanced-rules-techniques)
  - [Measuring Rules Effectiveness](#measuring-rules-effectiveness)
  - [Implementing Rules Gradually](#implementing-rules-gradually)
- [Context Management](#context-management)
- [Prompt Engineering](#prompt-engineering)
- [File Organization](#file-organization)
- [Best Practices](#best-practices)
- [Advanced Tips](#advanced-tips)
- [Troubleshooting](#troubleshooting)
- [Measuring Success](#measuring-success)

## 🔧 Setup Awal

### 1. Konfigurasi `.cursor/` Directory
```
.cursor/
├── rules/          # Aturan khusus proyek
├── prompts/        # Template prompt yang sering digunakan
└── docs/           # Dokumentasi internal proyek
```

### 2. Environment Setup
- Pastikan workspace folder sudah ter-organize dengan baik
- Gunakan `.gitignore` yang tepat
- Buat struktur folder yang konsisten

## 📜 Cursor Rules - The Power of Context

Cursor Rules adalah file konfigurasi `.mdc` (Markdown) yang memberikan instruksi khusus kepada AI tentang bagaimana bekerja dengan proyek Anda. Rules ini adalah kunci untuk mendapatkan output yang konsisten dan sesuai dengan standar tim Anda.

### 🎯 Mengapa Rules Sangat Penting?

#### 1. **Konsistensi Code Quality**
- AI akan selalu mengikuti style guide yang sama
- Mengurangi variation dalam coding patterns
- Team members mendapat output yang predictable

#### 2. **Domain-Specific Knowledge**
- AI memahami business context proyek Anda
- Mengetahui constraints dan requirements khusus
- Menghasilkan solusi yang relevan dengan use case

#### 3. **Productivity Boost**
- Tidak perlu menjelaskan basic requirements setiap kali
- AI langsung tahu tech stack dan preferences
- Faster iteration dan less back-and-forth

### 🏗️ Jenis-Jenis Rules dan Manfaatnya

#### 1. **Technical Standards Rules**
```markdown
# .cursor/rules/technical-standards.mdc

## TypeScript Configuration
- Use strict mode: `"strict": true`
- Prefer interfaces over types untuk object shapes
- Always define return types untuk public functions
- Use meaningful generic names: `TUser` instead of `T`

## Error Handling Standards
- Always use Result<T, E> pattern untuk functions yang bisa fail
- Implement proper error boundaries dalam React components
- Log errors dengan structured format: timestamp, level, context
- Never swallow errors silently

## Performance Guidelines
- Lazy load components yang tidak immediate visible
- Implement virtualization untuk large lists (>100 items)
- Use React.memo untuk pure components
- Avoid inline functions dalam render methods
```

**Manfaat:**
- ✅ Code review yang lebih cepat karena AI sudah follow standards
- ✅ Bugs berkurang karena error handling yang konsisten
- ✅ Performance yang lebih baik dari awal
- ✅ Onboarding developer baru jadi lebih mudah

#### 2. **Business Domain Rules**
```markdown
# .cursor/rules/ecommerce-domain.mdc

## Business Context
This is an e-commerce platform untuk UMKM Indonesia dengan focus pada:
- Simplicity over feature richness
- Mobile-first experience (80% traffic from mobile)
- Integration dengan payment gateway lokal (Midtrans, QRIS)
- Multi-language support (Bahasa Indonesia primary)

## Key Business Rules
- Inventory harus real-time synchronized
- Price calculations must include tax (PPN 11%)
- Order status harus trackable dengan notification
- Support COD (Cash on Delivery) untuk area tertentu
- Product reviews only from verified purchases

## User Personas
- **Primary**: Pemilik toko kecil, usia 30-50, familiar basic smartphone
- **Secondary**: Staff toko, usia 20-35, tech-savvy
- Prioritize kemudahan penggunaan over advanced features
```

**Manfaat:**
- ✅ AI menghasilkan solutions yang sesuai target market
- ✅ Feature requests yang lebih practical dan relevant
- ✅ UX decisions yang aligned dengan user needs
- ✅ Business logic yang accurate dari first iteration

#### 3. **Architecture & Patterns Rules**
```markdown
# .cursor/rules/architecture.mdc

## Project Architecture
- Clean Architecture dengan Domain-Driven Design
- Folder structure: `/domain`, `/infrastructure`, `/application`, `/presentation`
- Dependency injection menggunakan inversify
- Repository pattern untuk data access

## State Management
- Zustand untuk client state (simple, lightweight)
- React Query untuk server state (caching, background updates)
- Context hanya untuk theme dan authentication
- Avoid prop drilling dengan custom hooks

## API Design
- RESTful endpoints dengan consistent naming
- Use HTTP status codes properly (200, 201, 400, 404, 500)
- Always return structured response: `{ success, data, error, metadata }`
- Implement pagination untuk list endpoints: `{ items, totalCount, hasNext }`
- API versioning dalam URL: `/api/v1/products`
```

**Manfaat:**
- ✅ Consistent architecture decisions across features
- ✅ Scalable codebase yang mudah di-maintain
- ✅ Team alignment pada technical choices
- ✅ Faster development karena AI tahu patterns yang digunakan

#### 4. **Testing Strategy Rules**
```markdown
# .cursor/rules/testing.mdc

## Testing Philosophy
- Test behavior, not implementation
- Minimum 80% code coverage untuk business logic
- Test pyramid: banyak unit tests, moderate integration, few e2e

## Testing Patterns
- **Unit Tests**: Jest + Testing Library
- **Integration Tests**: Supertest untuk API endpoints
- **E2E Tests**: Playwright untuk critical user journeys
- **Visual Tests**: Chromatic untuk UI components

## Test Structure
```javascript
describe('ProductService', () => {
  describe('when calculating discounts', () => {
    it('should apply percentage discount correctly', () => {
      // Arrange
      // Act  
      // Assert
    });
  });
});
```

## Mock Strategy
- Mock external APIs dengan msw (Mock Service Worker)
- Use test factories untuk data generation
- Reset mocks between tests
- Mock time-dependent functions (Date.now, setTimeout)
```

**Manfaat:**
- ✅ AI generates comprehensive test suites automatically
- ✅ Consistent testing patterns across team
- ✅ Better test coverage dan quality
- ✅ Faster debugging dengan reliable tests

#### 5. **Security & Compliance Rules**
```markdown
# .cursor/rules/security.mdc

## Security Standards
- Input validation pada semua user inputs
- SQL injection prevention dengan parameterized queries
- XSS protection dengan Content Security Policy
- CSRF protection untuk state-changing operations

## Authentication & Authorization
- JWT dengan short expiration (15 minutes) + refresh token
- Role-based access control (RBAC)
- Multi-factor authentication untuk admin users
- Password policy: minimum 8 characters, mixed case, numbers

## Data Protection
- Encrypt sensitive data at rest (PII, payment info)
- Log access ke sensitive endpoints
- Implement rate limiting (100 requests/minute per IP)
- Regular security audits dengan automated tools (OWASP ZAP)

## Compliance Requirements
- GDPR compliance untuk EU users
- PCI DSS untuk payment processing
- Audit trail untuk financial transactions
- Data retention policy (7 years untuk transaction data)
```

**Manfaat:**
- ✅ Security-first approach dalam semua features
- ✅ Compliance requirements met from day one
- ✅ Reduced security vulnerabilities
- ✅ Audit-ready codebase

### 🔧 Advanced Rules Techniques

#### 1. **Conditional Rules Berdasarkan File Type**
```markdown
# .cursor/rules/file-specific.mdc

## React Components (.tsx files)
- Always use TypeScript interfaces untuk props
- Implement proper error boundaries
- Use React.memo untuk performance optimization
- Include PropTypes untuk runtime validation (development only)

## API Routes (/api/* files)
- Always validate request body dengan Zod schemas
- Implement proper HTTP status codes
- Add request/response logging
- Include OpenAPI documentation comments

## Database Models (/models/* files)  
- Use Prisma schema dengan proper relations
- Include created_at dan updated_at timestamps
- Add soft delete capability dengan deleted_at field
- Implement proper indexes untuk query optimization
```

#### 2. **Environment-Specific Rules**
```markdown
# .cursor/rules/environment.mdc

## Development Environment
- Enable detailed error messages dan stack traces
- Use development-only debugging tools
- Allow CORS from localhost
- Mock external services untuk faster development

## Production Environment
- Minimal error messages (no stack traces)
- Enable comprehensive monitoring dan logging
- Strict CORS policy
- Rate limiting yang aggressive
- Health check endpoints untuk load balancer

## Testing Environment
- Use in-memory database untuk speed
- Mock all external services
- Enable test-only endpoints untuk data seeding
- Disable authentication untuk easier testing
```

#### 3. **Team Collaboration Rules**
```markdown
# .cursor/rules/collaboration.mdc

## Code Review Standards
- Maximum 400 lines per pull request
- Include screenshots untuk UI changes
- Add performance benchmarks untuk optimization PRs
- Link related issues dalam PR description

## Documentation Requirements
- README.md untuk setiap major feature
- API documentation dengan examples
- Architecture decision records (ADR) untuk major changes
- Inline comments untuk complex business logic

## Git Workflow
- Feature branches dari `develop`
- Squash commits sebelum merge
- Conventional commit messages
- Protected main branch dengan required reviews
```

### 📊 Measuring Rules Effectiveness

#### Key Metrics:
```
- Code Review Time: Target <2 hours per PR
- Bug Rate: Target <5 bugs per 100 features
- Test Coverage: Target >80% untuk business logic
- Development Velocity: Track story points per sprint
- Code Quality Score: SonarQube analysis
```

#### Success Indicators:
```
✅ AI generates code yang langsung pass CI/CD pipeline
✅ Fewer questions dalam code reviews
✅ Consistent architecture decisions across team
✅ New team members productive faster
✅ Less time spent pada style guide discussions
```

### 🚀 Implementing Rules Gradually

#### Week 1: Basic Setup
```
1. Create basic technical-standards.mdc
2. Add project-specific context rules
3. Define coding style preferences
4. Test dengan simple feature development
```

#### Week 2: Domain Knowledge
```
1. Add business domain rules
2. Define user personas dan use cases
3. Include architecture decisions
4. Create testing guidelines
```

#### Week 3: Advanced Features
```
1. Add security dan compliance rules
2. Create file-specific guidelines
3. Define team collaboration standards
4. Implement metrics tracking
```

#### Week 4: Optimization
```
1. Review dan refine existing rules
2. Add environment-specific configurations
3. Create team-specific templates
4. Document lessons learned
```

> 📚 **Panduan Lengkap**: Untuk pembahasan mendalam tentang Cursor Rules, implementasi level-by-level, dan teknik advanced, lihat [Panduan Lengkap Cursor Rules](guides/cursor-rules-comprehensive.md)

## 🎯 Context Management

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

## 💬 Prompt Engineering

### 1. Structure Prompts dengan Template

**Template untuk Feature Development:**
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

**Template untuk Bug Fixing:**
```