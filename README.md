# Chui plugin

[Chui](https://chui.io) records meetings on a phone, a watch, a computer or the
web, then transcribes and summarises each one in the language it was held in.
This plugin brings the same account into your assistant.

Search every meeting you recorded and quote what was said, read a meeting's
summary or its transcript, ask about the people in your meetings and what is
coming up on your calendar, and correct, share and organise meetings, people
and settings in your own words. Nothing here can start a recording in a
room — that needs a device with a microphone there; the one exception is a
phone call placed through your own Chui number, which Chui records.

## What is in it

Only a connection to Chui's hosted MCP server. No skills, hooks, commands or
local code; nothing is installed or run on your machine.

| File | For |
|---|---|
| `.mcp.json` | Claude Code and Grok Build (`type: http`) |
| `mcp.json` | Cursor (`type: streamable-http`) |
| `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json` | Claude Code |
| `.grok-plugin/plugin.json` | Grok Build |
| `.cursor-plugin/plugin.json` | Cursor |
| `plugin.json` | other agents that read the agent-plugins.org manifest |

## Install

- **Grok Build:** `/marketplace`, find Chui, press `i` (once listed).
- **Claude Code:** `/plugin marketplace add generativechaos/chui-plugin`, then
  `/plugin install chui@chui`. Or without the plugin:
  `claude mcp add --transport http chui https://mcp.chui.io`.
- **Cursor:** from the Cursor marketplace (once listed), or add
  `https://mcp.chui.io` as an MCP server.
- **grok.com, claude.ai, ChatGPT:** add `https://mcp.chui.io` as a custom
  connector. Step-by-step pages: <https://chui.io/grok>,
  <https://chui.io/claude>, <https://chui.io/chatgpt>. In claude.ai Chui is
  also listed in the Connectors Directory.

## Network and credentials

- **Two addresses, both Chui's own**, run by Generative Chaos LLC, the maker
  of Chui: `https://mcp.chui.io`, the MCP server, and `https://api.chui.io`,
  where your assistant registers and signs you in (`/oauth/…`, named by
  `mcp.chui.io/.well-known/oauth-protected-resource`). Nothing else is called.
- **Sign-in:** OAuth 2.1 with dynamic client registration and PKCE (S256). Your
  assistant registers itself; the first call opens Chui's own page, where you
  sign in with Apple, Google or Microsoft, as in the Chui app. No API key, no
  secrets in this repo, nothing read from your machine.
- **What it can do:** read and change your own Chui account, and, when you ask,
  act beyond it the way the app does: email meeting notes or a promised
  follow-up to the people in a meeting, post a summary or a to-do where you set
  them to go, share a meeting by a link, ring a phone through your Chui number,
  send a code to confirm a phone number or a work address, and invite a
  colleague into your company. Deleting a meeting, folding two people into
  one, and sending notes, a follow-up or an invitation to other people take
  two steps: Chui first names exactly what would happen, and it happens only
  after you agree. Re-sending an invitation already agreed to, a confirmation
  code you asked for, and a phone call you asked for go in one.

You need a Chui account; signing in creates one.

- Privacy: <https://chui.io/privacy>
- Terms: <https://chui.io/terms>
- Support: support@chui.io

## License

MIT, © 2026 Generative Chaos LLC. The Chui name and logo are not covered by
the license.
