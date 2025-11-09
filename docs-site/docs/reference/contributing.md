# Contributing to Documentation

## Documentation Standards

### File Naming

- Use lowercase with hyphens: `user-authentication.md`
- Use descriptive names: `api-integration-guide.md`
- READMEs for directory overviews: `README.md`

### Markdown Style

- Use ATX-style headers: `# Header 1`, `## Header 2`
- Use fenced code blocks with language: ` ```yaml `
- Keep line length reasonable (80-120 chars)
- Use relative links for internal docs: `[Link](./other-doc.md)`

### OpenAPI Specs

- Follow OpenAPI 3.0+ specification
- Include examples for all schemas
- Document all endpoints
- Use `$ref` for shared schemas

### Structure

Follow the domain-driven structure:
```
/docs
  /<domain>
    /<subdomain>
      api/
        openapi.yaml
        event-schema.yaml
```

## Review Process

1. Create documentation in appropriate domain/subdomain
2. Ensure all links work
3. Validate OpenAPI specs
4. Submit for review
5. Address feedback
6. Publish

## Best Practices

✅ **DO:**
- Write clear, concise documentation
- Include examples
- Keep docs up to date with code
- Use diagrams when helpful
- Reference ADRs for architectural decisions

❌ **DON'T:**
- Copy-paste without context
- Leave broken links
- Use jargon without explanation
- Skip examples
- Document implementation details that change frequently

