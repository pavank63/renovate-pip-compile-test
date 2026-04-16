# renovate-pip-compile-test

Test repo to verify Renovate pip-compile manager with standard naming:
- `requirements.in` — direct deps (input)
- `requirements.txt` — pip-compile lockfile (output)
- `requirements-dev.txt` — dev deps (should NOT be managed by pip-compile)

## Expected behavior

1. Renovate detects `requirements.txt` as pip-compile output
2. Updates `fromager` pin in `requirements.in` when new version available
3. Regenerates `requirements.txt` with updated transitive deps
4. Does NOT touch `requirements-dev.txt`
