# siliXon

Design printed circuit boards with Rocky, siliXon's PCB design agent, from Claude, ChatGPT, Cursor or any MCP client: from an idea to a placed, routed and checked board that is ready to manufacture.

This plugin connects your agent to the siliXon MCP server at `https://app.silixon.io/mcp` and adds skills that teach it to use it. Your agent can:

- ask Rocky for a board in plain English, send it photos, sketches and datasheets, and answer its questions;
- place and route a board on siliXon's servers and run the manufacturing check;
- download the KiCad project and the Gerbers;
- import a KiCad project or a Specctra DSN;
- show the live board in the chat, in clients that support MCP Apps.

A siliXon account is required. Connecting opens siliXon's sign-in, where you can also create one. Your plan gives an agent exactly what it gives you in the app, and an agent you connect works only on projects you can open. Disconnect an agent at any time from your account's Sign-in & security page.

## Install

**Claude Code**

```bash
claude plugin marketplace add silixon-io/silixon-plugin
claude plugin install silixon@silixon
```

**Claude, ChatGPT and Cursor**: install siliXon from the client's plugin or connector directory.

**Any other MCP client**: add `https://app.silixon.io/mcp` as a remote (Streamable HTTP) server. It signs in with OAuth.

**Try a local copy**: in Claude Code, `claude --plugin-dir <checkout>`. In the ChatGPT desktop app, `codex plugin marketplace add <checkout>`, then `codex plugin add silixon@silixon`, and restart the app; it shows under Plugins, on the Personal tab. To try another siliXon deployment, replace `https://app.silixon.io` with its origin everywhere in `.mcp.json` (the server URL, the OAuth URLs and `oauth_resource`) and in `.cursor-plugin/plugin.json`.

## Skills

| Skill | Use |
| --- | --- |
| `get-started` | Connect siliXon and see what it can do. |
| `design-a-board` | Design or change a board with Rocky. |
| `check-and-fix-a-board` | Check a board for manufacturing, then place, route or fix it. |
| `import-a-project` | Import a KiCad project or a Specctra DSN. |

## Layout

One folder serves every directory: `.claude-plugin/`, `.cursor-plugin/` and `.codex-plugin/` hold each client's manifest, beside the shared `skills/`, `assets/` and `.mcp.json`.

## Links

- Website: https://silixon.io
- Privacy: https://silixon.io/privacy
- Terms: https://silixon.io/terms
- Support and community: https://discord.gg/k9rjZxVpED

## License

MIT
