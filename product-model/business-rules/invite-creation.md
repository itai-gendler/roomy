---
appliesTo:
  - { type: entity, id: invite, effect: creates }
permits:
  - related: [{ verb: has, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
  - related: [{ verb: has, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Banned, is: "No" }
      - { entity: space, fact: Member invites, is: Allowed }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/[space]/settings/invites/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getInvites.ts" }
---

# Admins, and members when allowed, create invite links

Admins always may; other members may only while the space allows member invites.
