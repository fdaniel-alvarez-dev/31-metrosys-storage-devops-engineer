# 31-aws-reliability-governance-gitops

A portfolio-grade repository that demonstrates **GitOps-style governance** through deterministic CI checks, evidence artifacts, and reviewable automation.

## The top pains this repo addresses
1) Reducing risky changes by enforcing offline-safe validation gates before “production” style checks run.
2) Making governance measurable: guardrails produce evidence artifacts you can review and store.
3) Keeping automation honest: docs and CI match what the code actually does.

## Quick demo (local)
```bash
make demo-offline
make test
```

What you get:
- offline demo pipeline output (no pip installs needed)
- GitOps guardrails report (`artifacts/gitops_guardrails.json`)
- explicit `TEST_MODE=demo|production` tests with safe production gating

## Tests (two explicit modes)

- `TEST_MODE=demo` (default): offline-only checks, deterministic artifacts
- `TEST_MODE=production`: real integrations (requires explicit opt-in + dependencies)

Run demo mode:

```bash
make test-demo
```

Run production mode:

```bash
make test-production
```

## GitOps guardrails

Generate evidence:

```bash
python3 tools/gitops_guardrails.py --format json --out artifacts/gitops_guardrails.json
```

## Sponsorship and contact

Sponsored by:
CloudForgeLabs  
https://cloudforgelabs.ainextstudios.com/  
support@ainextstudios.com

Built by:
Freddy D. Alvarez  
https://www.linkedin.com/in/freddy-daniel-alvarez/

For job opportunities, contact:
it.freddy.alvarez@gmail.com

## License

Personal, educational, and non-commercial use is free. Commercial use requires paid permission.
See `LICENSE` and `COMMERCIAL_LICENSE.md`.
