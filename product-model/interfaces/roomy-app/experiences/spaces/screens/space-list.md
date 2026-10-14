---
entities:
  - { entity: user, collects: [Space order] }
  - { entity: space, shows: [Name, Avatar] }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/ServerBar.svelte" }
---

# Space list

The user's spaces, in their own order, with a way into each.
