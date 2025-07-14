# Project-Specific Context Directory

This directory contains project-specific context files that augment the global CLAUDE.md rules.

## Directory Structure

```
.claude/project/
├── README.md           # This file
├── context.md         # Additional project context
├── mcp-config.md      # MCP tool configuration
└── examples/          # Project-specific examples
```

## Usage

Files in this directory are automatically loaded by Claude Code when working on this project. They provide:

1. **Project-specific rules** that override or extend global rules
2. **MCP tool configurations** specific to this project
3. **Context examples** that demonstrate patterns
4. **Architecture decisions** unique to this project

## Priority Order

1. `.claude/project/` files (highest priority)
2. Root `CLAUDE.md` file
3. Global `.claude/CLAUDE.md` file (lowest priority)

## Best Practices

- Keep files focused and under 500 lines
- Use clear headings and structure
- Include examples where possible
- Document MCP tool usage patterns
- Update as project evolves