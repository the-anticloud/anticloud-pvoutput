# Educators — PVOUTPUT

**Project:** PVOUTPUT  
**Category:** SOLAR  
**Upstream:** see BENCH.json  
**Pinned commit:** `2051391e1004988b5935ab75567e35ebbb82ddb5`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `569b3486f463589d59f168e25c2e8d17324fbdc7ba49a98bff3aa573a588a253`  
**Date:** October 2026

## Teaching with PVOUTPUT

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `569b3486f463589d59f168e25c2e8d17324fbdc7ba49a98bff3aa573a588a253` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
