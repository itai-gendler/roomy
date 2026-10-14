---
entities:
  - { entity: user, shows: [Display name, Handle, Avatar, Banner, Description, Pronouns, Website], collects: [Display name, Description, Pronouns, Website, Avatar, Banner] }
  - { entity: message, shows: [Content] }
entryPoints:
  - roomy-app: "/user/{user}"
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/user/[user]/+page.svelte" }
---

# Profile

A user's profile, which its owner can edit.
