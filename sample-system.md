```yaml
apiVersion: backstage.io/v1alpha1
kind: System
metadata:
  name: <system-name>-system
  namespace: <namespace>
  title: <Human Readable System Name>
  description: >
    <One sentence describing the main responsibility of this system and
    how it fits into the domain or platform.>
  tags:
    - <primary-function>
    - <secondary-function>
    # - <optional-technology-or-pattern>
spec:
  owner: group:<group-name>
  domain: domain:<domain-name>
```