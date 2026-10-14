---
entities:
  - { entity: space, shows: [Name] }
  - { entity: channel, shows: [Name] }
  - { entity: thread, shows: [Name] }
  - { entity: message, shows: [Content, Sent at] }
entryPoints:
  - roomy-app: "/"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/feed/ActivityFeed.svelte" }
---

# Home

The start page: the user's spaces and the recent activity across them.
