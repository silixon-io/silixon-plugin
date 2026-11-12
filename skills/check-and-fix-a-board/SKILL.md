---
name: check-and-fix-a-board
description: Check a board for manufacturing and fix what the check finds. Use when the person asks whether a board is ready to order, or asks to route, place or fix it.
---

# Check and fix a board

1. Call `check_board`, and `wait` on its handle if it is still running.
2. Report its `readiness` and what is in `attention`, in plain language.
3. If there is a `fix_with_rocky` message and the person wants it fixed, pass it to `ask_rocky`, follow the turn with `wait`, then check again.
4. Use `place_board` and `route_board` when the person asks for placement or routing directly. Each ends `saved`, `stale` (the board changed while it ran, so run it again) or `failed` (`problem` says why). Re-placing the whole board clears the router's copper, so route afterwards.
5. Only tell the person a board is ready when the latest check says so.
