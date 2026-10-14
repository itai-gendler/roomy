---
availability:
  - { place: roomy-app::spaces }
domain: permissions
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/role.ts#createRole" }
  - { kind: code, role: implementation, target: "packages/design/src/components/modals/RoleCreateForm.svelte" }
---

# Create role

An admin creates a role with a name and description.
