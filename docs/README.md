# Documentation Directory

This directory contains all project documentation organized by type.

## Directory Structure

```
docs/
├── README.md              # This file
├── decisions/            # Architecture Decision Records (ADRs)
│   └── ADR-001-mcp-integration.md
├── specs/               # Feature specifications
│   └── README.md
├── api/                # API documentation
│   └── README.md
└── capability-matrix.md # Feature inventory
```

## Documentation Types

### Architecture Decision Records (ADRs)
Location: `decisions/`

ADRs document important architectural decisions with their context and consequences.

Format: `ADR-XXX-[title].md`

### Feature Specifications
Location: `specs/`

Detailed specifications for features, including:
- Requirements
- Design decisions
- Implementation notes
- Testing criteria

### API Documentation
Location: `api/`

- Endpoint documentation
- Request/response schemas
- Authentication details
- Rate limits

### Capability Matrix
Location: `capability-matrix.md`

Living document tracking:
- What the project can do
- What it cannot do yet
- Partial/in-progress features
- Future roadmap

## Best Practices

1. **Keep Updated**: Update docs as code changes
2. **Be Concise**: Focus on essential information
3. **Use Examples**: Include code snippets
4. **Cross-Reference**: Link between related docs
5. **Version**: Include dates and versions

## Templates

See each subdirectory for specific templates and examples.