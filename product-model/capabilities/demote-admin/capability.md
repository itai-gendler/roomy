---
availability:
  - { place: roomy-app::spaces }
domain: members
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/space.ts#RemoveAdmin" }
---

# Demote admin

An admin makes another admin an ordinary member.
