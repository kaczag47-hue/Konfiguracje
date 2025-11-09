# General concept

## Structure

```bash
/docs
  /<domain>
    README.md -> Domain overview and purpose
    architecture.md -> High-level domain architecture
    changelog.md -> Changelog for the domain
    data-model.md -> Core data model for the domain
    /<subdomain>
      README.md -> Subdomain overview
      architecture.md -> General architecture that communicate within the subdomain
      api/ 
        openapi.yaml -> REST API spec
        event-schema.yaml -> Event schema (publish/subscribe)
        graphql-schema.graphql -> GraphQL schema (if applicable)
      data-model.md -> Detailed subdomain data model
      policies.md -> Business rules and policies
      integration.md -> Integration guidelines with other domains
      workflows.md -> Workflows and process flows within the subdomain
      message-templates.md -> Templates for notifications/messages (if applicable)
      security.md -> Security considerations and requirements
      testing.md -> Testing strategy and examples
  /platform
    README.md -> Platform documentation overview
    shared-schemas/
      user-common.yaml -> Common user schemas
      error-codes.yaml -> Standard error codes
      pagination.yaml -> Pagination schemas
      validation-rules.yaml -> Common validation rules
    architecture-overview.md -> Overall system architecture
    integration-guidelines.md -> Cross-domain integration patterns
    deployment.md -> Deployment strategies and infrastructure
    monitoring.md -> Monitoring and observability guidelines
    security-standards.md -> Platform-wide security standards
    api-standards.md -> API design standards and conventions
  /reference
    README.md -> Reference documentation index
    changelog.md -> Global changelog
    glossary.md -> Terms and definitions
    adr/ -> Architecture Decision Records
      001-example-decision.md
      template.md
    style-guide.md -> Documentation style guide
    contributing.md -> Contribution guidelines
```

## Running Documentation

### Quick Start

```bash
cd docs-site
PORT=3001 npm start
```

The documentation will be available at **http://localhost:3001**

### Build for Production

```bash
cd docs-site
npm run build
npm run serve
```

### Project Structure

```
/docs                        # Source documentation (domain-driven)
  /core                     # Core domain
    /users                  # Users subdomain
    /auth                   # Auth subdomain
  /platform                 # Platform-wide resources
    /shared-schemas         # Shared OpenAPI schemas
  /reference                # Reference materials
    /adr                    # Architecture Decision Records

/docs-site                  # Docusaurus site
  /docs                     # Generated from /docs
  /src                      # React components
  docusaurus.config.ts      # Configuration
  sidebars.ts              # Navigation structure
```

### Features

✅ **Domain-Driven Architecture** - Documentation organized by domains and subdomains
✅ **OpenAPI Integration** - Native support for API documentation
✅ **Multi-sidebar Navigation** - Separate navigation for Domains, Platform, and Reference
✅ **Shared Schemas** - Reusable OpenAPI schemas in `/platform/shared-schemas`
✅ **ADRs** - Architecture Decision Records tracking
✅ **Modern UI** - Beautiful, responsive design with dark mode

### Adding New Domain

1. Create domain folder: `mkdir -p docs/my-domain/my-subdomain/api`
2. Add documentation files (README.md, data-model.md, policies.md, etc.)
3. Add OpenAPI spec in `api/openapi.yaml`
4. Update `docs-site/sidebars.ts` to include new domain
5. Restart dev server

### Commands

```bash
npm start              # Start dev server
npm run build          # Build for production
npm run serve          # Serve production build
npm run clear          # Clear cache
```