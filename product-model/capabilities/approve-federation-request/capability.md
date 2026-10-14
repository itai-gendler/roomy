---
availability:
  - { place: roomy-app::spaces }
domain: federation
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/federation.ts#respondFederation" }
---

# Approve federation request

An admin of the origin space accepts a pending request.
