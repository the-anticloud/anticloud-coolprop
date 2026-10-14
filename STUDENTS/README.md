# Students — COOLPROP

**Project:** COOLPROP  
**Category:** CHEMICAL_PRODUCTION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d190a0f3d542756f02639a7ab4d22f54749287d4`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c47e489603f5f1c89a95cb5fc12a92bbd767842bfa554e722c6b0ba9a8065fdd`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `d190a0f3d542756f02639a7ab4d22f54749287d4`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `c47e489603f5f1c89a95cb5fc12a92bbd767842bfa554e722c6b0ba9a8065fdd`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
