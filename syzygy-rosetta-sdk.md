# Syzygy Rosetta — SDK

> **Official SDK for the Syzygy Rosetta Governance API**

[![Status: Planned — Phase 4](https://img.shields.io/badge/Status-Planned%20Phase%204-lightgrey.svg)]()
[![Python](https://img.shields.io/badge/Python-Coming%20Soon-blue.svg)]()
[![JavaScript](https://img.shields.io/badge/JavaScript-Coming%20Soon-yellow.svg)]()

---

## Overview

This repository will house the official **Python and JavaScript SDKs** for the Syzygy Rosetta governance API.

The SDK will make it straightforward for developers to integrate Rosetta's `POST /evaluate` governance layer into any application stack without writing raw HTTP requests.

---

## Planned SDK Features

### Python SDK

```python
from rosetta import RosettaClient

client = RosettaClient(base_url="http://localhost:8000")

result = client.evaluate(
    input="Your prompt or AI output here",
    context={
        "environment": "production",
        "industry": "finance"
    }
)

print(result.decision)      # "allow" | "rewrite" | "escalate"
print(result.risk_score)    # float 0.0 – 1.0
print(result.confidence)    # float 0.0 – 1.0
print(result.violations)    # list of policy violations
print(result.rewrite)       # rewritten output or None
```

### JavaScript / TypeScript SDK

```typescript
import { RosettaClient } from '@trivian/rosetta-sdk';

const client = new RosettaClient({ baseUrl: 'http://localhost:8000' });

const result = await client.evaluate({
  input: 'Your prompt or AI output here',
  context: {
    environment: 'production',
    industry: 'healthcare'
  }
});

console.log(result.decision);    // "allow" | "rewrite" | "escalate"
console.log(result.risk_score);  // number 0.0 – 1.0
```

---

## Current Status

The SDK is planned for **Phase 4 — Scaling** of the Rosetta roadmap.

Until the SDK is available, integrate directly with the `POST /evaluate` HTTP endpoint. See the [API Documentation](https://github.com/Trivian-Technologies/syzygy-rosetta-docs) for the full request and response reference.

---

## Direct API Integration (Now)

While the SDK is in development, you can call Rosetta directly:

```bash
curl -X POST http://localhost:8000/evaluate \
  -H "Content-Type: application/json" \
  -d '{
    "input": "Your prompt here",
    "context": {
      "environment": "production",
      "industry": "general"
    }
  }'
```

---

## Stay Updated

Watch this repository to be notified when the SDK development begins.

Follow [@TrivianOS](https://x.com/TrivianOS) for product updates.

---

## Related Repositories

| Repository | Role |
|---|---|
| [syzygy-rosetta-originbase](https://github.com/Trivian-Technologies/syzygy-rosetta-originbase) | Core governance engine |
| [syzygy-rosetta-docs](https://github.com/Trivian-Technologies/syzygy-rosetta-docs) | Full documentation |
| [syzygy-rosetta-sandbox](https://github.com/Trivian-Technologies/syzygy-rosetta-sandbox) | Testing and simulation |

---

## Organization

Part of the [Trivian Technologies](https://github.com/Trivian-Technologies) organization.

**Website:** [triviantech.com](https://triviantech.com) | **X:** [@TrivianOS](https://x.com/TrivianOS) | **LinkedIn:** [Trivian Technologies](https://www.linkedin.com/company/awakening-the-architect)
