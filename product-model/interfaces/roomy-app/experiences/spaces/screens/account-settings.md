---
entities:
  - { entity: space, shows: [Name] }
entryPoints:
  - roomy-app: "/user/settings"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/user/settings/+page.svelte" }
---

# Account settings

The user's own settings, including the spaces they left.
