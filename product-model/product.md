---
id: roomy
summary: Group chat for online communities on AT Protocol, where conversations grow into threads and shared knowledge.
category: communication
tags: [group-chat, community, at-protocol, bluesky]
license: MPL-2.0
languages: [en]
limitations:
  - People sign in with their own AT Protocol account, such as a Bluesky handle; Roomy keeps their profile in that account.
  - Threads have no permissions of their own; who reads and writes a thread follows the channel it grew from.
  - Archiving a channel or thread hides it from everyone but admins and never deletes it.
  - Only a message's author edits it; admins may delete any message but never rewrite one.
  - Media can be attached only in public spaces.
references:
  - { kind: doc, role: intent, target: README.md }
  - { kind: doc, role: intent, target: PRODUCT.md }
  - { kind: doc, role: context, target: ARCHITECTURE.md }
---

# Roomy

Roomy is a group messaging app for online communities, built on AT Protocol.
People sign in with their existing Bluesky or other AT Protocol account and
gather in spaces. A space holds channels, grouped into categories in its
sidebar; a conversation in a channel can be turned into its own named thread.
Admins shape the space, decide who reads and writes each channel through
members' access and roles, invite people into invite-only spaces, moderate
members, and can share channels with other spaces through federation. Members
chat with mentions, replies, reactions, forwards and media, follow unread
counts and recent activity, and choose how often Roomy notifies them.

## Intent

Roomy gives online communities "tools for autonomous collaboration —
designable, gardenable spaces not just for chat, but for cultivating a web of
shared understanding together". Every communication artifact can grow from a
chat message into a thread and onward into documentation, so a community's
conversations become legible, lasting knowledge. People bring their own
identity and extend their existing social profile with Roomy.
