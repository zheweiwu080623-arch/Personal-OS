# Personal OS Architecture

## Goal

Personal OS gives an Agent enough context to help without turning the Agent into
the owner of the user's life. It separates discovery, state, reasoning, evidence,
and execution into explicit boundaries.

## Planes

### 1. External information plane

Owned by Cairn in the reference implementation.

Responsibilities:

- connect to external sources;
- normalize source content;
- preserve source identity and timestamps;
- present opportunities, schedules, and signals;
- expose read-only capabilities to an Agent.

It does not own the user's canonical goals, evidence, or task completion claims.

### 2. Personal state and evidence plane

Owned by University OS in the reference implementation.

Responsibilities:

- maintain user-confirmed context, goals, projects, and local tasks;
- distinguish observations from facts;
- attach evidence to claims;
- generate morning and evening briefings;
- expose a bounded context packet to an Agent;
- preserve uncertainty, freshness, and ownership metadata.

The state plane reads external task truth without copying it into a second task
database.

### 3. Agent plane

The Agent:

- selects relevant context;
- reasons over state and external information;
- proposes plans and actions;
- explains uncertainty and missing evidence;
- never silently promotes a proposal into a user decision.

An Agent does not own any canonical store.

### 4. Execution boundary

Execution is optional and environment-specific.

```text
ActionProposal
    -> explicit policy check
    -> user approval when required
    -> execution adapter
    -> ExecutionReceipt
    -> independently verified Evidence
```

The public edition does not ship private execution adapters. A receipt proves
that an adapter reported an attempt; it does not by itself prove that the desired
real-world outcome occurred.

## Ownership matrix

| Data | Canonical owner | Agent access |
| --- | --- | --- |
| External source content | Cairn | Read |
| External opportunities and signals | Cairn / curated state plane | Read and propose |
| User goals and context | User-confirmed state plane | Read; propose changes |
| External tasks | Cairn | Read-only integration |
| Local tasks | State plane | Read and propose |
| Evidence | State plane | Append through a controlled contract |
| Action proposal | Agent / workflow | Create and explain |
| Execution receipt | Execution adapter | Import as evidence input |
| Credentials | User-controlled secret store | Never read into prompts |

The rule is one writer per canonical object. Cross-system reads must preserve
source, timestamp, freshness, and provenance.

## Failure semantics

- A source that is unavailable is reported as unavailable, not empty.
- A partial synchronization remains partial and names the failed source.
- A proposal is not a commitment.
- A receipt is not evidence of outcome.
- Evidence is not automatically a confirmed fact.
- Missing data is represented explicitly rather than inferred.

## Public/private boundary

The public repository contains architecture and release documentation only.
The private workspace may contain personal state, credentials, local device
configuration, and implementation-specific adapters. None of those are required
to understand the public design.

## Compatibility

The v1.0.0 public documentation describes:

- Cairn v1.2.0 / Vol.2.6;
- University OS snapshot verified on 2026-10-27;
- Node.js 22 or newer for Cairn;
- Python 3.14 for the documented state-plane test baseline.

Release-specific verification and limitations are recorded in
[RELEASE_NOTES_v1.0.0.md](RELEASE_NOTES_v1.0.0.md).
