---
name: design-a-board
description: Design or change a printed circuit board with Rocky, siliXon's PCB design agent. Use when the person describes a board, circuit or electronics project to build, or asks to change one.
---

# Design a board

1. Pass the person's request to `ask_rocky` in their words. Add `project` to change an existing board; without one, Rocky starts a new conversation and makes the project when it builds the board. Put sketches, photos and datasheets in `attachments`; ChatGPT fills in files the person attached. When they ask you to send one from disk, call `create_upload`, run its command for that file, and pass its `attachment` in `attachments`.
2. If the result has a `handle` and is not `done`, call `wait` with it until it is. Rocky's work can take minutes.
3. Relay Rocky's `reply`. Do not list every tool step.
4. If the result has `choices`, Rocky is asking, and the person decides. Pick for them only when they already told you what they want. Otherwise show the `question` and choices and ask (in hosts that show the board card, they can tap one there). Send the answer with `ask_rocky`: the `choice` label and its `offer`, or `message` for a choice marked `answer_in_own_words`. A result with `chat` instead of `project` is answered by passing that `chat`.
5. Once there is a project, call `read_board` once so the board card shows it; it follows every later change on its own. Always give the person the `editor_url` when they want to look closer.

Send one message at a time per chat: wait for a running turn before the next.
