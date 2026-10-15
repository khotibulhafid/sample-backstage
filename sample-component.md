``` yaml
apiVersion: backstage.io/v1alpha1
kind: Component
metadata:
  name: <service_name>
  namespace: <namespace> # team-environment
  description: <description>
  tags:
    - <tag1>
    - <tag2>
  links:
    - title: Source Repository
      url: <url_repo>
    - title: Documentation
      url: <url_documentation>
    - title: Monitoring / Logs (Datadog)
      url: <url_datadog>
    - title: Deployment (ArgoCD)
      url: <url_argocd>
    - title: Docker Image
      url: <url_docker_image>
    - title: Deployment YAML (Env & Config)
      url: <url_deployment>
    - title: Base URL
      url: <url_api>
    - title: Liveness Endpoints
      url: <url_liveness>
    - title: Readiness Endpoints
      url: <url_readiness>
    - title: Swagger / Open API
      url: <url_swagger>
    - title: Kafka Topic List
      url: <url_kafka_topic_list>
    - title: Sample Kafka Message
      url: <url_sample_kafka_message>
spec:
  type: <type_service> # REST/Website/Workflow/Scheduler/Consumer
  owner: <owner_name_or_team>
  system: <system_name>
  domain: <domain_name>
  lifecycle: <lifecycle_status> # experimental, production, deprecated
  environments: <environment1, environment2> # dev, uat, prod
  language: <programming_language> # java / python / javascript
  framework:
    - name: <framework_name> #Quarkus / FastAPI / NodeJS
    - version: <framework_version>
  workflow:
    version: <workflow_version>
  auth:
    method: <auth_method> # OAuth2, API Key, etc.
    notes: <auth_notes>
    links:
      - url: <url_docs_auth>
        title: Auth Documentation
  secretType: <secret_type> #Kubernetes Secret / KMS / AWS Secret Manager
  security:
    rotationPolicy: <rotation_policy> # 90d, manual
  dependsOn: [
    <kind>:<[namespace]/[name]>
  ]
  runtime:
    cluster: <cluster_name>
    namespace: <namespace_service>
  consumeApis: [
    <kind>:<[namespace]/[name]>
  ]
  providesApis: [
    <kind>:<[namespace]/[name]>
  ]
  limits: <rate_limit> # '10/sec', '1000/day'
  usesLibraries:
    - name: <Library1>
      implemented: <True/False>
    - name: <Library2>
      implemented: <True/False>

```