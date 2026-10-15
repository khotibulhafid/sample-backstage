# Service Catalog Guide

## Repository Overview

This is a **Backstage Software Catalog** repository for IFG Life (IFGL). It contains YAML entity definitions that are consumed by Backstage to create a service catalog for the organization's microservices ecosystem.

## Entity Types & File Structure

The catalog uses Backstage's standard entity kinds:

- **Domains** (`domains/*.yaml`) - Business domain groupings (e.g., claim, fraud, lifenet, pas)
- **Systems** (`systems/*.yaml`) - Logical groupings of components within domains
- **Components** (`components/<team>/*.yaml`) - Individual services/applications
- **APIs** (`apis/<team>/*.yaml`) - API definitions provided by components
- **Resources** (`resources/*.yaml`) - Infrastructure resources (databases, clusters, Kafka)
- **Organization** (`organization/entities.yaml`) - Groups and user definitions

## Aggregation Files (Root Level)

- `all.yaml` - Master location file referencing all other aggregation files
- `all-domains.yaml` - References all domain definitions
- `all-systems.yaml` - References all system definitions
- `all-components.yaml` - References all production component definitions
- `all-components-uat.yaml` - References UAT environment components
- `all-apis.yaml` - References all production API definitions
- `all-apis-uat.yaml` - References UAT environment APIs
- `all-resources.yaml` - References all resource definitions

## Adding New Entities

When adding new entities, follow the templates in the sample files:

- `sample-component.md` - Component YAML template with all available fields
- `sample-domain.md` - Domain YAML template
- `sample-system.md` - System YAML template

### Key Component Fields

Components support these important spec fields:
- `type`: service, website, workflow, scheduler, consumer
- `lifecycle`: experimental, production, deprecated
- `owner`: group reference (e.g., `default/nbuw`)
- `system`: system reference with namespace
- `providesApis`, `consumesApis`: API relationships
- `dependsOn`: resource dependencies
- `language`, `framework`, `auth`, `secretType`, `runtime`

### Naming Conventions

- Components: `<service-name>-component.yaml`
- APIs: `<service-name>-api.yaml`
- UAT variants: `<name>-uat.yaml` in `uat/` subdirectories
- Namespaces match team/domain names (e.g., `ao-new-business`, `lifenet-acquirer`)

## Workflow for Changes

1. Create/modify YAML entity files in appropriate directories
2. Register new files in the corresponding `all-*.yaml` aggregation file
3. Ensure namespace references are consistent across related entities
4. UAT components go in `<team>/uat/` subdirectories and are registered in `all-*-uat.yaml`

## Major Business Domains

- **ao-*** (Automation Operations): claim, fraud, hospital-network, lifehub, new-business, pos, product-engine, workflow
- **lifeforce-***: admin, group, individu (sales force systems)
- **lifenet-***: acquirer, issuer, network (insurance network systems)
- **payment**: Payment gateway integrations
- **data**: Data platform and ETL services
- **dplk**: Pension fund services
- **psak**: Accounting standard services
