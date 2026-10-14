---
entities:
  - { entity: channel, collects: [Name, Members access] }
  - { entity: channel-permission, collects: [Access] }
  - { entity: role, shows: [Name] }
  - { entity: category, collects: [Name, Channels] }
  - { entity: space, shows: [Name, Join policy], collects: [Category order] }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/sidebar/SpaceSidebar.svelte" }
---

# Space sidebar

A space's structure: its categories and channels with their active threads and unread counts, edited in place by admins.
