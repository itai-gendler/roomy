---
entities:
  - { entity: user, collects: [Default update rhythm] }
entryPoints:
  - roomy-app: "/user/settings/notifications"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/user/settings/notifications/+page.svelte" }
---

# Notification settings

Whether notifications are on for this device, and the user's default update rhythm.
