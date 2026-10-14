---
domain: chat
relations:
  - { entity: reaction, verb: has, cardinality: one-to-many }
references:
  - { kind: code, role: implementation, target: "packages/sdk/src/schema/events/message.ts" }
  - { kind: code, role: implementation, target: "packages/appserver/src/handlers/space.roomy.room.getMessages.ts" }
---

# Message

Something a user said in a channel or thread: text with mentions, media and link previews, a reply to another message, or a forward of one.

## Information kept

- **Content** — the message text, with its formatting and links
- **Sent at** — when the message was sent
- **Reply to** — the message it answers, when it is a reply
- **Mentions** — the people it mentions
- **Media** — the images and files attached to it
- **Link previews** — the previews of the links in it that are still shown
- **Forwarded from** — the original message, its author and room, when it is a forward
- **Edited** — whether it changed since it was sent
- **Timeline position** — which room it sits in and where in that room's timeline
