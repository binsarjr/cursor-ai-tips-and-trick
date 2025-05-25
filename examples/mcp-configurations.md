# 🔌 MCP Configuration Examples

Koleksi konfigurasi MCP untuk berbagai skenario development dan team setup.

## 🚀 Basic Setup - Individual Developer

### Minimal Essential Configuration
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

### Enhanced Personal Setup
```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "15000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./src"
      }
    }
  }
}
```

## 👥 Team Development Setup

### Frontend Team Configuration
```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "20000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./src"
      }
    }
  }
}
```

### Full-Stack Team Configuration
```json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "25000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_TOKEN}"
      }
    },
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./"
      }
    },
    "sqlite": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sqlite"],
      "env": {
        "SQLITE_DB_PATH": "./data/development.db"
      }
    },
    "brave-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "${BRAVE_API_KEY}"
      }
    }
  }
}
```

## 🏗️ Project-Specific Configurations

### React/Next.js Project
```json
{
  "mcpServers": {
    "context7-react": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "18000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "filesystem-components": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./src/components"
      }
    }
  }
}
```

### Node.js/Express API Project
```json
{
  "mcpServers": {
    "context7-node": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "20000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "filesystem-api": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./src/routes"
      }
    },
    "sqlite-dev": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sqlite"],
      "env": {
        "SQLITE_DB_PATH": "./data/api.db"
      }
    }
  }
}
```

### DevOps/Infrastructure Project
```json
{
  "mcpServers": {
    "context7-devops": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "22000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    },
    "github-ci": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "${GITHUB_CI_TOKEN}"
      }
    },
    "filesystem-infra": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem"],
      "env": {
        "ROOT_PATH": "./infrastructure"
      }
    },
    "brave-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "${BRAVE_API_KEY}"
      }
    }
  }
}
```

## 🔧 Environment-Specific Configurations

### Development Environment
```json
{
  "mcpServers": {
    "context7-dev": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "15000"
      }
    },
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory-dev": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
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

### Production/Staging Environment
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
    "sequentialthinking": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory-prod": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
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

## 🚀 Platform-Specific Configurations

### Windows Configuration
```json
{
  "mcpServers": {
    "context7": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@upstash/context7-mcp"]
    },
    "sequentialthinking": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "cmd",
      "args": ["/c", "npx", "-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

### macOS/Linux with Bun
```json
{
  "mcpServers": {
    "context7": {
      "command": "bunx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "sequentialthinking": {
      "command": "bunx",
      "args": ["-y", "@modelcontextprotocol/server-sequential-thinking"]
    },
    "memory": {
      "command": "bunx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

### Docker Container Setup
```json
{
  "mcpServers": {
    "context7": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "context7-mcp"]
    },
    "sequentialthinking": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "sequential-thinking-mcp"]
    }
  }
}
```

## 🔍 Troubleshooting Configurations

### Alternative Package Managers
```json
{
  "mcpServers": {
    "context7-alt": {
      "command": "bunx",
      "args": ["-y", "@upstash/context7-mcp"]
    },
    "context7-deno": {
      "command": "deno",
      "args": ["run", "--allow-env", "--allow-net", "npm:@upstash/context7-mcp"]
    }
  }
}
```

### With Node Options
```json
{
  "mcpServers": {
    "context7-experimental": {
      "command": "npx",
      "args": [
        "-y",
        "--node-options=--experimental-vm-modules",
        "@upstash/context7-mcp"
      ]
    }
  }
}
```

### Performance Optimized
```json
{
  "mcpServers": {
    "context7-fast": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"],
      "env": {
        "DEFAULT_MINIMUM_TOKENS": "8000"
      }
    }
  }
}
```

## 📋 Configuration Checklist

### Basic Setup ✅
- [ ] Context7 MCP configured
- [ ] Sequential Thinking MCP configured
- [ ] Cursor restarted after configuration
- [ ] Test "use context7" dalam prompt

### Team Setup ✅
- [ ] Shared MCP configuration file
- [ ] Environment variables documented
- [ ] API keys properly secured
- [ ] Team training completed

### Advanced Setup ✅
- [ ] Project-specific configurations
- [ ] Environment-specific settings
- [ ] Performance optimization
- [ ] Monitoring dan logging setup

## 💡 Pro Tips untuk MCP Configuration

### 1. **Environment Variables Management**
```bash
# .env file
GITHUB_TOKEN=your_github_token
BRAVE_API_KEY=your_brave_api_key
DEFAULT_MINIMUM_TOKENS=15000
```

### 2. **Team Configuration Sharing**
```bash
# Share via git (without secrets)
git add .cursor/mcp.json
git commit -m "feat: add team MCP configuration"

# Document environment variables in README
echo "GITHUB_TOKEN=your_token_here" >> .env.example
```

### 3. **Performance Monitoring**
```bash
# Check MCP server status
ps aux | grep mcp

# Monitor token usage
tail -f ~/.cursor/logs/cursor.log | grep token
```

### 4. **Regular Updates**
```bash
# Update MCP servers
npx -y @upstash/context7-mcp@latest
npx -y @modelcontextprotocol/server-sequential-thinking@latest
```

---

## 🎯 Recommended Starting Point

**Untuk pemula**, start dengan **Basic Setup**:
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

**Setelah 1-2 minggu**, upgrade ke **Enhanced Personal Setup** dengan Memory dan File System.

**Untuk team development**, langsung gunakan **Team Development Setup** sesuai stack technology Anda.

**Happy coding dengan MCP! 🚀** 