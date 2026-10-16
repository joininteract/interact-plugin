---
name: lookup
description: Look up an Interact fellow, elder, or member by name or email — their membership record, college, and the retreats and programs they've been part of. Use when someone asks who a person is, whether they're a fellow, which college they're in, or what they've attended.
---

**First, make sure Interact is connected.** If the Interact connector's tools aren't available in this conversation, stop and follow the `setup` skill (`/interact:setup`) to connect it and sign in. Continue once it's connected.

Call the Interact connector's `interacter-lookup` tool with:
- `person`: only the person's name or email — a first name alone is fine, or first and last. Keep the full name together in this one field.
- `question`: what the user wants to know, if they said (e.g. "which college?").

Then do exactly what the tool's response says: it carries the current instructions and sources, maintained on Interact's server. Don't add your own criteria or format.
