# AI Report Prompt — RSA vs ECDSA (Verification-Focused)

**Goal:** Write a research report that argues *RSA (RSASSA-PSS)* can be a better choice than ECDSA for blockchain-style verification-heavy workloads, using evidence from the **Blockchain-signature-benchmark** project (112/128/192-bit security levels). The report must be structured, evidence-driven, and cite the provided plots in `resources/plots/`.

## Required Structure
1. **Abstract** — 4–6 sentences summarizing findings and thesis.
2. **How RSA Works (RSASSA-PSS)** — high-level explanation (keygen, sign, verify, probabilistic padding).
3. **How ECDSA Works** — high-level explanation (elliptic curve keys, per-message nonce, sign/verify).
4. **Where They’re Used Today**
   - RSA: TLS, PKI, enterprise systems, some blockchains
   - ECDSA: Ethereum, Bitcoin (secp256k1), many modern systems
5. **Benchmark Setup & Methodology**
   - security levels: 112/128/192-bit
   - metrics: sign/verify time, CPU, memory, key size, signature size
   - workloads: single verification + batch verification (5k–30k)
6. **Results (with plot citations)**
   - Compare RSA vs ECDSA across 112/128/192-bit
   - Highlight verification time advantage of RSA in batch workloads
   - Mention that signing is one-time; verification dominates in blockchains
   - Note key/signature size tradeoffs
7. **Interpretation & Implications for Blockchains**
   - Why verification throughput matters more than signing latency
   - When RSA can be preferred (verification-heavy, throughput-focused systems)
   - When ECDSA still makes sense (compact key/signature, bandwidth constraints)
8. **Conclusion** — firm advocacy for RSA in verification-heavy blockchain validation, with fair caveats.

## Evidence & Plot Usage
Use and reference the following plots from `resources/plots/`:
- `signing_time.png`
- `verification_time_single.png`
- `verification_time_5k.png`
- `verification_time_10k.png`
- `verification_time_15k.png`
- `verification_time_20k.png`
- `verification_time_25k.png`
- `verification_time_30k.png`
- `verification_ratio_summary.png`
- `key_size.png`
- `signature_size.png`
- `cpu_time.png`
- `memory_usage.png`

In the Results section, explicitly reference these figures (e.g., “Figure: verification_time_10k.png shows…”).

## Notes You Must Incorporate
- Signing is typically done once per transaction; verification happens many times by many validators.
- Emphasize verification throughput in decentralized networks.
- The benchmark uses RSASSA-PSS (probabilistic RSA signatures), not RSA encryption.
- The benchmark compares equivalent security levels: 112/128/192-bit.

## Style Requirements
- Academic but readable.
- Cite the plots by filename.
- Use headings and subheadings.
- Provide a short “Limitations” paragraph (hardware-dependent, benchmark scope, key size tradeoff).

## Deliverable
Produce the report in **Markdown**.
