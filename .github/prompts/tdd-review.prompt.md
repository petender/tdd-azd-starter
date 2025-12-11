---
agent: 'agent'
description: 'Review Azure Developer CLI template for Trainer Demo Deploy best practices and suggest improvements.'
---
# Trainer Demo Deploy Template Review

Review the Azure Developer CLI (azd) template in ${selection} for compliance with Trainer Demo Deploy catalog best practices. Provide actionable recommendations without making code changes.

## Required Template Components

- **README.md**: Follow structure defined in .github/instructions/readme.instructions.md (includes What You'll Deploy with costs, Architecture, Prerequisites, Quick Start, Verification Steps, Troubleshooting, Cost Management)
- **azure.yaml**: Follow .github/instructions/azure-yaml.instructions.md (name with tdd- prefix, semantic versioning, bicep provider)
- **infra/main.bicep**: Follow .github/instructions/bicep.instructions.md (subscription targetScope, standard parameters, SecurityControl:Ignore tag, resources module)
- **infra/resources.bicep**: Follow .github/instructions/bicep.instructions.md (resourceGroup targetScope, abbreviations.json pattern, outputs in UPPER_SNAKE_CASE)
- **prereqs.md**: Follow .github/instructions/prereqs.instructions.md (scenario-specific tools only, proper naming conventions)
- **demoguide/demoguide.md**: Resource list with screenshots, step-by-step demo instructions, consistent formatting
- **CONTRIBUTING.md**: Customization workflow, testing checklist, quality standards, submission process

## Review Checklist

- **Documentation Quality**: README includes cost estimates ($X/day)? Deployment time specified? Architecture diagram present? Verification steps clear? Troubleshooting section helpful?
- **Infrastructure Standards**: main.bicep uses subscription scope? SecurityControl:Ignore tag present (required for MTT subscriptions)? Abbreviations.json pattern used? resourceToken follows uniqueString(subscription().id, environmentName, location) pattern?
- **Bicep Best Practices**: All parameters have @description decorators? Secrets use @secure()? Outputs avoid exposing connection strings? Latest stable API versions? Resource references use symbolic names not functions?
- **Naming Conventions**: Parameters use lowerCamelCase? Outputs use UPPER_SNAKE_CASE? Resource names follow abbrs + resourceToken pattern? azure.yaml name has tdd- prefix?
- **Security**: No hardcoded credentials? Managed identities used? RBAC implemented with least privilege? 
- **Trainer-Friendliness**: Cost estimates realistic for training scenarios? Optional expensive resources use bool flags? Demo steps clear and actionable? Verification straightforward?
- **azd Compatibility**: Uses 3-step deployment (init/up/down)? Tags include azd-env-name? Outputs saved to .env file? Hooks properly configured if present?
- **Prerequisites**: Only scenario-specific tools listed? PowerShell 7+ not .NET SDK version numbers correct (.NET 8 not .NET Core)? URLs point to official sources?
- **Modular Architecture**: Files under 500 lines? resources.bicep separate from main.bicep? Domain modules in core/ folders? Azure Verified Modules used appropriately?
- **Demo Guide Quality**: Screenshots show deployed resources? Instructions use numbered steps? Placeholders replaced with actual content? Images use raw GitHub URLs?
- **Consistency**: All CONTRIBUTOR comments present? Instruction files referenced (.github/instructions/)? Version follows semantic format (1.0.0 not v1.0.0)?
- **Catalog Compliance**: Badge present linking to aka.ms/trainer-demo-deploy? Links use raw.githubusercontent.com not relative paths? Template suitable for trainer scenarios?
- **Parameters replaced**: [YOUR-PLACEHOLDER] or similar placeholders are left in files? 

## Common Anti-Patterns to Flag

- **Security Issues**: newGuid() for passwords, hardcoded credentials, overly permissive firewall rules, secrets in outputs
- **Documentation Gaps**: Missing cost estimates, unclear verification steps, missing troubleshooting section, incomplete architecture documentation
- **Infrastructure Problems**: Missing SecurityControl tag, no abbreviations.json, resourceGroup targetScope in main.bicep, inline resources instead of modules
- **Naming Violations**: snake_case parameters, lowercase outputs, missing tdd- prefix, inconsistent casing
- **Trainer Blockers**: No feature flags for expensive resources, unclear demo steps, missing screenshots, cost >$20/day
- **Template Quality**: Monolithic files (>1000 lines), missing @description decorators, outdated API versions, no CONTRIBUTING.md
- **azd Incompatibility**: 4-step deployment instructions, missing azd-env-name tag, outputs not in .env format

## Improvement Focus Areas

- **Cost Optimization**: Recommend Basic/Standard SKUs, feature flags for optional resources, realistic cost estimates based on Azure Pricing Calculator
- **Documentation Enhancement**: Add missing sections, improve clarity of demo steps, include architecture diagrams, expand troubleshooting
- **Security Hardening**: Implement managed identities, add RBAC role assignments, remove hardcoded values, use Key Vault for secrets
- **Infrastructure Patterns**: Modularize large files, adopt Azure Verified Modules for production templates, follow abbreviations + resourceToken naming
- **Trainer Experience**: Clarify verification steps, improve screenshot quality, simplify demo instructions, ensure clear demo flow
- **Catalog Readiness**: Ensure CONTRIBUTING.md present, add quality checklist, verify all instruction files referenced, test 3-step deployment

## Quality Tiers Reference

Compare template against catalog quality tiers:

- **Tier 1 (Exemplar)**: tdd-functions-e2e-http-to-eventhubs, protect-apim-with-oauth - Complete documentation, modular architecture, comprehensive parameters, security best practices
- **Tier 2 (Production-Ready)**: BadgeMaker, MachineLearningAZD - Azure Verified Modules, managed identities, monitoring integration, good documentation
- **Tier 3 (Functional)**: Most templates - Basic azd structure, clear purpose, appropriate for demos, adequate documentation
- **Tier 4 (Needs Improvement)**: Missing documentation, unclear purpose, limited guidance

Provide specific, actionable recommendations prioritizing:
1. Security fixes (hardcoded credentials, missing tags)
2. Documentation completeness (cost, time, verification)
3. Trainer-friendliness (demo clarity, cost optimization)
4. Catalog compliance (structure, naming, links)
5. Code quality (modularization, best practices)