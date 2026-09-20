# rerere

**Repository Re-Organizer Agent**

rerere reads a repository, understands its current structure and meaning, and reorganizes it with minimal change.

It is the repository-organizing agent in the bons.ai ecosystem.

## Core loop

`read → understand → detect → decide → reorganize → verify → commit`

## Design principles

1. **1 repo = 1 agent**
2. Preserve the repository's own semantics.
3. Prefer minimal and reversible changes.
4. GitHub is the canonical source of truth.
5. Structure follows meaning, not a universal template.

## Related agents

- `agentify` — turns a repository into an agent by defining `agent.md`
- `rerere` — organizes an existing repository
- `nurse-aoi` — observes conversations and notices pain/concern
- `solve` — turns issues into actions
- `tango` — orchestrates agents

## First principle

**Do not organize for organization itself. Organize so the repository can be understood and acted on.**
