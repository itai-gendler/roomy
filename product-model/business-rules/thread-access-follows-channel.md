---
appliesTo:
  - { type: entity, id: thread }
  - { type: capability, id: read-messages }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/auth/access.ts#resolveRoom" }
---

# A thread's access is its channel's

Nobody may do more in a thread than in the channel it grew from: who reads and writes a thread follows the channel's Members access and role access, and threads have no permission settings of their own.
