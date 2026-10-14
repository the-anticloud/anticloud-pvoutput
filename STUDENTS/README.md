# Students — PVOUTPUT

**Project:** PVOUTPUT  
**Category:** SOLAR  
**Upstream:** see BENCH.json  
**Pinned commit:** `2051391e1004988b5935ab75567e35ebbb82ddb5`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `569b3486f463589d59f168e25c2e8d17324fbdc7ba49a98bff3aa573a588a253`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `2051391e1004988b5935ab75567e35ebbb82ddb5`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `569b3486f463589d59f168e25c2e8d17324fbdc7ba49a98bff3aa573a588a253`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
