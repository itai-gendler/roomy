---
availability:
  - { place: roomy-app::spaces }
domain: notifications
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/user/settings/notifications/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/push/level.ts" }
---

# Change notification settings

Choose the default update rhythm — Silent, Quiet, Engaged or Busy — for spaces without a rhythm of their own.
