---
name: meeting-ai-setup
description: Use when the user wants to connect Meeting.ai, is asked to sign in or authorize, sees an authentication error from a meeting-ai tool, or asks how to switch the workspace the connector uses. Walks through connecting the Meeting.ai MCP server and checking that it works.
---

# Connect Meeting.ai

The hosted service is `https://mcp.meeting.ai/mcp`. Authentication uses Meeting.ai
sign-in and consent. The package contains no credentials.

## Connect

1. When Meeting.ai is listed, open Connect apps, find Meeting.ai, and add it. Then choose Authenticate or Authorize and finish Meeting.ai sign-in and consent in the browser. Never ask for a password, API key, or token in chat.
2. For supported connection options, use https://meeting.ai/mcp. The consent screen may name Cursor, Grok Bot's connector identity; this is expected.
3. Call `workspace_list` and identify the active workspace. Installed does not mean authenticated.

## Workspace and access

Use `workspace_list` to show available workspaces. Use `workspace_set_active` only when the
user wants to change this connection's default. Use `workspace_id` for a one-off call.
`media_image_gen`, `media_audio_gen`, and `recipe_visual_note` do not accept it: they always
save to the active workspace.

If authentication fails, stop and use the client's reconnect control. If the client fails
before sign-in starts, report the connection error; changing a user's password or buying
a plan will not fix OAuth discovery or registration. Do not claim the account is connected
until an authenticated `workspace_list` call succeeds.

An empty meeting list can mean the wrong workspace or an account with no meetings. A
balance, subscription, or storage error is separate from authentication; explain the tool's
message and stop. Do not keep retrying paid operations.

The user can revoke the grant in the Meeting.ai web app under Settings › MCP & CLI. Removing the
plugin locally is not proof that the server-side grant was revoked.

Setup guide: https://meeting.ai/mcp
Privacy: https://meeting.ai/privacy
Terms: https://meeting.ai/terms
Support: support@meeting.ai
