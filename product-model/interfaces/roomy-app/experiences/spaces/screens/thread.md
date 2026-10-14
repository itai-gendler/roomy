---
entities:
  - { entity: thread, shows: [Name] }
  - { entity: message, shows: [Content, Sent at, Reply to, Mentions, Media, Link previews, Forwarded from, Edited], collects: [Content, Mentions] }
entryPoints:
  - roomy-app: "/{space}/{thread}"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/[room]/+page.svelte" }
---

# Thread

One thread: its message timeline and composer.
