# Model Selection

Choose the right Gemini model for your task.

## Available Models

### Gemini 1.5 Pro
- **Best for**: Complex analysis, large codebases
- **Context**: 2M tokens
- **Use when**: Analyzing entire projects, architectural reviews

### Gemini 1.5 Flash
- **Best for**: Quick responses, routine tasks
- **Context**: 1M tokens  
- **Use when**: Fast code reviews, simple explanations

### Gemini 1.5 Flash-8B
- **Best for**: Ultra-fast responses
- **Context**: 1M tokens
- **Use when**: Quick checks, simple queries

## Setting Models

### Via Environment Variable
```bash
export GEMINI_MODEL="gemini-1.5-pro-002"
```

### In Configuration
```json
{
  "mcpServers": {
    "gemini-cli": {
      "command": "gemini-mcp",
      "env": {
        "GEMINI_MODEL": "gemini-1.5-flash"
      }
    }
  }
}
```

### Per Request (Coming Soon)
```
/gemini-cli:analyze --model=flash @file.js quick review
```

## Model Comparison

| Model | Speed | Context | Best Use Case |
|-------|-------|---------|---------------|
| Pro | Slower | 2M tokens | Full codebase analysis |
| Flash | Fast | 1M tokens | Daily development |
| Flash-8B | Fastest | 1M tokens | Quick queries |

## Cost Optimization

1. **Start with Flash** for most tasks
2. **Use Pro** only when you need the full context
3. **Flash-8B** for simple, repetitive tasks

## Token Limits

- **Pro**: ~2 million tokens (~500k lines of code)
- **Flash**: ~1 million tokens (~250k lines of code)
- **Flash-8B**: ~1 million tokens (~250k lines of code)

## Recommendations

- **Code Review**: Flash
- **Architecture Analysis**: Pro
- **Quick Fixes**: Flash-8B
- **Documentation**: Flash
- **Security Audit**: Pro