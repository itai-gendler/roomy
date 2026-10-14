---
availability:
  - { place: roomy-app::spaces }
references:
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/thread/ChannelBoardView.svelte" }
  - { kind: code, role: implementation, target: "packages/app-lite/src/lib/components/thread/ThreadsTab.svelte" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.room.getThreads.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.space.getThreads.ts" }
---

# Browse threads

See a channel's threads, or every thread and channel in a space, by latest activity with who spoke last and what is unread.
