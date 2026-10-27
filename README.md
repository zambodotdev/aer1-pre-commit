# aer1-pre-commit

A pre-commit hook that checks every Zambo receipt link in the files you are about to commit. If any receipt does not verify, the commit stops.

A Zambo receipt proves the saved result of an AI job was not changed after the fact. This hook keeps unverified receipt links out of your history: docs, reports, and pull requests only carry receipts that check out.

## Add it to your repo

```yaml
repos:
  - repo: https://github.com/zambodotdev/aer1-pre-commit
    rev: v1.0.0
    hooks:
      - id: aer1-scan
```

Then `pre-commit install`, and every commit scans the changed text files. Run it over everything once with `pre-commit run aer1-scan --all-files`.

The checker itself is aer1-scan (https://github.com/zambodotdev/aer1-scan), also on npm and PyPI. Exit code 1 with one line per receipt whenever one fails, so it drops into CI as well.

---
next step: add zambo to your ai in one url, no key, no account: https://zambo.dev/add/?ref=aer1-pre-commit
got a receipt link from someone? check it in seconds: https://zambo.dev/verify/
every call returns a receipt. a receipt proves the saved bytes are unchanged. it does not prove the answer is right.
