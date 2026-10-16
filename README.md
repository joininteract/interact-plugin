# Interact plugin for Claude

Helps Interact's internal team (fellowship, Studio, chapter leads, and college directors) find information and get answers to their questions about Interact, straight from Interact's own documents.

It connects Claude to Interact's knowledge base, so questions about programs, retreats, colleges, members, and how things work get answers grounded in Interact's records, with links to the sources.

**You need an email on Interact's allowlist.** Ask an Interact admin to add you before you start.

## How to use it

### In Claude (claude.ai or the Claude desktop app)

1. **Open the plugins page.** Go to **Customize** and select the **Plugins** tab. Click **Add** (top right), then **Add marketplace**.

   ![Customize → Plugins → Add → Add marketplace](docs/install/1-add-marketplace.png)

2. **Choose "Add from a repository".**

   ![Add from a repository](docs/install/2-add-from-repository.png)

3. **Paste the repository URL and sync.** Paste the URL below, select **Use "https://github.com/joininteract/interact-plugin"**, then click **Sync**.
   ```
   https://github.com/joininteract/interact-plugin
   ```
   Claude shows a standard warning about trusting plugins from outside Anthropic. That's expected for any marketplace you add yourself.

   ![Paste the URL, then Sync](docs/install/3-paste-url-sync.png)

4. **Turn on the Interact plugin.** Open **Interact** (from interact-plugin) and switch on the toggle at the top right.

   ![The Interact plugin page, with the toggle at the top right](docs/install/4-enable-plugin.png)

5. **Connect and sign in.** On the same page, open the **Connectors** tab and connect **interact**. Enter your allowlisted email, then the code Interact's sign-in page emails you.

6. **Start asking.** Click **Try in chat**, or open a new chat, and ask anything about Interact. No special commands needed:
   - "What programs is Interact running this year?"
   - "Who is Jordan Lee? Which college are they in?"
   - "Is this email on-brand?" followed by your draft
   - "What would M\* do about…"

### In Claude Code

1. **Add and install the plugin:**
   ```
   /plugin marketplace add joininteract/interact-plugin
   /plugin install interact@interact
   ```
2. **Connect and sign in:** run `/interact:setup` and follow the steps. It opens Interact's sign-in page; enter your allowlisted email and the emailed code.
3. **Start asking**, in plain language or with a shortcut:

   | Shortcut | What it does |
   |---|---|
   | `/interact:ask <question>` | Answers questions about Interact, with sources |
   | `/interact:lookup <name or email>` | Looks up a member: their record first, then retreat and program history |
   | `/interact:comms-reviewer <draft>` | Reviews a draft against Interact's brand and voice |
   | `/interact:wwmd <situation>` | What would M\* do? Who is M? That's for you to figure out. |
   | `/interact:setup` | Checks your connection and helps you sign in |

4. **Stay up to date (optional):** `/plugin` → **Marketplaces** → **interact** → **Enable auto-update**.

### If something doesn't work

- **Claude says it can't connect after you sign in:** your email probably isn't on the allowlist yet. Ask an Interact admin to add the exact email you used.
- **Interact's answers don't show up:** check the plugin is connected (Connectors tab on claude.ai, or `/interact:setup` in Claude Code).
- **Still stuck:** ask in the Interact team channel.

## Data

Requests go to Interact's server, which searches Interact's indexed documents. Access is read-only, and the plugin stores nothing itself. Only users on the Interact allowlist can access data. Ask an Interact admin to add you.

## Maintainers

- The skills here are thin. The real logic (tools, instructions, documents) lives in the private `interact-mcp` server, so most changes need no plugin update.
- `plugin.json` has no `version`, so Claude Code users track the latest commit.
- The server URL appears in two places: `plugins/interact/.mcp.json` and `skills/setup/SKILL.md`. Update both when moving to mcp.joininteract.com.
- Validate before pushing: `claude plugin validate .`
