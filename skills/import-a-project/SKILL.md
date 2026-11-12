---
name: import-a-project
description: Import an existing KiCad project or Specctra DSN into siliXon. Use when the person attaches or links a KiCad ZIP, .kicad_sch or .dsn file.
---

# Import a project

1. Call `import_project` with the `file`: a KiCad project as a ZIP of its folder, a KiCad schematic, or a Specctra DSN. ChatGPT fills in a file the person attached. When they ask you to send one from disk, call `create_upload`, run its command for that file, and pass its `attachment` as the `file`. Never retype a file as base64. Give a `name` if the person gave one. Pass `project` only when they asked to replace that project's board, since it replaces the board.
2. If the result has a `handle` and is not `done`, call `wait` until it is.
3. Report what was imported from `stats`, any `warnings`, and the `editor_url`.
4. If the result says the person's plan does not include this, tell them so and give them its plans link.
