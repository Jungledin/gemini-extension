# JungledIn — Gemini CLI extension

Remote MCP connector to JungledIn's Amazon/eBay seller tools (`https://app.jungledin.com/mcp`). Not affiliated with Google — this is JungledIn's own published extension, listed in the public, unreviewed Gemini CLI extensions gallery.

## Install

```
gemini extensions install https://github.com/Jungledin/gemini-extension
```

## What's in this repo

- `gemini-extension.json` — the extension manifest. Declares the remote MCP server and that it requires OAuth, using `dynamic_discovery` so Gemini CLI finds JungledIn's OAuth endpoints and registers itself automatically — no client ID is hardcoded here.
- `GEMINI.md` — context file Gemini CLI loads so the model knows when to reach for JungledIn's tools.

## Notes

- First use will open a browser for the user to sign in to their own JungledIn account.
- Known issue to watch for: Gemini CLI has open bugs (google-gemini/gemini-cli#12628, #29109) where OAuth dynamic discovery / dynamic client registration detection sometimes fails even when the server supports it correctly. If a user reports "No client ID provided and dynamic registration not supported," this is a Gemini CLI-side bug, not a JungledIn server issue — JungledIn's OAuth server has DCR enabled.
