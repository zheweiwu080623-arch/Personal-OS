# Public Boundaries

This repository is intentionally narrower than the local Personal OS workspace.

## Included

- architecture and design rationale;
- ownership rules;
- public release notes;
- public verification evidence;
- security and contribution guidance.

## Excluded

- personal data and personal reports;
- user goals, schedules, tasks, memories, observations, and evidence records;
- email, calendar, browser, and attachment content;
- credentials, tokens, cookies, private keys, and account IDs;
- runtime databases, logs, caches, backups, and temporary files;
- private execution adapters and machine-specific launch scripts.

## Publication rules

Before publishing a change:

1. run a secret and personal-information scan;
2. verify that no generated state or runtime directory is tracked;
3. check all links and version references;
4. separate verified facts from plans and limitations;
5. do not claim autonomous external execution without a real receipt and
   independently checked evidence.

The public documentation may describe a capability without distributing the
private adapter that implements it on a particular machine.
