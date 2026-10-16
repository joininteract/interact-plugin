---
name: interact
description: Route any Interact task to the right Interact connector tool — questions about Interact, looking up a member, reviewing comms against the brand, what M would do, or finding and reading Interact documents. Use whenever the user's request involves Interact, its fellowship, programs, retreats, members, brand, or documents.
---

# Using the Interact connector

The Interact connector holds Interact's own documents: Google Drive folders, the Notion guide, Airtable member records, and joininteract.com. **Answer Interact questions from these tools, not from general knowledge,** and cite the links they return.

## First: make sure Interact is connected

Before using any tool below, check that the Interact connector's tools are available in this conversation. If they aren't, the connector isn't connected or signed in yet: follow the `setup` skill (`/interact:setup`) first, then come back to the request.

## Pick the tool for the task

| The user wants to… | Tool | What to pass |
|---|---|---|
| Ask anything about Interact (programs, retreats, colleges, how things work, history, policies) | `ask_interact` | `question`: their full question |
| Find out who someone is, whether they're a fellow, their college, or what they've attended | `interacter-lookup` | `person`: just the name (first name is fine) or email. `question`: what they want to know, if they said |
| Review comms against the brand: check whether writing is on-brand, or get edits for an email, announcement, invite, WhatsApp, or speech | Interact Brand Reviewer (`interact_comms_reviewer`) | `draft`: the full text. `context`: audience or channel, if known |
| Know what M would do | `wwmd` | `situation`: the decision or question, in full |
| Find documents on a topic (a list, not an answer) | `search_interact_docs` | `query`: keywords. `tag`: optional, from `list_interact_sources` |
| Read a whole document found by another tool | `get_interact_document` | `doc_id`: from the earlier result |
| See what's in the corpus, or check the connection | `list_interact_sources` | none |

## How to work with the results

- **Let the tools lead.** `ask_interact`, `interacter-lookup`, `interact_comms_reviewer`, and `wwmd` return the relevant documents plus the current instructions for answering, maintained on Interact's server. Do exactly what they say, without adding your own criteria or format.
- **Comms reviews come only from the Interact Brand Reviewer.** Use the guidance `interact_comms_reviewer` returns, not any other brand guide, skill, or general sense of Interact's voice.
- **Cite every fact** by its [number] and link.
- **Keep multi-word values whole.** Pass a full name or a whole draft as one argument.
- **Go deeper when needed.** If an answer is thin, run `search_interact_docs` with more specific terms, then `get_interact_document` on the best hit.
- **Say what's missing.** If the documents don't cover something, say so rather than filling in from general knowledge.
