---
availability:
  - { place: roomy-app::spaces }
domain: federation
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/federation.ts#requestFederation" }
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts" }
---

# Request federation

An admin of one space asks another space they are a member of to share channels with it, with an optional message to its admins.
