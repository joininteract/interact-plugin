---
name: ask
description: Answer questions about Interact (programs, history, people, events, policies, how things work) from Interact's own documents. Use for any question about Interact.
---

**First, make sure Interact is connected.** If the Interact connector's tools aren't available in this conversation, stop and follow the `setup` skill (`/interact:setup`) to connect it and sign in. Continue once it's connected.

Call the Interact connector's `ask_interact` tool with `question` set to the user's full question.

Then do exactly what the tool's response says: it carries the current instructions and sources, maintained on Interact's server. Don't add your own criteria or format.

For follow-ups, use `search_interact_docs` to find more and `get_interact_document` to read a full document.
