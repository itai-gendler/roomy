---
availability:
  - { place: roomy-app::spaces }
domain: invites
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/SpaceSidebarButtons.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/share-links.ts" }
---

# Copy invite link

Copy a link that brings people to the space: the space's own link when it is public, or an invite link when it is invite-only.
