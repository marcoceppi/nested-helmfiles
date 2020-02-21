# Example of nested helmfiles

The goal is to override the service config in `models/unit1/values/test.yaml.gotmpl`. The following structures do not work:

```yaml
helmfiles:
- path: ...
  values:
  - default-test:
      config:
        ip: 10.9.0.1
```

```yaml
helmfiles:
- path: ...
  values:
  - test:
      config:
        ip: 10.9.0.1
```

```yaml
helmfiles:
- path: ...
  values:
  - default-test.config.ip: 10.9.0.1
```
