---
availability:
  - { place: roomy-app::spaces }
domain: federation
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/federation.ts#setRoomPermission" }
---

# Change channel sharing

An admin of the origin space sets each of its channels to Off, Read, or Read + write for a federated space.
