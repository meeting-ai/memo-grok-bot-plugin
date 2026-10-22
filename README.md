# Meeting.ai plugin for Grok Bot

![Meeting.ai in a meeting room, with the Meeting.ai notetaker on the table](assets/banner.webp)

Meeting.ai is the AI that works before, during, and after your meeting. It prepares decks and
research before, records and writes the notes during, and turns what was actually said into
minutes, documents, spreadsheets, follow-up decks, audio briefs, and Visual Notes after.

This plugin brings that into Grok Bot. Once connected, you talk to Grok Bot about your meetings
the way you would talk to a colleague who sat in every one of them: ask what happened, ask
what was decided, ask for it written up differently, ask for a picture of it.

## Connection

This package connects to the hosted Meeting.ai MCP server at `https://mcp.meeting.ai/mcp`.
Ask Grok Bot to connect to that URL, then follow the Meeting.ai sign-in prompt and choose
your workspace. The consent screen may name Cursor, Grok Bot's connector identity; this is
expected. See the [Meeting.ai connection guide](https://meeting.ai/mcp) for more help.

## Try it

Once connected, ask in plain words. Three to start with:

> Join my Google Meet and take notes: https://meet.google.com/abc-defg-hij

> Recap all my Acme meetings from September into one summary: decisions, open questions, and action items with owners.

> Turn my Q3 planning meeting into a one-page Visual Note.

## Everything else

Once you are connected, Grok Bot also knows how to tag meetings and Drive files with the tags
you already use, rename files, look up and tidy contacts, read text aloud into an audio file,
generate an image from a prompt, and switch between your workspaces. You do not need to
learn any of that up front. Ask for what you want in plain words, and Grok Bot uses the right
tool or tells you it is done in the web app instead.

Some actions, such as recording, exporting, Visual Notes, and media generation, use your
Meeting.ai subscription or coins. Grok Bot mentions this before doing one. If your account has
no active subscription or coins, Grok Bot tells you and stops.

## What is in this repository

| Path | Purpose |
|---|---|
| `.cursor-plugin/plugin.json` | Plugin manifest for Grok Bot |
| `mcp.json` | Connection to the hosted Meeting.ai MCP server |
| `skills/` | Guidance for recording, editing notes, Visual Notes, setup, and everyday meeting work |
| `oauth/client.json` | Legacy metadata kept available for older installations |

The MCP server itself is a hosted service operated by Meeting.ai. This repository contains no
server code and no credentials.

## Links

- [Connection guide](https://meeting.ai/mcp)
- [Website](https://meeting.ai)
- [Privacy policy](https://meeting.ai/privacy)
- [Terms of service](https://meeting.ai/terms)
- Support: support@meeting.ai

## License

Apache License 2.0. See [LICENSE](LICENSE). The Meeting.ai name, logo, and artwork are trademarks
of Meeting.ai and are not covered by the license; see [NOTICE](NOTICE).
