---
entities:
  - { entity: space, collects: [Name, Description, Avatar, Join policy, Member invites, Suggested to others, Category order] }
  - { entity: category, collects: [Name, Channels] }
  - { entity: channel, collects: [Name, Members access] }
entryPoints:
  - roomy-app: "/new"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/new/+page.svelte" }
---

# New space

The form that creates a space.
