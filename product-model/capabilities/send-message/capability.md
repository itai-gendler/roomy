---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/ChatInputArea.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/message.ts#sendMessage" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.sendEvents.ts" }
---

# Send message

Write in a channel or thread: text with formatting, @mentions of members, images and files, and link previews; optionally as a reply to a message.
