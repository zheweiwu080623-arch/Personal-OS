# Contributing

Thanks for reviewing Personal OS.

## Issues

- Use public issues for architecture, documentation, and reproducibility;
- do not include personal data, credentials, private logs, or account details;
- provide a small, redacted reproduction when reporting a problem.

## Pull requests

1. Keep changes focused on public documentation or public component code.
2. Preserve the ownership invariants in [ARCHITECTURE.md](ARCHITECTURE.md).
3. Distinguish verified facts from proposals, estimates, and unknowns.
4. Run available tests and include the exact command and result.
5. Run a secret and personal-information scan before requesting review.

## Public-content gate

A change is not mergeable if it includes:

- credentials or credential-shaped values;
- personal data stores;
- runtime databases, mail, attachments, or browser profiles;
- private-key material;
- local user-home or device-specific paths;
- a claim of successful external action without a receipt and evidence.
