# Personal OS

Personal OS is an architecture for a user-controlled personal AI environment. It
separates external information, personal state, evidence, and authorized action
instead of placing everything in one opaque assistant or database.

This repository is the public v1.0.0 documentation and release surface. The
working implementation remains private so that personal data, credentials,
runtime configuration, and environment-specific integrations cannot leak through
a public source tree.

## Core model

```text
User authority
    |
    +-- External information plane
    |      source collection -> normalization -> presentation
    |
    +-- Personal state and evidence plane
    |      context -> goals -> tasks -> evidence -> briefings
    |
    +-- Agent
           selection, reasoning, planning, and proposals
    |
    +-- Authorized execution boundary
           action proposal -> approval -> receipt -> evidence
```

The model has four invariants:

1. The user is the final authority for goals, commitments, and consequential
   actions.
2. External facts and personal state have different owners and failure semantics.
3. `ActionProposal`, `ExecutionReceipt`, and `Evidence` are distinct objects.
4. A successful tool call is not, by itself, proof that an outcome was achieved.

## Components in v1.0.0

| Component | Public status | Responsibility |
| --- | --- | --- |
| Cairn v1.2.0 | Source public | External information collection and presentation |
| University OS | Documentation only in this edition | Personal state, evidence, briefings, and read-only Agent contracts |
| Execution integrations | Not included | Private, environment-specific action adapters |

The public Cairn source is available at
[zheweiwu080623-arch/Cairn](https://github.com/zheweiwu080623-arch/Cairn).

## What is public in this repository

- product scope and architecture;
- ownership and trust boundaries;
- release notes and compatibility expectations;
- verification evidence and known limitations;
- contribution and security policies.

## What is intentionally excluded

- personal contexts, goals, tasks, observations, and reports;
- credentials, tokens, cookies, private keys, and account configuration;
- runtime databases, caches, mail, attachments, and browser profiles;
- device identifiers and local filesystem paths;
- private execution adapters and environment-specific launch scripts.

## Status

Personal OS v1.0.0 is a public architecture release. It documents a working local
prototype and a verified Cairn integration; it does not claim fully autonomous or
irreversible external execution.

See [ARCHITECTURE.md](ARCHITECTURE.md),
[RELEASE_NOTES_v1.0.0.md](RELEASE_NOTES_v1.0.0.md), and
[SECURITY.md](SECURITY.md).
