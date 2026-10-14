---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/reaction.ts#addReaction" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/MessageReactions.svelte" }
---

# Add reaction

React to a message with an emoji.
