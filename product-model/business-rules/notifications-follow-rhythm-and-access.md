---
appliesTo:
  - { type: entity, id: push-subscription }
  - { type: capability, id: send-notifications }
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/push/evaluate.ts#evaluatePush" }
  - { kind: code, role: implementation, target: "packages/appserver/src/push/level.ts" }
---

# Notifications follow each member's rhythm and access

A member is notified only about rooms they may read, never about their own messages, and only as their update rhythm for the space allows — the space's own rhythm, else their default, else Engaged.
