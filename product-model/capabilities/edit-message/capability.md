---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/message.ts#editMessage" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/ChatMessage.svelte" }
---

# Edit message

The author changes the text of their own message, adding or hiding link previews.
