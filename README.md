# Audits

## Contributing

This repository scans every commit for secrets. Before your first commit,
install the hook:

```bash
brew install pre-commit    # or: pip install pre-commit
pre-commit install
```

`pre-commit install` activates the [gitleaks](https://github.com/gitleaks/gitleaks)
hook defined in [`.pre-commit-config.yaml`](./.pre-commit-config.yaml). The hook
rejects any commit that contains a secret, before that commit leaves your
machine.

Run `pre-commit install` once in every clone. The committed configuration does
nothing until you do. A `gitleaks` job in CI repeats the scan on every pull
request, so `git commit --no-verify` does not get a secret past review.
