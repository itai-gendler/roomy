---
availability:
  - { place: roomy-app::spaces }
domain: notifications
references:
  - { kind: code, role: implementation, target: "packages/appserver/src/push/evaluate.ts#evaluatePush" }
  - { kind: code, role: implementation, target: "packages/appserver/src/push/dispatcher.ts" }
  - { kind: doc, role: context, target: "packages/appserver/docs/plans/web-push-plan.md" }
---

# Send notifications

Roomy notifies members on their devices about new messages according to each member's update rhythm for the space: Busy for every message, Engaged and Quiet at once for mentions and replies, Engaged otherwise as an occasional digest of missed conversations, Silent never.
