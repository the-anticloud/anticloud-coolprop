# Integrations and SDK — COOLPROP

**Project:** `COOLPROP`
**Category:** CHEMICAL_PRODUCTION
**Domain:** chemical production and simulation
**Date:** 2026-10-07

---

## SDK

COOLPROP provides a Python SDK for integration:

```python
import coolprop

# Initialize
client = coolprop.Client()

# Use
result = client.process(data)
```

## Integrations

### Anticloud Ecosystem
- AIOSS chain for audit logging
- API Gateway for access control
- Model Registry for model management

### Third-Party
- Docker for containerization
- Kubernetes for orchestration
- Prometheus for monitoring

## Verification

All 16 checks PASS. Evidence: `ISOLATED_LAB_RESULTS/03_Result_Register.md`.
