# 📝 Prompt Templates untuk Cursor AI

Koleksi template prompt yang bisa langsung digunakan untuk berbagai skenario development.

## 🏗️ Feature Development

### Template Dasar
```
Context: Saya sedang membuat [deskripsi fitur] untuk [jenis aplikasi]

Requirements:
- [Requirement 1]
- [Requirement 2] 
- [Requirement 3]

Tech Stack: [JavaScript/TypeScript, React, Node.js, dll]

Please implement this feature following best practices dan include:
1. Type definitions (jika menggunakan TypeScript)
2. Error handling
3. Unit tests
4. Documentation
```

### Template untuk API Development
```
Saya perlu membuat API endpoint untuk [fungsi spesifik].

Endpoint Details:
- Method: [GET/POST/PUT/DELETE]
- Path: [/api/path]
- Purpose: [Jelaskan tujuan endpoint]

Request Format:
```json
{
  "field1": "value1",
  "field2": "value2"
}
```

Expected Response:
```json
{
  "status": "success",
  "data": { ... }
}
```

Tech Stack: [Express.js, Fastify, dll]
Database: [MongoDB, PostgreSQL, dll]

Please include validation, error handling, dan proper HTTP status codes.
```

## 🐛 Bug Fixing & Debugging

### Template Debug
```
🚨 Bug Report

Problem: [Deskripsi singkat masalah]

Current Behavior:
[Apa yang terjadi sekarang]

Expected Behavior:
[Apa yang seharusnya terjadi]

Steps to Reproduce:
1. [Step 1]
2. [Step 2]
3. [Step 3]

Error Message:
```
[Copy paste error lengkap dengan stack trace]
```

Environment:
- OS: [macOS/Windows/Linux]
- Node Version: [v18.x.x]
- Browser: [Chrome/Firefox/Safari]

Relevant Code:
[Paste kode yang bermasalah atau mention file dengan @filename]

Please help me identify dan fix this issue.
```

### Template Performance Issue
```
🐌 Performance Issue

Page/Feature: [Nama halaman atau fitur]
Performance Problem: [Loading lambat, memory leak, dll]

Current Metrics:
- Load Time: [X seconds]
- Bundle Size: [X MB]
- Memory Usage: [X MB]

Expected Performance:
- Load Time: [< X seconds]
- Bundle Size: [< X MB]

Tech Stack: [React, Vue, Angular, dll]

Please analyze dan suggest optimizations for:
1. Code splitting opportunities
2. Lazy loading implementation
3. Bundle size reduction
4. Runtime performance improvements
```

## 🧪 Testing

### Template Test Generation
```
Generate comprehensive tests untuk [component/function/API endpoint].

Target Code:
[Paste kode atau mention dengan @filename]

Test Requirements:
- Unit tests untuk all functions
- Integration tests untuk API endpoints
- Component tests untuk React components
- Edge cases dan error scenarios

Testing Framework: [Jest, Vitest, Cypress, dll]

Please include:
1. Happy path tests
2. Error handling tests
3. Edge cases
4. Mocking external dependencies
5. Test setup dan teardown
```

## 🔄 Refactoring

### Template Code Review
```
🔍 Code Review Request

Please review this code untuk:
1. **Code Quality**: Clean code principles, readability
2. **Performance**: Potential optimizations
3. **Security**: Vulnerabilities atau best practices
4. **Maintainability**: Structure dan organization
5. **Testing**: Test coverage dan quality

Code Location: [Mention files dengan @filename atau paste code]

Specific Concerns:
- [Concern 1]
- [Concern 2]

Please provide:
- ✅ What's good
- ⚠️ Areas for improvement
- 🔧 Specific suggestions
- 📚 Best practices recommendations
```

### Template Refactoring
```
🛠️ Refactoring Request

Current Code: [Location atau paste code]

Refactoring Goals:
- [Goal 1: e.g., improve readability]
- [Goal 2: e.g., reduce duplication]
- [Goal 3: e.g., better error handling]

Constraints:
- [Constraint 1: e.g., maintain backward compatibility]
- [Constraint 2: e.g., don't change public API]

Please refactor this code while:
1. Maintaining current functionality
2. Improving code quality
3. Adding proper TypeScript types (if applicable)
4. Including updated tests
5. Adding documentation
```

## 📖 Documentation

### Template Documentation Generation
```
📚 Generate Documentation

For: [Component/Function/API/Module]
Code Location: [Use @filename atau paste code]

Please create comprehensive documentation including:

1. **Overview**: What it does dan why it exists
2. **Usage Examples**: Practical code examples
3. **API Reference**: Parameters, return values, types
4. **Error Handling**: Possible errors dan how to handle
5. **Best Practices**: Recommended usage patterns

Format: [JSDoc, Markdown, TypeDoc, dll]
Audience: [Developers, end users, API consumers]

Include real-world examples dan common use cases.
```

## 🎨 UI/UX Development

### Template Component Creation
```
🎨 Create React Component

Component Name: [ComponentName]
Purpose: [What this component does]

Design Requirements:
- [Visual requirement 1]
- [Interaction requirement 2]
- [Responsive behavior]

Props Interface:
```typescript
interface Props {
  prop1: string;
  prop2?: boolean;
  onAction: (data: any) => void;
}
```

Styling: [CSS Modules, Styled Components, Tailwind, dll]

Please include:
1. TypeScript interface
2. Responsive design
3. Accessibility features
4. Loading states
5. Error states
6. Storybook story (if applicable)
```

## 🗃️ Database Operations

### Template Database Schema
```
🗄️ Database Schema Design

Entity: [EntityName]
Purpose: [What this entity represents]

Fields:
- [field1]: [type] - [description]
- [field2]: [type] - [description]
- [field3]: [type] - [description]

Relationships:
- [belongs to / has many / many to many]: [RelatedEntity]

Business Rules:
- [Rule 1]
- [Rule 2]

Database: [PostgreSQL, MongoDB, MySQL, dll]
ORM: [Prisma, TypeORM, Mongoose, dll]

Please create:
1. Schema definition
2. Migration files
3. Model/Entity classes
4. Basic CRUD operations
5. Validation rules
```

## 🚀 Deployment & DevOps

### Template CI/CD Setup
```
🚀 CI/CD Pipeline Setup

Project Type: [React SPA, Node.js API, Full-stack, dll]
Target Platform: [Vercel, Netlify, AWS, Docker, dll]

Pipeline Requirements:
- [Requirement 1: e.g., run tests]
- [Requirement 2: e.g., lint code]
- [Requirement 3: e.g., build production bundle]

Environment Variables needed:
- [ENV_VAR_1]: [description]
- [ENV_VAR_2]: [description]

Please create:
1. GitHub Actions workflow / deployment config
2. Environment setup instructions
3. Build dan deployment scripts
4. Error monitoring setup
5. Performance monitoring
```

## 💡 Tips Penggunaan Template

### 1. Customization
- Replace placeholder `[...]` dengan informasi spesifik Anda
- Adjust template sesuai tech stack proyek
- Add atau remove sections sesuai kebutuhan

### 2. Context Sharing
- Always open relevant files sebelum menggunakan template
- Use `@filename` untuk reference specific files
- Include error messages atau logs jika ada

### 3. Iterative Approach
- Start dengan basic template
- Refine berdasarkan AI response
- Build on previous conversations

### 4. Save Successful Prompts
- Keep track dari prompts yang bekerja dengan baik
- Create project-specific variations
- Share dengan team members

---

**Pro Tip**: Copy template ke clipboard, lalu customize sesuai kebutuhan sebelum send ke Cursor AI. Ini akan menghemat waktu dan meningkatkan consistency! 🎯 