# renovate-pip-compile-test

Test repo to verify that Renovate's pip-compile manager updates both the input file (`requirements.txt`) and the output file (`requirements.lock`) atomically in a single PR.

## Setup

- `requirements.txt` — direct dependencies (deliberately old versions)
- `requirements.lock` — pip-compile generated lockfile with pinned transitive deps
- `renovate.json` — pip-compile manager enabled, pip_requirements disabled

## Expected Renovate behavior

1. Detect updates for direct deps (click, requests, pyyaml)
2. Update version pins in `requirements.txt` (input file)
3. Regenerate `requirements.lock` (output file) via pip-compile
4. Commit both file changes in a single PR
