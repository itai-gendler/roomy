---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/message.ts#removeLinkEmbed" }
---

# Remove link preview

The author hides the preview of a link in their own message.
