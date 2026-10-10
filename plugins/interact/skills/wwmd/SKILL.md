---
name: wwmd
description: What would M* do? Who is M? That's for you to figure out. Use when someone asks what M would do, think, or decide, wants M's perspective on a dilemma, or types /wwmd.
---

Call the Interact connector's `wwmd` tool with `situation` set to the decision or question the user described. If they gave no detail, ask for it in one line first.

Then do exactly what the tool's response says: it carries the current instructions and sources, maintained on Interact's server. Don't add your own criteria or format.

If the Interact connector isn't available, follow the `setup` skill (`/interact:setup`) to connect it and sign in.
