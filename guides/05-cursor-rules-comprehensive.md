# 📜 Panduan Lengkap Cursor Rules

Panduan comprehensive untuk membuat, mengelola, dan memaksimalkan efektivitas Cursor Rules dalam proyek development.

## 🎯 Apa itu Cursor Rules?

Cursor Rules adalah file konfigurasi berformat Markdown (`.mdc`) yang memberikan context dan instruksi spesifik kepada AI tentang bagaimana bekerja dengan proyek Anda. Rules ini berfungsi sebagai "domain knowledge" yang membuat AI memahami preferensi, standards, dan constraints proyek Anda.

### Anatomi Rules File
```
.cursor/
├── rules/
│   ├── project-context.mdc     # Context umum proyek
│   ├── technical-standards.mdc # Standards coding
│   ├── business-domain.mdc     # Domain knowledge
│   ├── testing-strategy.mdc    # Guidelines testing
│   └── security.mdc            # Security requirements
```

## 🏗️ Level-Level Rules Implementation

### Level 1: Basic Project Rules
**Target**: Consistency dalam coding style dan basic practices

```markdown
# .cursor/rules/basic-standards.mdc

## Project Overview
- **Type**: [Web app / Mobile app / API / Library]
- **Tech Stack**: [React, TypeScript, Node.js, PostgreSQL]
- **Target Users**: [Description of users]
- **Business Domain**: [E-commerce / SaaS / Fintech / etc]

## Code Style
- **Language**: TypeScript dengan strict mode enabled
- **Formatting**: Prettier dengan 2-space indentation
- **Linting**: ESLint dengan recommended rules
- **Naming**: camelCase untuk variables/functions, PascalCase untuk components

## File Organization
- Components dalam `/components` dengan co-located styles dan tests
- Business logic dalam `/hooks` atau `/services`
- Types dalam `/types` dengan meaningful names
- Constants dalam `/constants` digroup by feature

## Git Practices
- Conventional commits: feat, fix, docs, style, refactor, test, chore
- Branch naming: feature/task-description, bugfix/issue-description
- PR size: maksimal 400 lines untuk maintainability
```

**Manfaat Level 1:**
- ✅ Consistent code style across team
- ✅ Predictable file organization
- ✅ Better code reviews
- ✅ Easier onboarding

### Level 2: Domain-Specific Rules
**Target**: AI memahami business context dan domain knowledge

```markdown
# .cursor/rules/ecommerce-domain.mdc

## Business Context
Platform e-commerce untuk UMKM Indonesia dengan karakteristik:
- **Target Market**: Pemilik usaha kecil, usia 25-50 tahun
- **Tech Literacy**: Basic to intermediate
- **Primary Device**: Mobile (75% traffic)
- **Key Features**: Product catalog, order management, payment processing

## Business Rules
### Inventory Management
- Real-time stock tracking dengan automatic low-stock alerts
- Batch operations untuk bulk product updates
- SKU format: [CATEGORY]-[SUBCATEGORY]-[ID] (e.g., FASHION-SHIRT-001)

### Pricing Strategy
- Support multiple currency (IDR primary)
- Tax calculation: PPN 11% included in display price
- Discount types: percentage, fixed amount, buy-X-get-Y
- Price history tracking untuk analytics

### Order Processing
- Order status flow: pending → confirmed → processing → shipped → delivered
- Payment methods: bank transfer, e-wallet, COD, credit card
- Shipping integration: JNE, TIKI, SiCepat, Grab
- Auto-cancel orders after 24 hours if unpaid

## User Experience Guidelines
- **Mobile-first**: Design untuk screen 360px minimum width
- **Language**: Bahasa Indonesia primary, English secondary
- **Loading states**: Skeleton screens untuk better perceived performance
- **Error messages**: User-friendly dalam Bahasa Indonesia
- **Accessibility**: WCAG 2.1 AA compliance

## Integration Requirements
- **Payment Gateway**: Midtrans untuk all payment methods
- **WhatsApp Business**: Order notifications dan customer service
- **Google Analytics**: E-commerce tracking dengan custom events
- **Social Media**: Instagram shop integration
```

**Manfaat Level 2:**
- ✅ Business-relevant feature suggestions
- ✅ Domain-appropriate error handling
- ✅ User experience aligned dengan target market
- ✅ Realistic business logic implementation

### Level 3: Advanced Architecture Rules
**Target**: Scalable, maintainable, dan secure codebase

```markdown
# .cursor/rules/architecture-advanced.mdc

## System Architecture
### Layered Architecture
```
/src
├── presentation/     # UI components, pages, forms
├── application/      # Use cases, application services
├── domain/          # Business entities, domain services
├── infrastructure/  # External APIs, database, third-party
└── shared/          # Common utilities, types, constants
```

### Dependency Management
- **Dependency Injection**: Use inversify container
- **Interface Segregation**: Small, focused interfaces
- **Dependency Inversion**: Depend on abstractions, not concretions
- **Cross-cutting Concerns**: Logging, caching, validation as decorators

## State Management Strategy
### Client State (UI State)
- **Zustand** untuk simple state management
- Store structure: flat, normalized data
- Actions co-located dengan stores
- TypeScript interfaces untuk all state shapes

### Server State (API Data)
- **React Query (TanStack Query)** untuk server state
- Cache invalidation strategy berdasarkan data dependencies
- Optimistic updates untuk better UX
- Background refetch untuk fresh data

### Forms State
- **React Hook Form** dengan Zod validation
- Schema-driven validation dengan custom error messages
- Debounced validation untuk better UX
- Form persistence untuk draft data

## Performance Architecture
### Code Splitting Strategy
- Route-based splitting dengan React.lazy
- Component-based splitting untuk heavy components
- Dynamic imports untuk conditional features
- Webpack bundle analysis untuk optimization

### Caching Strategy
- **Browser Cache**: Static assets dengan long TTL
- **Memory Cache**: Frequently accessed data dengan TTL
- **Service Worker**: Offline-first untuk critical features
- **CDN Cache**: Images dan static content

### Database Design
- **Normalization**: 3NF untuk transactional data
- **Denormalization**: Read-optimized views untuk reporting
- **Indexing Strategy**: Compound indexes untuk common queries
- **Partitioning**: Time-based partitioning untuk large tables

## Error Handling Architecture
### Error Types
```typescript
interface AppError {
  type: 'ValidationError' | 'BusinessError' | 'SystemError' | 'ExternalError';
  code: string;
  message: string;
  details?: Record<string, any>;
  correlationId: string;
}
```

### Error Boundaries
- **Component Level**: Granular error boundaries untuk features
- **Route Level**: Page-level error boundaries dengan retry
- **Global Level**: Application-level error boundary dengan reporting
- **Async Boundaries**: Error boundaries untuk async operations

### Logging Strategy
- **Structured Logging**: JSON format dengan consistent fields
- **Log Levels**: DEBUG, INFO, WARN, ERROR dengan appropriate usage
- **Correlation IDs**: Request tracing across services
- **Sensitive Data**: Automatic PII redaction dalam logs

## Security Architecture
### Authentication Flow
- **JWT Tokens**: Short-lived access (15 min) + long-lived refresh (7 days)
- **Token Storage**: httpOnly cookies untuk refresh, memory untuk access
- **Session Management**: Concurrent session limits dengan device tracking
- **Logout Strategy**: Token blacklisting dengan Redis

### Authorization Patterns
- **RBAC (Role-Based)**: User → Roles → Permissions mapping
- **ABAC (Attribute-Based)**: Context-aware permissions
- **Resource-Based**: Owner, collaborator, viewer permissions
- **Time-Based**: Temporary access dengan expiration

### Input Validation
- **Schema Validation**: Zod schemas untuk all inputs
- **Sanitization**: HTML/SQL injection prevention
- **Rate Limiting**: Request throttling per user/IP
- **File Upload**: Type validation, size limits, virus scanning
```

**Manfaat Level 3:**
- ✅ Scalable architecture dari awal
- ✅ Security best practices terintegrasi
- ✅ Performance optimization yang systematic
- ✅ Maintainable codebase untuk long-term

### Level 4: Team Collaboration Rules
**Target**: Efficient teamwork dan knowledge sharing

```markdown
# .cursor/rules/team-collaboration.mdc

## Development Workflow
### Sprint Planning
- **Story Estimation**: Fibonacci sequence (1, 2, 3, 5, 8, 13)
- **Definition of Done**: Code review, tests pass, documentation updated
- **Sprint Goals**: Clear, measurable objectives
- **Capacity Planning**: 70% development, 20% bugs, 10% tech debt

### Code Review Process
#### Review Checklist
- [ ] **Functionality**: Does it solve the stated problem?
- [ ] **Performance**: Any obvious performance issues?
- [ ] **Security**: Potential security vulnerabilities?
- [ ] **Testing**: Adequate test coverage?
- [ ] **Documentation**: Is code self-documenting or properly commented?
- [ ] **Architecture**: Follows established patterns?

#### Review Guidelines
- **Size Limit**: Maximum 400 lines per PR
- **Response Time**: Review within 24 hours
- **Feedback Style**: Constructive, specific, actionable
- **Approval Criteria**: At least 2 approvals untuk major changes

### Knowledge Sharing
#### Documentation Standards
- **ADRs (Architecture Decision Records)**: Document major technical decisions
- **API Documentation**: OpenAPI specs dengan examples
- **Runbooks**: Step-by-step operational procedures
- **Troubleshooting Guides**: Common issues dan solutions

#### Learning & Development
- **Tech Talks**: Weekly 30-min sessions on relevant topics
- **Code Katas**: Monthly coding practice sessions
- **Pair Programming**: Regular pairing untuk knowledge transfer
- **External Learning**: Conference talks, online courses, books

## Quality Assurance
### Testing Strategy
#### Test Types Distribution
- **Unit Tests**: 70% - Fast, isolated, deterministic
- **Integration Tests**: 20% - API endpoints, database interactions
- **E2E Tests**: 10% - Critical user journeys

#### Test Standards
- **Naming Convention**: describe('when X', () => { it('should Y', () => {})})
- **AAA Pattern**: Arrange, Act, Assert dengan clear separation
- **Test Data**: Factories untuk consistent test data generation
- **Mocking Strategy**: Mock external dependencies, stub internal

### Monitoring & Observability
#### Application Monitoring
- **Error Tracking**: Sentry untuk error aggregation dan alerting
- **Performance Monitoring**: Application performance metrics
- **User Analytics**: User behavior tracking dengan privacy compliance
- **Business Metrics**: KPI tracking dan dashboards

#### Infrastructure Monitoring
- **Health Checks**: Endpoint untuk load balancer monitoring
- **Resource Usage**: CPU, memory, disk usage alerting
- **Database Performance**: Query performance dan connection pooling
- **Third-party Dependencies**: External service availability monitoring

## Communication Standards
### Meeting Guidelines
- **Daily Standups**: Max 15 minutes, focus on blockers
- **Sprint Review**: Demo working software, gather feedback
- **Retrospectives**: Action items untuk continuous improvement
- **Technical Discussions**: Dedicated time untuk architecture decisions

### Documentation Culture
- **Living Documentation**: Keep docs updated dengan code changes
- **Decision Rationale**: Document why, not just what
- **Examples**: Always include code examples dalam documentation
- **Accessibility**: Documentation accessible to all team members

### Conflict Resolution
- **Technical Disagreements**: Data-driven decisions, POCs when needed
- **Code Style Disputes**: Refer to established standards, tools enforcement
- **Architecture Decisions**: Collaborative decision-making dengan pros/cons analysis
- **Priority Conflicts**: Product owner final decision dengan team input
```

**Manfaat Level 4:**
- ✅ Streamlined development workflow
- ✅ Consistent quality standards
- ✅ Effective knowledge sharing
- ✅ Reduced team conflicts

## 🔧 Rules Implementation Strategies

### 1. Progressive Implementation
```
Week 1: Basic project rules (Level 1)
Week 2: Domain-specific rules (Level 2)
Week 3: Architecture rules (Level 3)
Week 4: Team collaboration rules (Level 4)
```

### 2. File Organization Strategy
```
.cursor/rules/
├── 01-project-basics.mdc      # Level 1: Basic standards
├── 02-domain-knowledge.mdc    # Level 2: Business context
├── 03-architecture.mdc        # Level 3: Technical architecture
├── 04-team-process.mdc        # Level 4: Collaboration
├── 05-security.mdc            # Cross-cutting: Security
└── 06-performance.mdc         # Cross-cutting: Performance
```

### 3. Rules Maintenance
```markdown
# Monthly Rules Review Checklist
- [ ] Update based on team feedback
- [ ] Remove outdated practices
- [ ] Add new patterns discovered
- [ ] Validate against current project needs
- [ ] Check consistency across files
```

## 📊 Measuring Rules Effectiveness

### Quantitative Metrics
```
• Code Review Time: Before vs After rules implementation
• Bug Rate: Defects per feature before vs after
• Development Velocity: Story points per sprint
• Test Coverage: Percentage coverage maintained
• Documentation Quality: Percentage of features documented
```

### Qualitative Indicators
```
• Team Satisfaction: Regular surveys
• Onboarding Time: Time for new developers to contribute
• Code Consistency: Subjective assessment during reviews
• Decision Speed: Time to make technical decisions
• Knowledge Sharing: Frequency of questions/discussions
```

### Success Stories Template
```markdown
## Success Story: [Feature Name]

**Before Rules:**
- AI generated code that required 3 rounds of review
- Missing error handling dan validation
- Inconsistent with existing patterns
- Required additional testing

**After Rules:**
- AI generated production-ready code
- Proper error handling included
- Followed established patterns
- Tests included automatically

**Impact:**
- 60% reduction in review time
- Zero production bugs in first month
- Pattern reused by team members
```

## 🚀 Advanced Rules Techniques

### 1. Conditional Rules
```markdown
## File-Specific Guidelines

### React Components (*.tsx)
When working dengan React components:
- Always use TypeScript interfaces untuk props
- Include error boundaries untuk error handling
- Implement loading dan error states
- Use React.memo untuk performance optimization

### API Routes (/api/*)
When creating API endpoints:
- Validate request body dengan Zod schemas
- Implement proper HTTP status codes (200, 201, 400, 404, 500)
- Add request/response logging
- Include OpenAPI documentation comments

### Database Models (/models/*)
When defining database models:
- Use Prisma schema dengan proper relations
- Include timestamps (created_at, updated_at)
- Add soft delete capability
- Implement proper indexes
```

### 2. Environment-Aware Rules
```markdown
## Environment-Specific Behavior

### Development Environment
- Enable detailed error messages dengan stack traces
- Use development-only debugging tools
- Allow CORS from localhost
- Mock external services

### Production Environment
- Minimal error messages (no stack traces)
- Enable comprehensive monitoring
- Strict CORS policy
- Real external service connections
```

### 3. Role-Based Rules
```markdown
## Team Role Considerations

### Frontend Developer Focus
- Emphasize responsive design dan accessibility
- Include performance optimization suggestions
- Focus on user experience considerations
- Suggest component reusability patterns

### Backend Developer Focus
- Emphasize API design dan documentation
- Include database optimization suggestions
- Focus on security considerations
- Suggest scalability patterns

### DevOps Engineer Focus
- Include deployment considerations
- Suggest monitoring dan logging
- Focus on infrastructure patterns
- Include security scanning
```

---

## 🎓 Rules Mastery Checklist

### Basic Level (Week 1-2)
- [ ] Created basic project context rules
- [ ] Defined coding standards dan style guides
- [ ] Established file organization patterns
- [ ] Implemented git workflow standards

### Intermediate Level (Week 3-4)
- [ ] Added domain-specific business rules
- [ ] Defined architecture patterns
- [ ] Implemented testing strategies
- [ ] Created security guidelines

### Advanced Level (Week 5-6)
- [ ] Added performance optimization rules
- [ ] Implemented team collaboration standards
- [ ] Created environment-specific configurations
- [ ] Established monitoring dan observability

### Expert Level (Week 7-8)
- [ ] Implemented conditional rules
- [ ] Created role-based guidelines
- [ ] Established rules maintenance process
- [ ] Measured dan optimized rules effectiveness

---

**Remember**: Great rules are living documents yang evolve dengan project dan team needs. Start simple, iterate based on feedback, dan always measure impact! 🎯 