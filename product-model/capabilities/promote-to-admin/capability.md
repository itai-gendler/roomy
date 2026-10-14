---
availability:
  - { place: roomy-app::spaces }
domain: members
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/members/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#AddAdmin" }
---

# Promote to admin

An admin makes a member an admin.
