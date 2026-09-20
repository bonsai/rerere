# rerere

**Repository Re-Organizer Agent**

rerere receives repository analysis and reorganizes the repository accordingly.

## Position

`repos-analyze` is the **analysis & action hub**: it observes repository data, analyzes repository life cycles, and can execute lifecycle actions such as stale detection, archive, snapshot, and feeds.

`rerere` is the **re-organization agent** downstream of that analysis. Its concern is the internal structure and semantic organization of an individual repository.

```
GitHub repositories
      ↓
repos-analyze
  observe / analyze
      ↓
analysis result
      ↓
rerere
  understand / reorganize
      ↓
organized repository
```

## Core loop

`receive → understand → detect → decide → reorganize → verify → commit`

## Input

Analysis results from `repos-analyze`, together with the target repository's current state.

Typical signals include:

- repository role/domain
- activity and lifecycle state
- duplicate or related repositories
- stale/obsolete candidates
- structural observations
- repository metadata and history

The analysis is evidence. rerere interprets that evidence against the repository itself before changing it.

## Actions

rerere may:

- move
- rename
- merge
- split
- archive internal material
- remove redundant material
- update documentation
- establish clearer boundaries

Prefer minimal and reversible changes.

## Preserve

- repository intent
- working behavior
- canonical data
- useful history
- explicit user intent

## Design principles

1. **1 repo = 1 agent**
2. Structure follows meaning, not a universal template.
3. Do not reorganize for organization itself.
4. Analysis and reorganization are separate concerns.
5. GitHub is the canonical source of truth.

## Ecosystem

- `repos-analyze` — repository analysis & action hub
- `rerere` — repository re-organization
- `agentify` — repository → agent definition
- `nurse-aoi` — conversation → pain/concern observation
- `solve` — issue/pain → action
- `tango` — orchestration

## Principle

> Read what the repository is, receive what analysis discovered, then reorganize it without destroying its meaning.
