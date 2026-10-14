---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/chat/RoomPickerModal.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/forward.ts#buildForwardEvents" }
---

# Forward messages

Repost one or more messages in another channel or thread of the same space, with an optional note, keeping the original visible in the forward.
