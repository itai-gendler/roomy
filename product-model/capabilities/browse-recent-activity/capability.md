---
availability:
  - { place: roomy-app::spaces }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/feed/ActivityFeed.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getActivityFeed.ts" }
  - { kind: doc, role: context, target: "packages/appserver/docs/activity-feed-api.md" }
---

# Browse recent activity

See the latest conversations across the user's spaces on Home.
