# Splunk Workflow App Framework

This repository generates Splunk workflow applications backed by KV Store.

## Architectural rules

- Treat workflow-app.yaml as the canonical application specification.
- Do not directly edit generated files when the requested change can be
  represented in workflow-app.yaml.
- Do not connect directly to MongoDB.
- Use documented Splunk KV Store REST endpoints for CRUD.
- Preserve the required fields:
  user, timestamp, message, status, urgency, object.
- Include `_key` in lookup output for record updates.
- Never place credentials or session tokens in source files.
- Keep collections.conf, transforms.conf, dashboard fields, JavaScript
  validation, and SPL synchronized.
- Validate custom SPL and token interpolation.
- Run the generator and validation suite after modifications.
