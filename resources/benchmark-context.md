# Blockchain Signature Benchmark — Context & Methodology

This repository’s prompt is backed by results from the **Blockchain-signature-benchmark** project. The benchmark is designed to compare **RSA (RSASSA-PSS)** and **ECDSA** at equivalent security levels used in modern systems.

## What the Benchmark Measures
The script `benchmark_complete.py` runs a full suite and reports:
- **Signing time** and **verification time**
- **CPU time** and **memory usage**
- **Key size** and **signature size**
- **Verification throughput** under batch workloads (5k–30k verifications)

## Security Levels Tested
The benchmark matches RSA and ECDSA at **112**, **128**, and **192-bit** security levels. This ensures comparisons are aligned by cryptographic strength, not just key length.

## Why Verification Matters
In blockchain systems, a signature is created once (signing) but verified many times by validators and nodes. This makes **verification throughput** a dominant cost at scale — particularly for chain validation and block propagation.

## Outputs Used in This Report
The benchmark outputs are stored under `results/graphs/` in the original project and copied into this repo at `resources/plots/`. The report references these plots by filename, including:
- Signing vs verification time
- Batch verification curves (5k–30k)
- Key and signature size
- CPU and memory usage
- RSA/ECDSA verification ratio summary

## Notes on Execution
- The benchmark uses **RSASSA-PSS** (probabilistic RSA signatures) — this is signature logic, not encryption.
- The results are generated automatically by the benchmark script.
- Longer key sizes (very large RSA) can be slower to generate; CI runs often cap the maximum key size to keep runtime reasonable.

This context should be cited in the research report’s methodology and limitations sections.
