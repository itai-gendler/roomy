---
entities:
  - { entity: channel, shows: [Name, Members access] }
  - { entity: message, shows: [Content, Sent at, Reply to, Mentions, Media, Link previews, Forwarded from, Edited], collects: [Content, Mentions, Reply to, Media, Link previews] }
  - { entity: reaction, shows: [Emoji], collects: [Emoji] }
  - { entity: thread, shows: [Name], collects: [Name] }
  - { entity: read-position, shows: [Unread count] }
entryPoints:
  - roomy-app: "/{space}/{channel}"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/[room]/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/ChatArea.svelte" }
---

# Channel

One channel: its message timeline and composer, and its threads.
