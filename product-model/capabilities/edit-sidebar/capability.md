---
availability:
  - { place: roomy-app::spaces }
domain: sidebar
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/SpaceSidebar.svelte" }
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#UpdateSidebar" }
---

# Edit sidebar

An admin rearranges categories and moves channels between them, saving the new arrangement at once.
