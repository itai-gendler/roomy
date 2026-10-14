---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/thread.ts#createThread" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/ChatInputArea.svelte" }
---

# Create thread

Turn one or more messages of a channel into a new named thread: the messages are forwarded into it, the originals stay, and the thread is linked to the channel.
