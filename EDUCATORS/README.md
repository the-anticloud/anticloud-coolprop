# Educators — COOLPROP

**Project:** COOLPROP  
**Category:** CHEMICAL_PRODUCTION  
**Upstream:** see BENCH.json  
**Pinned commit:** `d190a0f3d542756f02639a7ab4d22f54749287d4`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `c47e489603f5f1c89a95cb5fc12a92bbd767842bfa554e722c6b0ba9a8065fdd`  
**Date:** October 2026

## Teaching with COOLPROP

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `c47e489603f5f1c89a95cb5fc12a92bbd767842bfa554e722c6b0ba9a8065fdd` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
