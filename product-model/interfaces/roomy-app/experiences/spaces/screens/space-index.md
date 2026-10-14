---
entities:
  - { entity: thread, shows: [Name] }
  - { entity: channel, shows: [Name] }
  - { entity: message, shows: [Content, Sent at] }
  - { entity: read-position, shows: [Unread count] }
  - { entity: space, shows: [Name] }
entryPoints:
  - roomy-app: "/{space}"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/thread/ThreadsTab.svelte" }
---

# Space index

A space's threads and channels by latest activity.
