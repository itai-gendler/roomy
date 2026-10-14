---
availability:
  - { place: roomy-app::spaces }
domain: permissions
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/role.ts#deleteRole" }
---

# Delete role

An admin deletes a role; its members lose the access it gave.
