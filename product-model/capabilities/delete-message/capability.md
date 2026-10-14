---
availability:
  - { place: roomy-app::spaces }
domain: chat
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/[room]/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/mutations/message.ts#deleteMessages" }
  - { kind: code, role: implementation, target: "packages/design/src/components/content/thread/message/DeleteMessageDialog.svelte" }
---

# Delete message

Remove a message after confirming; authors delete their own, admins anyone's, and admins may delete several selected messages at once.
