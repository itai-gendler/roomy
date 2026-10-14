---
availability:
  - { place: roomy-app::spaces }
domain: federation
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/federation.ts#removeFederation" }
---

# Remove federation

An admin of either space ends a federation after confirming; every shared channel stops being shared.
