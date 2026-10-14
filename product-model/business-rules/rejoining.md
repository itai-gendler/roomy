---
appliesTo:
  - { type: entity, id: membership, effect: changes, to: Joined }
permits:
  - related: [{ verb: holds, entity: user }]
    when:
      - { fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/routes/user/settings/+page.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.joinSpace.ts#joinSpaceHandler" }
---

# Only the member rejoins a space they left, unless banned

A space the user left is theirs to rejoin from their left spaces; a ban keeps them out.
