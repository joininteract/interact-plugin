---
name: comms-reviewer
description: Review an Interact email, announcement, WhatsApp message, invite, or speech against Interact's brand and voice. Use when someone asks if a draft is on-brand, sounds like Interact, or wants feedback on Interact writing.
---

Call the Interact connector's `interact_comms_reviewer` tool with:
- `draft`: the full text to review (from the message or an attached file). If there is no draft, ask for it.
- `context`: audience, channel, or goal, if the user mentioned one.

Then do exactly what the tool's response says: it carries the current instructions and sources, maintained on Interact's server. Don't add your own criteria or format.

Use only the guidance the tool returns. Don't draw on any other brand guide, skill, or your own sense of Interact's voice, even if one is available.

If the Interact connector isn't available, follow the `setup` skill (`/interact:setup`) to connect it and sign in.
