---
name: setup
description: Connect and sign in to the Interact connector (Interact's MCP server). Use when someone wants to set up or install Interact in Claude, when Interact tools are missing or failing, when they see a sign-in or "not on the allowlist" problem, or types /interact:setup.
---

# Set up the Interact connector

The Interact connector is Interact's MCP server at:

```
https://interact.straightupjac.xyz/mcp
```

It gives Claude read-only access to Interact's documents. Access requires signing in with an email on Interact's allowlist.

## 1. Check whether it's already connected

Call the `list_interact_sources` tool.

- **It works:** tell the user they're connected, show the list of sources briefly, and suggest what to try (see "What you can ask" below). Stop here.
- **The tool doesn't exist:** the connector isn't added or isn't signed in. Go to step 2.
- **It errors with an authorization or sign-in problem:** go to step 3.

## 2. Connect it

Give the steps for the app the user is in. If you can't tell, ask which they use.

**Claude Code**
- With this plugin installed, the connector is already configured as `plugin:interact:interact`. Run `/mcp`, select it, and choose **Authenticate**.
- Without the plugin, add it with:
  ```bash
  claude mcp add --transport http interact https://interact.straightupjac.xyz/mcp
  ```
  then run `/mcp` → **interact** → **Authenticate**.

**claude.ai or Claude Desktop**
- With this plugin installed: open **Customize → Plugins → Interact → Connectors** and click **Connect**.
- Without the plugin: **Settings → Connectors → Add custom connector**, paste `https://interact.straightupjac.xyz/mcp`, then **Connect**.

Signing in opens Interact's sign-in page. Enter your email, then the code sent to it.

## 3. If sign-in doesn't work

- **"Couldn't connect" after signing in:** the email is most likely not on Interact's allowlist. Ask an Interact admin to add the exact email you signed in with, then try again. Signing in with a different email also works if that one is on the list.
- **The sign-in page never opens:** in Claude Code, run `/mcp` and choose **Authenticate** again. In claude.ai, remove the connector and add it again.
- **It worked before and stopped:** sign out and back in from the same place (`/mcp` in Claude Code, Connectors in claude.ai).

After fixing, repeat step 1 to confirm.

## What you can ask once connected

- "What programs is Interact running this year?"
- "Who is <name>? Which college are they in?"
- "Is this email on-brand? <draft>"
- "What would M do about <situation>?"
