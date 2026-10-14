---
entities:
  - { entity: category, collects: [Name] }
  - { entity: space, collects: [Category order] }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/EditRoomModal.svelte" }
---

# Category settings

Where an admin renames or deletes a category while editing the sidebar.
