---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/ChatArea.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.room.getMessages.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.room.updateSeen.ts" }
---

# Read messages

Open a channel or thread and read its messages, with their replies, forwards, reactions and previews. Reading marks the room read.
