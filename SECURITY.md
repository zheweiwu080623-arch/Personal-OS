# Security Policy

## Reporting

Use GitHub's private vulnerability reporting for this repository. Do not post
credentials, personal data, exploitable details, or private logs in a public
issue.

## Supported release

Security fixes are considered for the current major release line. Public
documentation receives corrections through normal pull requests.

## Data handling rules

- Credentials must come from a protected user-controlled source.
- Secrets must never appear in prompts, source files, logs, or release assets.
- Consequential or irreversible actions require explicit user authority.
- Execution receipts and evidence must remain distinguishable.
- Unknown or unavailable sources must not be reported as successful.

## Public repository rule

If personal data is committed accidentally, do not merely delete the working-tree
file. Treat the commit as compromised, rotate exposed credentials, and rewrite
history only after preserving the necessary audit evidence privately.
