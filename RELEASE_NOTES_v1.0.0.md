# Personal OS v1.0.0 Release Notes

Release date: 2026-10-28

## Summary

Personal OS v1.0.0 is the first public architecture and release-documentation
edition of the project. It defines a user-controlled split between external
information, personal state, evidence, Agent reasoning, and authorized action.

The release links to Cairn v1.2.0 for the public external-information
implementation. The state-plane implementation and environment-specific
execution adapters remain private to protect personal data and credentials.

## Highlights

- explicit ownership and trust boundaries;
- evidence-first task and completion semantics;
- automatic morning and evening briefing design;
- observation-to-attention pipeline;
- read-only Agent context and task-integration contracts;
- separation between proposals, receipts, and evidence;
- offline-first testing and explicit unavailable/partial states.

## Compatibility

- Cairn: v1.2.0 / Vol.2.6, Node.js 22 or newer.
- State-plane documentation: 2026-10-27 snapshot, Python 3.14.
- Public repository: documentation and release assets only.

## Verification evidence

- Cairn v1.2.0 public release suite: 126/126 passed.
- University OS private snapshot suite: 644/644 passed, zero failures and zero
  errors.
- Public materials: no credentials, personal data directories, runtime
  databases, local user-home paths, or private-key markers.

The private implementation test result is stated as release evidence, not as a
claim that its source or data is included here.

## Known limitations

- This public edition does not include the state-plane source tree.
- It does not include private communication or execution adapters.
- File observation in the reference implementation uses bounded polling rather
  than a real-time watcher.
- Some external sources may be unavailable; they are reported as unavailable
  rather than silently treated as empty.
- Level 4 autonomous real-world execution is not claimed.
- The public architecture describes contracts, not a hosted service.

## Compatibility and upgrade

This documentation release has no runtime migration. For Cairn, preserve the
existing data directory and configuration, install the v1.2.0 source beside the
current copy, verify its health endpoint, and only then switch the launcher.

## Security

Never add personal data, credentials, browser profiles, mail, attachments,
runtime databases, or local paths to this repository. See
[SECURITY.md](SECURITY.md) and [PUBLIC_BOUNDARIES.md](PUBLIC_BOUNDARIES.md).
