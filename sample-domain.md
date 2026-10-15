```yaml
apiVersion: backstage.io/v1alpha1
kind: Domain
metadata:
  name: <domain-name>                 # Unique identifier for the domain, use lowercase and dash-separated
  namespace: <domain-namespace>       # Namespace representing the team or area responsible for this domain
  title: <Domain Title>               # Human-readable title for UI display
  description: <Domain Description>   # Describe the scope, capabilities, and responsibilities of the domain
  tags:                               # Optional tags to improve discoverability in the catalog
    - <tag1>
    - <tag2>
spec:
  owner: group:<team-responsible>     # The team or group responsible for managing this domain
```