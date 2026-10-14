---
appliesTo:
  - { type: entity, id: federation, effect: creates }
permits:
  - related: [{ verb: requests, entity: space }, { verb: has, entity: membership }, { verb: holds, entity: user }]
    when:
      - { entity: membership, fact: Role, is: Admin }
      - { entity: membership, fact: Banned, is: "No" }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/writeAuth.ts" }
---

# Only an admin of the asking space requests federation

The admin must also be a member of the space they ask, and the two spaces must not already federate or have been turned down.
