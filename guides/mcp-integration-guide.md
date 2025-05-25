# 🔌 MCP Integration Guide untuk Cursor AI

Panduan lengkap untuk mengintegrasikan Model Context Protocol (MCP) servers dengan Cursor AI untuk memaksimalkan kemampuan development.

## 🎯 Apa itu MCP (Model Context Protocol)?

Model Context Protocol adalah standard yang memungkinkan AI assistants seperti Cursor untuk mengakses external tools, databases, dan services secara real-time. Dengan MCP, Anda bisa:

- 📚 **Akses dokumentasi terbaru** dari library/framework apapun
- 🧠 **Enhanced reasoning capabilities** dengan sequential thinking
- 🔧 **Integration dengan tools** seperti databases, APIs, file systems
- 🎯 **Context-aware responses** berdasarkan data real-time

## 🚀 Setup MCP di Cursor

### 1. Konfigurasi Global MCP
Buat atau edit file `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "sequentialthinking": {
      "command": "npx", 
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    }
  }
}
```

### 2. Konfigurasi Project-Specific
Buat `.cursor/mcp.json` di root project untuk project-specific MCP:

```json
{
  "mcpServers": {
    "project-context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "15000"
      }
    }
  }
}
```

### 3. Restart Cursor
Setelah konfigurasi, restart Cursor untuk load MCP servers.

## 📚 Context7 MCP - Up-to-Date Documentation

Context7 adalah game-changer untuk mendapatkan dokumentasi terbaru dari library/framework apapun.

### Keunggulan Context7
- ✅ **Up-to-date docs** langsung dari source
- ✅ **Version-specific** documentation 
- ✅ **No hallucinated APIs** - semua real dan current
- ✅ **No outdated examples** - selalu fresh content

### Cara Penggunaan

#### Basic Usage
```
Create a basic Next.js project with app router. use context7
```

#### Database Operations
```
Create a script to delete rows where city is "" given PostgreSQL credentials. use context7
```

#### Framework-Specific
```
Build a React component with Material-UI v5 latest features. use context7
```

#### API Integration
```
Implement authentication dengan Supabase latest SDK. use context7
```

### Advanced Context7 Patterns

#### Multi-Library Context
```
Create a full-stack app dengan:
- Next.js 14 (app router)
- Prisma ORM latest
- TailwindCSS v4
- TypeScript strict mode

use context7 untuk semua dependencies
```

#### Version-Specific Requests
```
Show me how to implement server actions di Next.js 14.3+ 
dengan latest best practices. use context7
```

### Context7 Pro Tips
- Selalu mention "use context7" di akhir prompt
- Specific tentang version jika ada requirement khusus
- Combine dengan project context untuk hasil optimal

## 🧠 Sequential Thinking MCP - Advanced Problem Solving

Sequential Thinking MCP memberikan AI kemampuan untuk berpikir secara systematic dan reflective.

### Kapan Menggunakan Sequential Thinking?

#### Complex Problem Solving
```
I need to architect a microservices system untuk e-commerce platform
dengan high availability dan scalability requirements.

Please use sequential thinking untuk analyze:
1. Service boundaries
2. Data consistency strategies  
3. Communication patterns
4. Deployment considerations
```

#### Multi-Step Analysis
```
Analyze performance bottleneck di aplikasi React kita.
Current symptoms: slow initial load, laggy interactions.

Use sequential thinking untuk systematic debugging:
- Bundle analysis
- Runtime performance profiling
- Network optimization opportunities
- Rendering optimization strategies
```

#### Architecture Decisions
```
We need to choose state management solution untuk large React app.
Options: Redux Toolkit, Zustand, React Query + Context.

Use sequential thinking untuk evaluate:
- Learning curve untuk team
- Performance implications
- Maintenance overhead
- Future scalability
```

### Sequential Thinking Patterns

#### The Progressive Analysis Pattern
```
Use sequential thinking untuk analyze this codebase issue:

Starting point: User reports slow checkout process
Goal: Identify dan fix performance bottlenecks
Constraints: No breaking changes, maintain compatibility

Work through this systematically dengan multiple iterations.
```

#### The Decision Framework Pattern
```
Help me decide antara architectural approaches:

Option A: Monolithic dengan modular structure
Option B: Microservices dengan API gateway
Option C: Micro-frontends dengan shared backend

Use sequential thinking untuk structured comparison
considering our team size (5 devs) dan timeline (3 months).
```

## 🛠️ Essential MCP Servers - Recommendations

### 1. **Context7** (WAJIB)
**Use Case:** Up-to-date documentation
```json
"context7": {
  "command": "npx",
  "args": ["-y", "@upstash/context7-mcp"]
}
```

### 2. **Sequential Thinking** (WAJIB)
**Use Case:** Complex problem solving
```json
"sequentialthinking": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
}
```

### 3. **Memory MCP** (SANGAT DIREKOMENDASIKAN)
**Use Case:** Persistent memory across conversations
```json
"memory": {
  "command": "npx", 
  "args": ["-y", "@modelcontextprotocol/server-memory"]
}
```

### 4. **File System MCP** (BERGUNA)
**Use Case:** File operations dan code analysis
```json
"filesystem": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-filesystem"],
  "env": {
    "ROOT_PATH": "/path/to/your/projects"
  }
}
```

### 5. **GitHub MCP** (TEAM DEVELOPMENT)
**Use Case:** GitHub integration untuk PRs, issues, code reviews
```json
"github": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-github"],
  "env": {
    "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token"
  }
}
```

### 6. **Database MCP** (DATA-DRIVEN APPS)
**Use Case:** Database operations dan schema management
```json
"sqlite": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-sqlite"],
  "env": {
    "SQLITE_DB_PATH": "./data/app.db"
  }
}
```

### 7. **Web Search MCP** (RESEARCH)
**Use Case:** Real-time web search untuk current information
```json
"brave-search": {
  "command": "npx",
  "args": ["-y", "@modelcontextprotocol/server-brave-search"],
  "env": {
    "BRAVE_API_KEY": "your-brave-api-key"
  }
}
```

## 📋 MCP Setup Checklist

### Basic Setup (Week 1)
- [ ] Install Context7 MCP
- [ ] Install Sequential Thinking MCP
- [ ] Test basic functionality
- [ ] Practice "use context7" pattern

### Intermediate Setup (Week 2-3)
- [ ] Add Memory MCP untuk persistence
- [ ] Setup File System MCP
- [ ] Configure environment variables
- [ ] Practice complex prompts

### Advanced Setup (Week 4+)
- [ ] Add domain-specific MCPs (GitHub, Database)
- [ ] Create project-specific configurations
- [ ] Setup team-shared MCP configs
- [ ] Optimize performance settings

## 🎯 MCP Best Practices

### 1. **Prompt Patterns dengan MCP**

#### Context7 Integration
```
// Specific library request
"Create authentication middleware dengan Express.js latest security practices. use context7"

// Multi-library integration  
"Build dashboard dengan React, Chart.js v4, dan TailwindCSS. use context7 untuk all libraries"

// Framework migration
"Convert this jQuery code to modern React hooks pattern. use context7 untuk latest React practices"
```

#### Sequential Thinking Integration
```
// Complex architecture
"Design microservices architecture untuk e-commerce platform. Use sequential thinking untuk systematic analysis of service boundaries, data flow, dan deployment strategy."

// Performance optimization
"Our React app has memory leaks. Use sequential thinking untuk methodical debugging: profiling, source identification, fix strategies, testing approach."

// Technology decision
"Choose between GraphQL vs REST untuk our API. Use sequential thinking untuk structured comparison considering team expertise, performance, tooling, dan maintenance."
```

### 2. **Combining Multiple MCPs**

#### Context7 + Sequential Thinking
```
"I need to refactor legacy codebase dari jQuery ke React.

First, use context7 untuk latest React patterns dan migration strategies.

Then, use sequential thinking untuk plan systematic migration:
1. Assessment current state
2. Migration strategy planning
3. Risk mitigation
4. Implementation phases
5. Testing approaches"
```

#### Memory + Context7
```
"Based on our previous discussion about authentication patterns (check memory),
implement OAuth integration dengan latest security practices. use context7 untuk 
up-to-date OAuth 2.1 dan PKCE implementation."
```

### 3. **Environment-Specific Configurations**

#### Development Environment
```json
{
  "mcpServers": {
    "context7-dev": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "20000"
      }
    },
    "filesystem-dev": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./src"
      }
    }
  }
}
```

#### Production Planning
```json
{
  "mcpServers": {
    "context7-prod": {
      "command": "npx", 
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "25000"
      }
    },
    "github-prod": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${PROD_GITHUB_TOKEN}"
      }
    }
  }
}
```

## 🚀 Advanced MCP Workflows

### 1. **Full-Stack Development Workflow**

#### Research Phase
```
"Research latest full-stack architecture trends untuk SaaS application. 
use context7 untuk current best practices dari:
- Next.js 14+ features
- Database ORMs (Prisma, Drizzle)
- Authentication solutions
- Deployment platforms"
```

#### Planning Phase
```
"Based on research, use sequential thinking untuk architect complete solution:
1. Technology stack selection
2. Database schema design
3. API structure planning
4. Authentication flow
5. Deployment strategy"
```

#### Implementation Phase
```
"Implement user authentication system dengan selected stack.
use context7 untuk implementation details dan current security practices."
```

### 2. **Bug Hunting Workflow**

#### Investigation
```
"We have performance issue di React app. Use sequential thinking untuk systematic debugging:
1. Performance profiling setup
2. Bottleneck identification
3. Root cause analysis
4. Fix strategy development
5. Testing plan"
```

#### Research Solutions
```
"For identified performance issues, use context7 untuk:
- Latest React performance optimization techniques
- Bundle analysis tools dan best practices  
- Memory leak detection methods
- Profiling tools comparison"
```

#### Implementation
```
"Implement performance fixes berdasarkan research.
use context7 untuk latest implementation patterns."
```

## 📊 MCP Success Metrics

### Performance Indicators
```
✅ 50%+ faster library integration dengan Context7
✅ More systematic problem-solving dengan Sequential Thinking  
✅ Reduced research time untuk new technologies
✅ Better architecture decisions dengan structured thinking
✅ Up-to-date code patterns consistently applied
```

### Quality Improvements
```
🎯 Fewer deprecated API usage
🎯 More robust error handling patterns
🎯 Better security practices implementation
🎯 Improved code documentation quality
🎯 Consistent dengan latest best practices
```

## 🔧 Troubleshooting MCP

### Common Issues

#### MCP Server Not Loading
```bash
# Check MCP configuration
cat ~/.cursor/mcp.json

# Test MCP server manually
npx -y @upstash/context7-mcp

# Check Cursor logs
tail -f ~/.cursor/logs/cursor.log | grep mcp
```

#### Context7 Not Responding
```json
// Try alternative configuration
{
  "mcpServers": {
    "context7": {
      "command": "bunx",
      "args": ["-y", "@upstash/context7-mcp"]
    }
  }
}
```

#### Performance Issues
```json
// Optimize token limits
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "8000"
      }
    }
  }
}
```

---

## 💡 Pro Tips

### Prompt Optimization
- **Always specify** "use context7" untuk documentation needs
- **Combine MCPs** untuk comprehensive solutions
- **Be specific** tentang library versions dan requirements
- **Use sequential thinking** untuk complex architectural decisions

### Workflow Integration
- Setup MCP configs dalam version control
- Share team MCP configurations untuk consistency
- Document MCP usage patterns dalam project README
- Regular MCP server updates untuk latest features

**🚀 With proper MCP integration, Cursor AI becomes exponentially more powerful untuk modern development workflows!** 